# CMU《深度学习系统｜CMU 10-414714 Deep Learning Systems 2022 fall》中英字幕 p14 -15-Lecture 14 - Implementing Convolutions.zh_en -BV1ERtYepEpy_p14-

Hi everyone and welcome to our lecture on implementingmple convolutions。😊。

So in the last lecture we describe kind of the mathematics of convolutions。

 you know how we both what the operation of convolution is and how we implement this from a standpoint of automatic differentiation。

But today we're going to talk about actually how we implement it in code。

 so how do you really code a convolution？And we' I should go through a few different ways of coding convolutions first as sort of。

 I think explicit set of four loops， then as a set as a set of sort of。

Normal matrix implications with operations with the tens we already have and finally。

 as a sort of one big matrix operation using what's called the Incal operation and we'll show how to that kind efficiently using correct techniques from matrix str Now it may seem and if you sort covered the lectures time it may seem like some of these operations are somewhat complex especially for 2D matrices and things like this for 2D images。

 how do you really create the proper matrices。 This might seem like a very sort of arduous task。

 but as we'll show today， it actually ends up being quite simple with the use of these very nice kind of striding tricks So let's jump right in and kind of get started with implementinging compvols Now I will actually start this off by live coding this I'm actually going code everything here in the notebook and this notebook that I'm gonna be coding into you can download it on the course webpage but I would actually encourage everyone following along to just go ahead and implement with me as I'm doing these things even just copying code verbatim can be a very extractive process。

😊。

![](img/0932df05d90d8e157333d6981e19c846_1.png)

![](img/0932df05d90d8e157333d6981e19c846_2.png)

And so I would really sort of recommend you all do that。

 though of course the notebook with all the code implemented will be available on the course website。

Allright， so the first thing we're going to talk about in this lecture is storage order so storage order deals with sort of how we store the tensors involved with multiplication of matrices or start with convolutions in memory and so you've learned a lot about storage of sort of traditional matrices like with strides and row order and column row major order and column column row major order and column major order。

 but in the case of convolutions we actually have larger tensors and we need to know how to store these things and what's the right way of storing these in memory。

😊。

![](img/0932df05d90d8e157333d6981e19c846_4.png)

So I'm going to switch over to my iPad here briefly and talk about kind of the the sizes involved with these things。

 So remember the the sort of the the operator we're doing in convolutions we want to take a height by width image。

 which is really you know height by width by channel tensor。😊。

And I' saw those actually channel in Tensor and we want to convve it with this， say three by3 filter。

 or really more generally kind of a K by k convolutional filter， but remember in our notation here。

 each cell here was actually itself a C in by C out。

 I guess actually least it was C out by C in was the convention we used C out。😊，By C in。

Matrix and so doing this， we sort of want to kind perform these in the right way such that they're sort of stored it properly and so particular we need to store input images we we will need a C in by height by width so rank3 tensor。

 but we're actually going to make a rank for tensor because we're going to include a batch dimension and then for storing weight we need a K by K by C out by C in tensor but we'll talk about how how to store these in a second。

😊。

![](img/0932df05d90d8e157333d6981e19c846_6.png)

Okay， let's go back to our code here。The most obvious way to store our input images is in this format here。

 right， so we're going to store them as a multidimensional tensor。

 a four dimensional tensor where the first dimension indexes indexes over batches。

The second dimension indexes over the height of the image， so batches， you know。

 if you have a batch size of 64， this will be 64 elements there。

 then the height and the width of the image， and then channels。Okay， this is an ordering。

 this is sort of a standard way of ordering it channels is you know the number of the input image we usually have way have three channels。

 is a color image， but it could have other amounts of channels as well。

Now this is something known as NHWC format， if you've seen sort of ordering attendances before。

 you may have seen things like this before。And you may also know that there are alternatives right we can actually order things in other ways too。

 We could order them in you know batches sort of first is kind of always a standard and kind want to with each other。

 but actually pitorrch as a library default to actually the NCHW format。

 which means that you first have batches in memory then channels then height then with So P actually uses this NwH format and I kind of you know I'm opinionated here。

 but I kind of want to say that that's the wrong format。 as we'll see in a second。

 the way you implement these operations because they are matrix multiplies where of it's natural to have the channel dimension as the last dimension I would argue that NHwc is the right order for storing images and the one that Pitor is the wrong order。

 It's very rare that I disagree with pitorrches choices in their design architecture。

 but here I really disagree with it。 I really think that。😊。



![](img/0932df05d90d8e157333d6981e19c846_8.png)

toring them in this way as we're going to for for needle makes a lot more sense and and just makes much more sense in terms of the operations that are actually done in terms of the conversion to each multiplication。

 it's much much easier this way。 I know there are some advantages also for the way the P does it usually actually think like the batch storm operators or faster that way。

 But I'd rather specialize for the convolutional operators personally。

 So we're going to store all are， we're going think of all our inputs as being four dimensionmenal tensors stored as first the batches and the first dimension than height than width indexing over the sort of the where you are in the in the。

😊，In the image， then where you are in the in the in the where you are in the y direction。

 where you are in X direction and then then where you are in the channels。 Okay。

 so that's gonna be our format for how we store images。

The next sort of question is how we store store our kernel weights。

 How do we store our filters And here again， we have two kernel size by kernel size dimensions plus in channels plus out channels And so the way we're gonna do it here is actually exactly by storing it by first dimensions is gonna be again is the 40 tensor with the first dimension being indexing over the kernel dimensions。

 second one indexing over the kernel size then in channels then output channels so we're going to store these as four tensors ranked four tensors in this order Again。

 this is not how pytor does things again， I think they are wrong for doing it the way they're doing it。

 but you know they made these decisions and they store actually in the order of out channels by in channels by kernel size by kernel size。

 but you know that's just like we have to deal with what pythtor decisions and so let me just like talk for a second about about what I mean by de ordering going back to my picture here So what I mean by the ordering is that you know we have our weights for。

😊，In this and I'm actually going to erase this because even though I talked before about them being C out by C。

 I'm actually going to write CN by C out now that's how we'll do it today in this lecture we wrote sort of mathematically in a different form last time but let's not worry about that too much。

😊，What I mean is we have some filter weights right， we have some weights here which are stored。

 the first index would be sort of call this I don't know I right which indexes sort of where we are in the filters。

 that would be say you know I is one then we are here。

And then there's a J term which indexes sort of so this is I then we have the J term it indexes how far we are kind of in that direction in our filter and so this I guess would be j equals I equals 1 and j equals0 here and then we have remember each one of these sort of boxes here filters here you should think of as a matrix So of course we're gonna to have an index if we want to find a single value we'd have an index into the matrix2 and so this would be the index of I guess I'd call it like I don't use the word well。

😊，I've already used the term K， there's many too many indexes here。

 plus you see this like S and R to index over which location we're in so this would be if you blow up one of these things right so if you take one of these things and kind of blow it up into a big matrix。

 this would be kind of where we are in the S row and the J and the R column or something like this sub。

😊，Onent off the side there， the S row and the art column or something like that。

So that's what I mean by indexing them， it means that these things are great big tensors and you have to index the individual elements if you want a single scar value。

 but really it's much better to think except for the very first version we do。

 it's much better to think about these things as tensors and we'll talk about how that actually makes things life simpler in the big picture。

😊。

![](img/0932df05d90d8e157333d6981e19c846_10.png)

Okay， so let's get back to the implementation now we're going to implement our images in this format here and are going to implement our weights in this format here。

So that's going to be how we store basically the arrays。

 the multidimensional tensors or multi dimensionmensional arrays。

 the actual storage in memory of our input image and our output。All right。

 so now let's talk about the different ways we can go about implementing convolutions。

And the first these is kind of the obvious one。 We can do it just as with a for loop。

 So we can implement a convolution as a for loop。 I mean。

 we have to index over all the batches it's quite deep over， I shouldn't say four loop。

 many four loop， right end's over the batches then over the channels then over the know each channel。

 It to you know go over each position and convol with each location in the filter。

 but you can do that。 It ends up being like the deepest。

 I think it's like a seven layer deep or something like that。 four loop， which is quite， quite。

 you know， deep for the four loops I've ever implemented。 but but we can do it。😊。



![](img/0932df05d90d8e157333d6981e19c846_12.png)

Before we do that， though， I'm gonna， I'm gonna do something that all of you should do first before you design many of these things which is I'm gonna to write kind of a reference solution that we want to target。

 We want to be making sure that our implementation are correct。

 And so we're gonna use a reference solution to sort of to sort of verify that our implementation are。

 in fact， correct。 Now， if you're implementing something from brand new from scratch， right。

 So you're implementing the librarys or some operation that's never been done before。😊。

There's this is tricky right you have to sort of you're writing it for the first time to make your own reference implementation。

 But here we sort of have the benefit that convolutions already exist。

 There's lots of convolutions out there already。 And so what we can do is we can actually leverage existing libraries to sort of give us a reference implementation of convolutions and we're gonna do this and in fact。

 in this lecture， we're gonna to implement these things。

 we're going to use piytorrch as as a reference implementation for our our convolutions。 Now。

 as I said before， know the goal of this class in some sense is to write everything yourself to not use pytorrch。

 But when you're writing test cases， initial test cases， it's really valuable。

 these things do exist and you're free to use things like pytorrch as reference solutions to make sure that your code is doing the correct thing this does not work in all cases。

 but at this point， I mean even if you want to create if you actually want to create a new deep learning framework right now。

 you could do that so you could just use Ptorch as a reference solution and so in fact。

 we're gonna do this。😊，All right， so the first thing we're going to do is we're going to implement a reference solution in Piytorrch。

 so I'm going to implement， I'm going to import piyTtorch and I implement torch the neural network components。

 and I'm going to define the convolution reference。

 which is going to take my input image Z and some filter weights， the call weight。😊，Okay。

 so the first thing they have to do in a reference limitation is convert this from pie torches or from our。

 you know， nice good format， which is。Batch height width channel to pi torches because we're gonna do our convolutions in Ptorch has to convert from our nice N H WC to pitorrches。

 horrible N H N CW H format。 Okay， so let's， let's do like N H or N。 Yeah。

 So so we're forming our tensors in in this nice format。

 And we're gonna convert to Pi torches annoying format。

 So we're gonna find this know Z torch is gonna be torch do tensor。😊。



![](img/0932df05d90d8e157333d6981e19c846_14.png)

I'm gonna create a copy of it so I don't know accidentally erase memory or so we're gonna to do our influence as I should mention in nuumpy of course you could do it in the ND array and you will do it for the homework。

 but given that I'm not going to give away too much here in lecture I'm going to do it in in Numpy and you will so we'll represent our inputs to this function here in Ny so we convert to a tensor and then we're gonna to permute it to have the correct format so it would be the first dimension would be the batch then the channels then the height and the width okay。

😊，So that that converts to high torch's internal format now because this channel 3 is the in our notation is the channels and we want to put that first and similar for all the rest Okay and I got to the same for the Ws。

 So I have to convert Ws to to the in channel out channel。😊，Format， so then permit this to be。 okay。

 so I' just， I'll just write it here what I'm doing。 So， so art。

Input channel would be kernel size by kernel size by input channels by output channels。

 and pi torches is O is output input kernel kernel。 And so again， I need the that would be。

 So I want first。3，And I think actually it flips the order of these things too。 So I want actually 3。

2，0，1 for mine。Sorry， I know I need I need input， right， so I need input。

Output and torch uses output input， I believe， I don't know why。

That seemed like the wrong decision again， but you know they're doing it that way。 Okay。

 so give us a little bit more space here and then now we're going to call our convolution so we're going to call out and we'll use this like and then dot functional call here hopefully I have that right I haven't loaded it yet Com2D。

😊。

![](img/0932df05d90d8e157333d6981e19c846_16.png)

functionalal。com 2D。And I'm going call Z torch and the torch。



![](img/0932df05d90d8e157333d6981e19c846_18.png)

And I'll return I want to return a permuted version of it sort of back in our format。

 I'm going to return out do permute， and I want to convert it back to this format here。

 So permute just swaps the axes。 It's like the permute function or the swap axes function that you have in numpy and the forget what we call it inD array。

 but I think it's either permute or swap axes， and this is going to undo that one so this is going to be 0。

2，3，1。And then we want to convert to a numpy array。

 and I'm going to go to contiguous that contains a contiguous array。

 You have to do that before you call nuy sometimes but I'm going to do it like that。

 Okay and that should be our our function there。 Let's test it out。

 Let's create some some matrices here in Pytorrch or in sorry a nuy So let's import nuy yet。

 I didn an import nuy。😊。

![](img/0932df05d90d8e157333d6981e19c846_20.png)

Should not do it up here。Okay， and then let's say that Z equals NP dot random that random n。

 Let's do a batch size 10，32 by 32 images with8 channels。 Okay， and let's make our kernel。Let's see。

 It's。Let's say it's 3 by3 mapping from 8 channels to 16 channels。 Okay， and then out is going to be。

 let's make a con reference Z W。 And let's just print what the shape is。



![](img/0932df05d90d8e157333d6981e19c846_22.png)

OkaySo that's actually properly。 I wonder whys there's some an N pack there that couldn't be initialized。

 and this is actually proper。 So notice we actually didn't implement any padding here。

 So we just have kind of a convolution without padding。

 It turns out for our actual implementation what you will do if you want to add padding just for simplicity we could do it differently if we wanted。

 but we'll actually explicitly form the padding。 it's given that we as we see we're gonna be copying memory a fair amount anyway in these implementations。

 It doesn't matter too much to have padding。 So we're gonna do sort of paddingfr convolutions here。

 And that means that the output size is because we have a three by3 kernel。

 we are convolving a 32 by 32 image and so the output size is gonna be 30 by 30 because you lose one pixel off each side of the image。

😊。

![](img/0932df05d90d8e157333d6981e19c846_24.png)

![](img/0932df05d90d8e157333d6981e19c846_25.png)

Alright， so now to compare， so this this is sort of， you， this is an implementational convolution。

 but of course we're cheating。 We didn't implement anything。

 We just called pytorch after some after some permutations here。

 let's implement our own version of this convolution。

 Okay so lets let's do what I'll call like like the naive convolution here。

 which is simplest possible convolutional operator you could have which just does this with a whole bunch of four loops。

 And I said I think this is like the biggest number of four loops I've ever had in a and a function before。

 All right， so the first thing we'll do is let's let's get our sizes。

 So it's sort of helpful to have these things all sizes。

 So I'll call this as Z dot shape should be our batch size height width and input channel sizes the shape of Z。

 the kernel size。 And let's assume that the kernel size are the same You could have different size kernels。

 but everyone needs to the same test kernel anyway。 So that's all you have to implement。😊。



![](img/0932df05d90d8e157333d6981e19c846_27.png)

![](img/0932df05d90d8e157333d6981e19c846_28.png)

![](img/0932df05d90d8e157333d6981e19c846_29.png)

And so the kernel size kernel size Cm we already know， and so C out is equal to weight that shape。



![](img/0932df05d90d8e157333d6981e19c846_31.png)

And now let's go through the actual implementation of convolution。

So the first thing we're going to do is we're going to implement。

 we're going to initialize our output， and that's going to be a bunch of zeros which are of size。

 well with specific the size what this is going to be。

 well it's going to be number of batches is the first dimension in the size。ふ。😊。

And then the height of the new kernel is going to be H， but it's not H itself， right。

 because we're shrinking the kernel。 So rather we're shrinking the size of the image。

And so every point we shrink it by on each side， we shrink it by sort of like， you know。

K over 2 or K minus-1 over2。 And so the the end effect is that the actual size。

 the output will be h minus the kernel size plus1。 So the kernel size is3。

 that means to subtract two off of everything。 kernel size is 5。

 that means to subtract four off of everything etc ceter。

 right And so this is the this is the resulting size of our kernel。😊。

And let's do see out because the number of channels out。 Okay。

 now let's do sort of the largest for loop you've ever seen in a in a real function。

 And we're also doing it in Pythons is gonna to be， as you might imagine。

 like the slowest possible implementation you can you can ever really imagine of these things let's go ahead and do it Okay。

 so so what is a convolution too。 Well， first of all， let's just iterate over the。😊。

The examples in our mini batch and then let's iterate over the the output So so the input and the output channels。

 all right， so let's implement iterate over for C in in the range。CN呢。Then for C out。In range C out。

 Now we're input now what we're going do now we have a sort of single channel， single input channel。

 a single output channel。 Now we actually run a convolution， So what what does the convolution do。

 Well， it moves sort of the center position over the entire span of the image， right。

 So we have to sort of iterate over X and y in the range of allowable outputs。 Allright。

 so let's first iterate over y and that would y from you0 to the height of the output image。😊。

And let's iterate over x in the range of。Mus K to1， the range of the output image。 Okay。

 so now we're implementing over like the the output position。

 and then we implement over the position in the kernel matrix itself， right。

 so that's the next thing we index over is like where the kernel is as well。 And this。

 this is now a bit sort of tricky exactly where where it goes here。 But， but I。

 but if you sort of look at all your your innices correctly here。😊。

The what you would do is you would implement over it from I in range K。

 So that influence over like where in the filter were're convuling the image and then J in range K。

 And now you set the output image。 So you set the output at this location， know， this mini batch。

 this X， this Y channel C out plus equals， well， the image of that location， but not that location。

 actually， that location。Plus sort of the input that we want， right， the actual input in our image。

 and so the input in our image that we want to get was this be the same thing。

 but it's shifted over by I and by J right so x plus J x plus and then C in。

And then times the weights， well that would be the weights would be the IJ location in the weights because that's sort of the kernel position and then I should see in and see out。

 I'm going to run into myself here Okay， I think that is everything。I think that's our function。

 that's our big prototype， but I didn't make any mistakes there。あ what'。

I think I actually have the code to test this down。 So let's make out two out two here。



![](img/0932df05d90d8e157333d6981e19c846_33.png)

Equal to。The naive convolution of Z and W。And let's print out。The difference between out minus out 2。



![](img/0932df05d90d8e157333d6981e19c846_35.png)

What would I do？What I said， wait， wait。

![](img/0932df05d90d8e157333d6981e19c846_37.png)

![](img/0932df05d90d8e157333d6981e19c846_38.png)

And not surprisingly this take some time because that's a whole lot of four loops for on the handle。

 let's see it's one， two， three， oh， his price to return。That's also a problem。Alright。

 so it's how many four loops， It's 1，2，3，4，5，6，7，7 layers deep4 loop。 But we are in fact。

 implementing the convolution correctly。 and you know， we have the correct convolution。

 So I mean what I'm doing if I'm printing the difference out was our was the output we got from the reference solution and out two was what the answer we got from our sort of naive for loop implementation。

 and that is that they are the same right So there's no difference between the two implementing convolutions correctly。

 we can look at know out two do shape and stuff like that it's going to be of course the same size as what we want as out shape。

 otherwise the call before would not work。 But this is not a very good this is not a very good way of doing things So I mean sort of look at the time of these things。

 So whats the time it takes to run naive between Z and W。😊。



![](img/0932df05d90d8e157333d6981e19c846_40.png)

![](img/0932df05d90d8e157333d6981e19c846_41.png)

![](img/0932df05d90d8e157333d6981e19c846_42.png)

![](img/0932df05d90d8e157333d6981e19c846_43.png)

![](img/0932df05d90d8e157333d6981e19c846_44.png)

![](img/0932df05d90d8e157333d6981e19c846_45.png)

Let' let's just look at that and while let's running all right the codes at time and I'll actually use time it time it runs a few different iterations there took seven seconds to do let's run with pitorch calls dominated the time by like the overhead and calling them so it'll actually vary a lot when you call it each time So let's actually called timeit let's call the reference implementation of these two it's gonna run a bunch of times now it's actually running like hundreds of times but on average it takes very very little time to run this on less than a microsecond to run these things and so this is I mean this is not what you want to do so we're doing a very very long call and this is not that large of an image here its only batchche of10032 32 by8 took a seven seconds to do one convolution whereas ptorch not surprisingly still on CPU but not surprisingly takes less than a millisecond to run that So not exactly not exactly fast enough for for our implementation there Of course。



![](img/0932df05d90d8e157333d6981e19c846_47.png)

![](img/0932df05d90d8e157333d6981e19c846_48.png)

![](img/0932df05d90d8e157333d6981e19c846_49.png)

![](img/0932df05d90d8e157333d6981e19c846_50.png)

![](img/0932df05d90d8e157333d6981e19c846_51.png)

![](img/0932df05d90d8e157333d6981e19c846_52.png)

Surprise， you know， doing these things as a seven layer deep4 loop in Python is not maybe the best idea to do。



![](img/0932df05d90d8e157333d6981e19c846_54.png)

Okay， so let's move on now and do a much better version of compvolation。

 which is actually going to be almost as good as our as our final version。

 but which is going to but which is going to be in some sense like a。

I would say sort of like a the still the wrong way of doing it， right。

 So it's still going to involve four loops in Python and sort of， you know， too many calls in your。

 in your。And your on my differentiation tool， if you did it all on my differentiation library。

 so it's a reasonable doing convolutions actually， but especially as your filter sizeizers get too big。

 this winds up being not that efficient。Alright， so let me talk now about convolutions as matrix multiplication。

 So if you remember from before， we had before， we had this notion that a convolution kind of was a matrix multiplication。

 right， So you could think of the filters themselves。

 the filter positions as let me go back to my to my。😊，To my iPad here for a second， it's not working。



![](img/0932df05d90d8e157333d6981e19c846_56.png)

Let's go okay， with these filter positions that were， you know。

 each kind of a mess of a figure now let me erasse this here。

The the filter positions in our image in our compositionvolutional filter。

 they were all themselves matrices right and we multiply and the way to think about these things we're multiplying this matrix by the vectors in our image Okay so right so our images our vectors and we're taking each of those vectors。

 we're multiplying it by that matrix right that was the way of thinking about where we this each cell here each each component in our filter was a matrix。

😊，All right， so what this means though， is that if we were to think about the simplest possible case where our filter was a one by one filter right。

 so suppose k was equal to one in this case， doing a convolution， a one by one convolution。

Is just a matrix multiply Okay， so that's actually very simple。 It's just a matrix multiplication。

 that's all a convolution is right And so let's go back and let's show how to implement a convolution as a matrix multiplication for a particular for a 1 d convolution so let's take our weights1。

😊。

![](img/0932df05d90d8e157333d6981e19c846_58.png)

![](img/0932df05d90d8e157333d6981e19c846_59.png)

Let's make sort of weights1。 I guesss call it like W1。 looks our old was W。 So let's make another W。

 let's do this and peanut random that ran in a one by one convolutional filter。

 but still8 input channels and 16 output channels。 So this is in other words， just a 8 by 16 matrix。

 We is putting it in the  one，1 location of our random matrix so that we can of our filter matrix so that we can actually compute this。

😊。

![](img/0932df05d90d8e157333d6981e19c846_61.png)

So now let's look at what comm reference， I mean this this is still。

 we can still input this into our into our。

![](img/0932df05d90d8e157333d6981e19c846_63.png)

And maybe it'll print out this the shape it is， so it properly sort of produces a matrix。

 note that there's no change in size here because with a one by one filter you don't miss any other elements here you still keep all the elements。

So what this means though， is that in this setting， we can implement。

Convolutions with big quotes here very simply right。

 It's just gonna equal to Z times matrix multiply W。

 This won't quite work because that's not a matrix。 So you have to actually look at the Ww。

 the 11 entry there。 So I just say out it's2 the 11 entry there。

 and let's then look at the difference between。😊，The out and out to。



![](img/0932df05d90d8e157333d6981e19c846_65.png)

And thisOkay again， it's zero， so you know， we are properly implementing a convolution。



![](img/0932df05d90d8e157333d6981e19c846_67.png)

Okay， and as you sort of imagine， you know w like these are all the correct sizes right So W10，0。

 that's just going to be that's just going to be an8 by 16 matrix and multiplying it by this is just a matrix product。

 Now this is actually exploiting a property that's very convenient in nuy。

 which is that when you multiply a matrix here， a tensor here。

 so remember z is a rank four tensor by a matrix， it treats all the leading dimensions just sort of as as if they were sort of more and more rows in this matrix。

 Okay so theses are rank four tensor， but what it does is it basically treats z as a matrix that is you know all the first three dimensions by the last dimension does that as a matrix multiply and then reshapes it accordingly but we could do it explicitly here too right so this could all be done。

😊。

![](img/0932df05d90d8e157333d6981e19c846_69.png)

![](img/0932df05d90d8e157333d6981e19c846_70.png)

![](img/0932df05d90d8e157333d6981e19c846_71.png)

Explicitly as well。So we could， we could make this out and could sort of write if this is sort of too much cheating for you because we're sort of。

 you know， this is not a matrix and we're doing matrix multiplies。

 if you want to do sort of real matrix multiplies， what you can do is you can do something like this。

 you could do like Z dot reshape and something like the nice call here would be something like negative 1。

8。 That is a nice feature that I have in in。😊，And nu lets you sort of take all the leading dimensions of。

 well， let me just do this。 So look at z's shape first。 z is a 10 by 32 by 32 by 32。

 10 by 32 by 32 by 8 tensor and this now if if you do this。

 this would be a sort of 10 times 32 times 32 by8 dimensional matrix Okay so we can take this matrix and we can multiply this one is now a matrix like like a real matrix multiply it by w10。

0 Okay and then that's our answer。 but then we need to reshape it back into the size of z。

 so we can reshape this basically as z1 dot shape or z Z shape 0 z do。😊。



![](img/0932df05d90d8e157333d6981e19c846_73.png)

![](img/0932df05d90d8e157333d6981e19c846_74.png)

sh。Shape1。Z dot shape。I mean whatever let me just let me just actually since I I use the actual sizes there before so let me just do this so this would be 10 by 32 by 32 by 8 sorry by 16 because I'm multi I get 16 channels in the output and I could just set out two or else make it out of three equals that。

😊，Right， and you know， I can do the same thing here and look at the。The norm difference between。呃。Os。

Minus out three and that is going to be zero to。 Okay， so that is one by one convolutions， of course。

 one by one convol are not very interesting。

![](img/0932df05d90d8e157333d6981e19c846_76.png)

But the very cool thing here is what you can do， which you can sort of leverage by doing this is you can actually use this same formula or the same strategy to do normal convolutions not with just one niche multiplication here but with K by K of them because what we can do is we can take basically each location in W do a matrix multiply between that and the original image。

 the original image I should mention sort of like the proper subset of the original image we'll sort of see that in a second and then just add all those up and that also becomes a valid convolution。

😊。

![](img/0932df05d90d8e157333d6981e19c846_78.png)

So let's see how this works a little bit。 Okay， so let let's find another function。

Which is going to be convolution with matrix multiply and let's again have C and weight and let me just copy up here what I had before。

😊。

![](img/0932df05d90d8e157333d6981e19c846_80.png)

Let's copy this because this is all the same。 Nothing here changes。 We're still creating， you know。

 we want still want the same sizes， and then we're going to。



![](img/0932df05d90d8e157333d6981e19c846_82.png)

![](img/0932df05d90d8e157333d6981e19c846_83.png)

Create an output which is the same size。 but now we can actually do this a much we can do the whole sort of without instead of you know seven layers deep four loops。

 we can actually just do a two layer deep for loops。

 so we're going do is we're going to implement just just iterate over the locations in the kernel matrix and then use a matrix multiply to do everything else。

😊，So for J for sorry for I in range K and then for J in range K， we're going to add the output。😊。

It's going to be plus equal the input matrix。 So it's going to be like the the whole Z here。

 So it's going to be Z， all the batches， all the elements in the batch。 We'll deal with these next。

 Let's do those two next。 but all the all the output channels also times。😊。

The weight at location I J， which again， is a matrix， right。

 So we're multiplying kind of that portion of the image by the corresponding weight。

 But this portion here is actually quite important。 We need to figure out sort of where to put this。

 And what we have to do here is that sort of shift the image。

 shift the location we're multiplying with properly， such that we're， in fact。

 kind of sing our filter over the whole image。 And so what this would be is that rather than sort of the whole image here。

 which which wouldn't work right， that would just be like。😊。

Adding up all these multiplications applied to the same locations as the image。

 We have to sort of shift where we're， where we're compving things with。

 So this is actually going to be starting at position I in the height。Down to， well。

 it's going to be I plus H minus k plus 1。 And this one's similar going to be to J to J plus W minus K plus 1。

 And that's， that's another return。Turn it。

![](img/0932df05d90d8e157333d6981e19c846_85.png)

And this is now our new match multiplication carried out with just two layers deep of a for loop where we're doing kind of the hard work using a batch matrix multiply。

 Okay so let's actually do the same thing as before。

 let's let's make some I'm going to make them a bit bigger because now we can actually I couldn't have made it this big before。

 it would have taken too long to actually run， but I' make it a batch as 100 now just to have a bit more。

 just take it a bit longer to run all these things。😊。

Our filter is going to be 8 by 16 and we're going to say out equals。



![](img/0932df05d90d8e157333d6981e19c846_87.png)

![](img/0932df05d90d8e157333d6981e19c846_88.png)

Com reference of Z and W and out2 is going to be comm matrix multiply between Z and W。

 And then we're going to look at the。Difference between out and out W out minus out W out2。

s what I do here。😊。

![](img/0932df05d90d8e157333d6981e19c846_90.png)

Just misspelled Nor。

![](img/0932df05d90d8e157333d6981e19c846_92.png)

Okay， and it's not quite zero， but that's zero numerically right。

 so it's essentially those are in fact， again giving the same solution to numerical precision and doing it here with two loops。

 two， four loops instead of a whole lot more four loops。



![](img/0932df05d90d8e157333d6981e19c846_94.png)

![](img/0932df05d90d8e157333d6981e19c846_95.png)

Okay， so that is actually already a totally reasonable way of doing matrix multiplication and you in fact could just probably stop or sorry doing convolutions。

 Vm multiplication， you know with one little for loop here or two little for loops。

 but I mean these three by three filters， this is you know a loopus size9 and in pytorch。

 maybe it's not that bad， maybe it's probably fine。😊。



![](img/0932df05d90d8e157333d6981e19c846_97.png)

![](img/0932df05d90d8e157333d6981e19c846_98.png)

嗯。But for the sake of both understanding how these things work and honestly。

 as an illustration of the single coolest call that Numpy has。

 we're going to talk about how to do this kind of in the proper way。

 and we're going to do it with this into call kind of kind of routine。Alright。

 so what do I mean by that， So you remember what last time I talked about this。

 I talked about last time this。This way of sort of writing matrix multiplies or writing convolutions in terms of matrix multiplies right and so I sort of said that okay。

 we have a convolution， we have like a you know element5 matrix I'm going to get this wrong here， x2。

 x3， x4。

![](img/0932df05d90d8e157333d6981e19c846_100.png)

5， I guess I had zeros before， so let me just。Ese those。

 but you can look back in the previous lecture for this。😊。

I'll put the zeros there if I want to convolve it with like a。3 dimensional filter just in 1 d。

 right I could do this by basically writing this as some matrix that containss kind of all the versions that we have of this matrix of this sort of input matrix shifted over by the proper amount。

 so it had you know0 x1 x2， then x1， x2， x3， x2， x3， x 4， et cetera。

 all just multiplied by a big vector。Of this And the important thing to note is that this all still works when when these are replaced and no longer are no longer just images or are no longer just sort of scalarrs。

 but are now matrices and vectors So if I can somehow shape my matrix into something like this。

 I can actually perform the convolution。 and then maybe stack my weights。

 And it's a little bit more complex in two dimensions， of course。

 but it's not that much more complex。 and we'll see in one second how this actually works。

Then I can actually do sort of my whole convolution in one go just as one big matrix multiplication。

 and this is called an this is called the M to call operation。 So M to call M is written badly M。😊。

To call and we want to be able to implement this in code。And now it might seem like okay， that's。

 that's great。 this， this all makes sense here。 But I mean， writing this matrix。

 that's going to require just as much effort as that forward loop before。

 I have to I have to iterate over all my positions。

 all everything like this and copy these and create a new matrix of the same size。

 That seems like a paint。😊，But it turns out there's just a beautiful。

 beautiful way to write this whole thing， this whole construction this matrix in like five lines of Python code that' is actually very fast because we're using them p the whole time。

 and this uses this again this amazing function called the asstred function。

So to introduce as stride as a， as again。 So I think it's probably my favorite nuy function that I。

 I guess can you have favorite nupy functions。 I think I think I have a favorite nu function。😊。



![](img/0932df05d90d8e157333d6981e19c846_102.png)

![](img/0932df05d90d8e157333d6981e19c846_103.png)

Okay， to introduce the asstred call， I'm going to actually go start with something that is not related to convolutions at all。

 but which is actually related to what we saw a few lectures ago when it came to efficient matrix multiplication。

😊。

![](img/0932df05d90d8e157333d6981e19c846_105.png)

So you remember we typically stored these matrices for you know an M by n matrix right we stored this in what we called row matrix format。

 meaning that you know there were first all like we stored the last dimension contiguously then the dimension after that and if you have more dimensions you sort of go more and more and more but really what was happening is that we were used storing this as a contiguous array and then using strides in order to say like how much we increment our memory for each successive dimension。

And that's basically how we store these things in memory。

And if you remember what mentioned separately， he made this point that if we have sort of matrices stored not just like this。

 but like this in some tiled format， then you can actually multiplication more efficiently because you can leverage essentially cash locality to do batch operations and not just casuality。

 but also be sort of vector operations， even on a GPU and certainly even on a CPU and certainly not a GPU to do this much more efficiently So this is sort of this notion of tiling matrices to do the operations like like multiplication more efficiently。

 but you might sort of rightly ask like how do we get a matrix in this kind of form。 I mean。

 there're usually someone handdo a matrix。 it'll be in this form。

 I guess we could like write our own routine to copy these things all over。

 but that seems like of a waste。 It turns out it is a away。 So you don't have to actually do this。😊。



![](img/0932df05d90d8e157333d6981e19c846_107.png)

So there actually are ways to use this amazing call called the there's this this call this call here。

 So it's the NP。lib strideide tricks do asstred。 And if you can't tell from that name。

 Nmpie does not want using this function it's my best guess of why it's named like several layers deep in in thempie internals here。

 But it's like once you know how these things are stored。

 it's the most beautiful function and you can implement all these things kind of just so quickly and so efficiently with them。

😊。

![](img/0932df05d90d8e157333d6981e19c846_109.png)

So we're going to start by talking about how we can implement not convolutions。

 we'll get that in a second， but how we can implement a routine that converts our data from this format to this format using the as strideed call。



![](img/0932df05d90d8e157333d6981e19c846_111.png)

![](img/0932df05d90d8e157333d6981e19c846_112.png)

Okay， so and we're going gonna use two calls， we're going to use the assterta call。

 but then we're also going to use the contiguous array call。

 So I'm going to introduce this kind of kind of bit by bit here。

 but we'll sort of go through it in some in some detail。

 So at a high level what asstr it does what the asster call does is it lets you take the memory of an array and refer to it as kind of the same array。

 but with different strides， you can kind of keep the same memory as it was before。

 but make it represent an array that consists of different stride like like different strides in some sense。

 So you take the same memory convert to a new array but that new array has different strides。

 And so because of this， it actually represents a different tensor。

 different multidimensional array essentially。😊。

![](img/0932df05d90d8e157333d6981e19c846_114.png)

Okay， so let's I mean that's that's that's a little bit opaque what I'm saying there let me actually give an example of what I mean by this so let's generate a matrix here where's my cursor。

😊，呃。Where am I。There I am okay， so lets let's start out by just implementing， let's。

 let's say like n equals6 here and a equals NP dot a range。

 this is just going to be arranged from 0 to 6， I'm also going to make the float 32 type just I guess NP do float 32。

嗯。And I'm gonna reshape it to be an n by N matrix。 Okay， and then let's just look at what a is。 Okay。

 So A is just a。A range。

![](img/0932df05d90d8e157333d6981e19c846_116.png)

Okay， so A is a 2D array that has。The number is 0 through 35。Okay， so that is that's that。

Let's now start talking about how we go and actually look at how this memory is stored internally。

 how this data is stored internally in memory。

![](img/0932df05d90d8e157333d6981e19c846_118.png)

This data here because we such it as sort of a because A it's in row major format。

 but also because we constructed it as just as an array and then reshaped it。

This data here is gonna be laid out contiguously in memory。

 So the memory itself will contain the numbers0 through through 35。

 And it actually is not that trivial to get the internal memory that nu like the internal memory storage that Ny uses N。

 again， same with astroed Nmp every step tries to prevent you from knowing how the data stored internally。

 So there may be another way of doing this。 I found this way a while ago。

 and I've always just used it。 it was this call here。😊。



![](img/0932df05d90d8e157333d6981e19c846_120.png)

![](img/0932df05d90d8e157333d6981e19c846_121.png)

It is the the I use the C types library， which is again how you interface with C code so it naturally has the routines to do that。

 but what this does we can print this call I'm going to call I'm going to create like a new buffer from the data。

😊。

![](img/0932df05d90d8e157333d6981e19c846_123.png)

![](img/0932df05d90d8e157333d6981e19c846_124.png)

And I'm going to。Call C types dot string at A dot C types dot data。 and then a dot n bytes。 Okay。

 and so this creates like a C string that corresponds to the actual underlying data of the of the nupy right。

 If you just look at this data， for example， it won't， it won't， it'll actually rearrange it。

 as we'll see in a second。 and then you have to also change， I think the the， the the data type。

 So I think you need to say from the in the buffer call itself。 you need to say that this buffer。😊。

I want the D type to be equal to a dot D type and the count， which is sort of how many。

Types how many locations that you read would be A do size that's the number that's the size of a so I did this wrong。

 I did something wrong here。😊。

![](img/0932df05d90d8e157333d6981e19c846_126.png)

D type a D type。Oh， this is。

![](img/0932df05d90d8e157333d6981e19c846_128.png)

There we go， okay， so that sort of shows that this， you know。I mean。

 this is not going to be so surprising right now， it only be surprising when we see what happens differently。

 this is sort of how we access the data so again this is written out a bit more in in the notebook。

 but this is sort of how things are sort internally。😊。



![](img/0932df05d90d8e157333d6981e19c846_130.png)

![](img/0932df05d90d8e157333d6981e19c846_131.png)

![](img/0932df05d90d8e157333d6981e19c846_132.png)

The other important element to look at is the strides property of the array。

 So this array right would have a remember strides are indicate the number of sort of locations in memory you move with each consecutive element。

 right， So here you know， we have a2D array where moving one element in sort of the last dimension moves you over one location in memory。

 right So go from here to here， you increment by one unit。

 which in this case is4 bys and to increment from here to here。😊。



![](img/0932df05d90d8e157333d6981e19c846_134.png)

![](img/0932df05d90d8e157333d6981e19c846_135.png)

You increment by six units。

![](img/0932df05d90d8e157333d6981e19c846_137.png)

Right， so the way you can find that out in in。In nuumps by looking at the strides operator and Ny is a weird convention that strides actually is a stored in terms of the number of bytes。

 not in terms of the actual sort of number of elements。

 but just kind of non-standard ND array will use I think Pytorrch uses the number of elements。

 ND array that you're implementing we'll also use the number of elements not the number of bytes。

 but it's a pretty simple because we use float 32 and we're all going to use float 32 here。

 you just divide kind of by4 to get kind of the normal strides for nuumpy。



![](img/0932df05d90d8e157333d6981e19c846_139.png)

Okay， so， so let's now do this big thing and let's figure out how to convert this matrix here。

To one that is tiled in this form。 Okay， so what I mean by that is we want to convert this matrix here。



![](img/0932df05d90d8e157333d6981e19c846_141.png)

![](img/0932df05d90d8e157333d6981e19c846_142.png)

Which is is sort of a two by。

![](img/0932df05d90d8e157333d6981e19c846_144.png)

6ix by6 matrix， we want to convert that to a matrix looks like this， and we'll use a tile size of2。

 so we want to convert it from a6 by6 matrix to a or a three by three by two by2 tensor。



![](img/0932df05d90d8e157333d6981e19c846_146.png)

Okay， now if we just did that， Okay， so let's so if we just did that。

 if we just took a and did this then said reshape3 by3。By two by two。

 this is actually not what we want， right because the first sort of tile here is sort of the first tile contiguously in memory。

 right it would be 0，1，2，3。

![](img/0932df05d90d8e157333d6981e19c846_148.png)

But that's not actually the first tile here， right the first tile is 0167。second tile is 2，3，8，9。

 right， It would be like this term and this term， I can't highlight multiple lines here。

 but like the first tile would be these things here。



![](img/0932df05d90d8e157333d6981e19c846_150.png)

So just reshape enough does not actually give us what we want， doesn't really do what we want。



![](img/0932df05d90d8e157333d6981e19c846_152.png)

So we have to do something else。😊，So the question is。

 how can we what we're going to do is we're going to use the as strided call to create a new version of a that is the proper size and which is sort of has the proper strides in order to represent a proper tiling of that matrix here。



![](img/0932df05d90d8e157333d6981e19c846_154.png)

![](img/0932df05d90d8e157333d6981e19c846_155.png)

Okay， so what do I mean by that？Here's where I' was going to get actually， you know。

 let me actually just even say。 And since this is a pain to do every time stride tricks as stride as or rather from。

Striide tricks import as strideed。Okay。From I oh， it's nuy。Okay， so we have our astra call。😊。

Let's use our asstr call on a and in particular here， we can kind of get help on this。

 So the arguments for asstred the first argument is the well the first I mean can pass is is the shape then the strides I don't ever worry about the subok and those sort of things and writeable actually don't know what those things do。

 but the important arguments here are the shape and the strides so I think this is actually best shown by example。

 So I'm going to run asstred on the matrix a where I'm going to pass as the shape， the shape we want。

 which is a three by3 by2 by two matrix and now is the important part。

 which we're going to pass the strides， I'm going to pass the strides。

 I'm going multi I'm going to pass this as an array we can do it as a couple two but I'm just new as an array so I can multiply it by4 so I can do the strides in terms of the normal unit And the question is for each of these dimensions。

 So now we're reshaping this as a rank for tensor and the question I want to ask u is what。😊。



![](img/0932df05d90d8e157333d6981e19c846_157.png)

![](img/0932df05d90d8e157333d6981e19c846_158.png)

![](img/0932df05d90d8e157333d6981e19c846_159.png)

What is the size that we need for the strides to get the tiling that we want？All right。

 so let me actually copy this maybe I'm going to copy this down here。

So this is right above our call here。

![](img/0932df05d90d8e157333d6981e19c846_161.png)

What strides do we want to make this the matrix we want Okay。

 so we want to lay it out and memory like this we want sort of these elements to be contiguous then these elements in sort of the first dimension should be this one。

 the next element should be dimension should be that one， then this one then this one etca。

 right and so as sort of a three by three by two by two。



![](img/0932df05d90d8e157333d6981e19c846_163.png)

Yeah， three by three by two by two， tensor。Our first dimension would increase from this location to this location here。

 right， Does that make sense， that mean we would basically our first。

 as we increment our first index。It should jump from this location to this location。

AllAnd what that means is our first stride value should be 12。Okay， so that' again。

 that's like the dimension of our first our first kind of skip dimension。

 how much we jump in the first dimension would be increment memory by 12。Okay。

 now let's talk about the next dimension。 so the next dimension is sort of indicates what cell we're in。

 So you know this is like the this here is like a two by two block and we want to jump。

 we want to jump to this next two by two block here。

 That means the start of our in memoryory from our first sort of you know from our first dimension per second dimension goes from here to here。

So our stride increment for the next dimension would be two because we jump over by two elements when we increment our next dimension。

Okay， what about the third dimension， Well， the third dimension is sort of the dimension within our tile。

 like the height dimension within our tile。 And so that would jump us from here to here。

In our third dimension， and so that would be a stride of equal to6 and finally the last stride value is our last dimension in our tile and that just goes from there to there。

 so that's just going to be equal to one。

![](img/0932df05d90d8e157333d6981e19c846_165.png)

All right。

![](img/0932df05d90d8e157333d6981e19c846_167.png)

So that's the whole call， actually， unless unless you make this maybe equal to B so B equals to this。

All right， and then let's actually print print B。Oh。Point B。Okay。

 and so the nice thing now is that B is also， I mean， first image me just print B dot shape。

 So B is also a 3 by3 by  two by two matrix。 But if you look at B， the elements of B。

 the first sort of element in B of the first sort of grouping in B is exactly this tile right here。

 Okay， I'm doing that， But this tile here and this tile there。 So B。😊。



![](img/0932df05d90d8e157333d6981e19c846_169.png)

![](img/0932df05d90d8e157333d6981e19c846_170.png)

Is a three by three by two by two tensor where the indexes properly correspond to sort of the tiling that we want。

But we're actually not done yet because the atroed call does not copy memory。 So B points to。

 in fact， the exact same memory as a。 I think you can even look at this。

 So if I change like B0 to be equal to I don't know5 or something。

 This should also change a 0 to be 5 also，'s I've messed that up some oh， B， unfortunately。

 I did destroy memory there， I I set the whole the whole index there to be that。 but。



![](img/0932df05d90d8e157333d6981e19c846_172.png)

![](img/0932df05d90d8e157333d6981e19c846_173.png)

![](img/0932df05d90d8e157333d6981e19c846_174.png)

I meant to say B0，0，0，0。 I meant to do this， but let me recreate these things。

 So A is that B is that。 If I set the the B last one。

 then then a also as a matrix would have this thing here。 So B points to the exact same memory as a。

 This is， by the way， why nupi doesn't want you doing some of these things。

 that actually that one happens even when you just copy memories normally matrix normally。

 so that one actually is pretty common。 But it's very weird because you can now sort of manipulate it in different ways and like set different elements of it So if I set like this element here。

 to equal to 5， that will change this element down here， thatll change this yeah。

 this one thatll change this one here。😊。

![](img/0932df05d90d8e157333d6981e19c846_176.png)

![](img/0932df05d90d8e157333d6981e19c846_177.png)

![](img/0932df05d90d8e157333d6981e19c846_178.png)

Okay， so let's put this back the way it was and do that。 So， and of course。

 if we look at sort of this， our fancy function here， where was my function to， Yeah。

 if we look at our our fancy function here on， on looking at。😊。



![](img/0932df05d90d8e157333d6981e19c846_180.png)

![](img/0932df05d90d8e157333d6981e19c846_181.png)

That sort of the， the memory of B。 What we'll see is that like nothing's， nothing's different。 So。

 so B， in fact， if I replace B here with all of this， B is the exact same memory。

 So it's gonna be still to the continuous， the continuous elements in memory。😊，Nothing changes okay。

 in order to actually change anything。We need to use what's called the as contiguous call。 Okay。

 so what this does And oh， and by the way， you can also look at B do strides here so it can look at like the strides of B and the strides of B。

 as you would imagine， correspond to the strides that we set in our asstric call。

 just multiplied by four。

![](img/0932df05d90d8e157333d6981e19c846_183.png)

Okay， so the problem here is that we haven't actually changed the layout in memory at all of our tensor。

 right it's still stored in this order， so we can't do things like actually more efficient mix publication and stuff like this right all we can do is just have a different view that Numpa knows about but which is not very helpful for us。

So if you want to actually change the matrix such that it's laid out in this order。

 so laid out in memory like 01，67， etc ceter， we need to use the as contiguous array call。

 so we call C， for example， equals NP do as contiguous array。



![](img/0932df05d90d8e157333d6981e19c846_185.png)

![](img/0932df05d90d8e157333d6981e19c846_186.png)

Calling B and now we can print this whole thing here。From。C， you probably have made this a function。

Oh， well。And what we see now is that this is now laid out in contiguous order according to this sort of。



![](img/0932df05d90d8e157333d6981e19c846_188.png)

3 by。The three by three by two tiling of our array right so you know the memory as as expected is01。

67 then 23 right then sort of like this block， this one， this one， this one， this one then this one。

 this one this one this one， etcter and this is actually a really convenient way of generating a tiled matrix from a normal matrix right there's no four loop is required here it's just this。

😊。

![](img/0932df05d90d8e157333d6981e19c846_190.png)

![](img/0932df05d90d8e157333d6981e19c846_191.png)

I mean， I guess if you debate it one thing would be NP has contiguous array for this thing。

 but it's sort of one line of numpy， you can create a tiled version of your array and that's very convenient。



![](img/0932df05d90d8e157333d6981e19c846_193.png)

![](img/0932df05d90d8e157333d6981e19c846_194.png)

Okay， so that actually is going be sort of all for this simple oh。

 and actually maybe before I did that though I should just mentioned that that it's also possible to。



![](img/0932df05d90d8e157333d6981e19c846_196.png)

To look at the strides。

![](img/0932df05d90d8e157333d6981e19c846_198.png)

Of C and the strides of C are contiguous in that the strides are sort of descending in order of the dimensions in the matrix right so they're not something weird like the strides of B。

 which we created ourselves as the astical， they are contiguous， they're contiguous things。



![](img/0932df05d90d8e157333d6981e19c846_200.png)

Okay， so， so that's actually all that we have now from the。

For of the simple example of as contiguous array， let's now talk about how we use this procedure to implement convolutions。

😊。

![](img/0932df05d90d8e157333d6981e19c846_202.png)

Okay， so first of all， again， we're going to remember。

 we're sort of our convolutions themselves are going to be these these sort of rank four tensors that make things kind of kind of annoying。

 Let's actually keep things simple， though， let's think about just doing a convolution with a sort of alpha 2D image with a 1 d with a1 d sorry with a 3 by3 filter。

 Okay so I'm going do like go at scalar convolutions again。

 though the nice thing here is that we willll be very， we'll be able to very easily。😊。



![](img/0932df05d90d8e157333d6981e19c846_204.png)

Extend this to the case of matrices and vectors and we'll see this in a second。



![](img/0932df05d90d8e157333d6981e19c846_206.png)

Okay， so here's our a matrix。 And now let's supposedly we want to convul it with a filter that looks like this。

 That's just some like 3 by three filters。 So let's make our  three by3 filter。's let's let's。

 let's give this all sort of as two dimensional things here。 So let's make this you know。

 a range 9 dot reshape。 I guess I'll make the D type。Flot 32 again。And reshape it to B3 by3。

And so here's our filter that we're going to con this with okay。



![](img/0932df05d90d8e157333d6981e19c846_208.png)

嗯ん。So recall。That what we want to do with this operation here。

 is we' going to take this set of weights and kind of slide it over every three by three combination here。

 Okay， so I want to slide over this3bit3 combination， this three by three combination， this one。

 this one， etc。All right， so now the big question is。



![](img/0932df05d90d8e157333d6981e19c846_210.png)

Can I create？A， in this case， rank for tensor。

![](img/0932df05d90d8e157333d6981e19c846_212.png)

That would hold all the three by three locations here that I convolve this thing with that I sort of overlap this thing with。

Okay， so remember there's it's gonna be four positions that I can。

 I'm gonna create a  four by four output image。 there's sort of four by four positions that I can vol this with right first。

 this one here， then this one here， hopefully can see my mouse okay on this。 then starting this one。

 then starting at that one。 So that's four kind of in there and the X direction and similar4 in the y direction。

😊，Alright， so can I somehow create a3 a 4 by4 by3 by3 matrix or tensor of all those different locations。

 Okay， so I'm going to create some matrix B here。

![](img/0932df05d90d8e157333d6981e19c846_214.png)

![](img/0932df05d90d8e157333d6981e19c846_215.png)

Which is actually I'm kind of giving away the answer there， but that's okay。How do I do that， Okay。

 so I'm going to do this with the as strategy to call Okay， so let's look at this again All right。

 so we want our first block to be basically these nine numbers here。😊。



![](img/0932df05d90d8e157333d6981e19c846_217.png)

Then we want our second block to be these。9 numbers。 and our third block to be these9 numbers。

 Four block of this one。 And then our next dimension， we jump jump by one， okay so。



![](img/0932df05d90d8e157333d6981e19c846_219.png)

How do we do that？Well。Let's create an as write version of A。



![](img/0932df05d90d8e157333d6981e19c846_221.png)

But of course， you know， that's just the the first， the first bit， right， our shape。

 our output is gonna to be 4 by4 by 3 by3。 That's the output size we want。

 And we want each block in this new block nature， each3 by three block to be one of kind of these。

 these these blocks of things we're gonna to be convolving with。 Okay， so if I want my like。😊。



![](img/0932df05d90d8e157333d6981e19c846_223.png)

One by one element to be this thing。When I move down in my first so the first dimension kind of says。

 okay， I want this block here， if I move down in the first dimension， it should be this block here。

 then that should be this block starting here， then it should be this block starting here， etcter。



![](img/0932df05d90d8e157333d6981e19c846_225.png)

So how does that work？ Well， what should be my first stride？ Well， you know。

 if my first block is starts there， my next block would start， you know， move this down by one。

 my first stride number would be 6。 Allright， so strides。



![](img/0932df05d90d8e157333d6981e19c846_227.png)

![](img/0932df05d90d8e157333d6981e19c846_228.png)

![](img/0932df05d90d8e157333d6981e19c846_229.png)

Equal in p array again so I can use actual normal strides， not not nupy strange strides， be6。



![](img/0932df05d90d8e157333d6981e19c846_231.png)

Okay。So my first block that I have is this one， my next block， though。

 would be sort of this three by three block here， so it'd be this one， this one， and this one。

Right and therefore， you know， if I want to if if my next dimension。

 incrementing that dimension by one moves me over by one。



![](img/0932df05d90d8e157333d6981e19c846_233.png)

Well， the stride should just be one。So the next right is one。Next， I want to know， okay。

 so within these three by three blocks now， how do I tiled like that three by3 block， Well。

 in the first dimension of that three by three block， if I increment you know。

 from this position to this position。That moves six dimensions more in memory。

 so my next stride is going to be equal to6。

![](img/0932df05d90d8e157333d6981e19c846_235.png)

And then finally， if I'm with my last dimension moving over this and one， then my that of course。

 also is just a stride of one， and so that is my stride of one。



![](img/0932df05d90d8e157333d6981e19c846_237.png)

Okay， and just to emphasize this， this takes and by the way， if that all kind of went by fast。

 I would go through and read this some more and sort of figure out is what this is doing here。

 But what this does is this creates a new matrix。 Let's maybe just look at B dot shape versus B is a 4 by4 by3 by3 matrix where each block of B is exactly kind of one block that we are convullving with。

 so it's gonna to be one block that we're kind of going convolve with。

 And then we're gonna multiply it by this thing So first multiply this this whole thing here by this one that we multiply it by this next one So so the first block here of this of this matrix here is kind of the upper left corner here。

 the next block of this matrix is is the same decision moved over by one， etc。😊。



![](img/0932df05d90d8e157333d6981e19c846_239.png)

![](img/0932df05d90d8e157333d6981e19c846_240.png)

![](img/0932df05d90d8e157333d6981e19c846_241.png)

![](img/0932df05d90d8e157333d6981e19c846_242.png)

![](img/0932df05d90d8e157333d6981e19c846_243.png)

![](img/0932df05d90d8e157333d6981e19c846_244.png)

![](img/0932df05d90d8e157333d6981e19c846_245.png)

![](img/0932df05d90d8e157333d6981e19c846_246.png)

Okay， so that's， that's sort of how we create this matrix。 And actually that is。

 that's the inter call call。 I mean， it takes a little bit more。

 takes a little bit more kind of work to do this。 But you know， it's， it's I mean， for the。

 for the like multidimensional case， but it's actually not that much work It's essentially the same thing。

 Okay， so but， but how do we actually create a convolution of this， right， So like this is。

 this is still just kind of。😊。

![](img/0932df05d90d8e157333d6981e19c846_248.png)

This is just kind of creating sort of the shifted version of these things。

 but it's not really creating a convolution。

![](img/0932df05d90d8e157333d6981e19c846_250.png)

![](img/0932df05d90d8e157333d6981e19c846_251.png)

The way we create a convolution is we take this thing though。

 and now we treat each of these elements as a vector okay and the cool thing about this is that we can actually just use to do this。

 we can just use the reshape calls。 we can call B dot reshape I guess it would be 4 by 4。

 So it's 16 by9 and what that would be B dot reshape and what that is is that's now the first element here。

😊。

![](img/0932df05d90d8e157333d6981e19c846_253.png)

![](img/0932df05d90d8e157333d6981e19c846_254.png)

this first big kind of three by three block as a big vector， right。

 and then this three by three block as a big vector。

 So this is the the first three by three block is the next three by three block。

And so we can just multiply this thing。By a similarly reshaped version of W。3 shape W to B。

9 dimensional。That takes our filter here， multiplly bunch of this blocks， Ie runs the convolution。

 and then finally we'll take the whole thing and we'll reshape it to be4 by4。

 and that is our convolution。Okay， so we've done our convolution。

Essentially in one line of a call to。To sort of。As try it plus reshape now it's a very sort of important thing to note here。

 which is that some magic happened here。And actually a lot of a really sort of important bit of magic happened there。

 What happened here is that we and actually also in the as contiguous array call。

 we took our memory and we compacted our memory。 So we made our memory。

 we made these matrices contiguous in memory。😊，And unlike the tiling case where we didn't move stuff around the tiling case。

 but we kept the memory size the same。In doing this， this call here。

 we are actually expanding the size of the matrix okay。

 so there is no way to have a so I mean if we look at this。

 let just make C equal to this just for the sake of it。If we look at， let'll go back and。

So if we look at C， right， C has more elements than B does。

 right because we're repeating each location up to three times and unlike the case of。



![](img/0932df05d90d8e157333d6981e19c846_256.png)

Unlike the case of this tiling， there is no way to do that without copying memory right so this one term there occurs in more than one place it occurs here and it occurs here。

And know it's one's a simple case because it appears towards a corner。

 so it's actually not that bad example， but 14 right 14 occurs here here， here， you know， here， here。

 lots of places right all over the place， here， here， here okay。😊，There's no way around this。

 So this reshape call。 and you can even see it。 So if we sort of look at B B before the reshape and look at B's strides。

 this is these funny strides that we specified。 It's multiplied by3， but it's 6，1，6，1， essentially。

 But if we look at C dot strides。 C dot strides is just contiguous array。 So C is a contiguous array。

 It's a contiguous memory， everything is fine。 If we。

 if we do our kind of calls here to we find out I call the print C here。

 What we will find is that C is much larger。 right， actually has to store incontiguous memory。

 all that data。 So we are expanding our size of data when we do this。😊。



![](img/0932df05d90d8e157333d6981e19c846_258.png)

![](img/0932df05d90d8e157333d6981e19c846_259.png)

![](img/0932df05d90d8e157333d6981e19c846_260.png)

![](img/0932df05d90d8e157333d6981e19c846_261.png)

![](img/0932df05d90d8e157333d6981e19c846_262.png)

![](img/0932df05d90d8e157333d6981e19c846_263.png)

![](img/0932df05d90d8e157333d6981e19c846_264.png)

And that's really important to be aware of。Okay， so so let's so so that's that's kind of actually all we need to do I to call for multichannel convols okay。

 and so the entirety of our convolution now is going to be done with one big imp to call call。



![](img/0932df05d90d8e157333d6981e19c846_266.png)

![](img/0932df05d90d8e157333d6981e19c846_267.png)

Just with a bit more care about manipulating our convolution。 So I'm just going to write it here。

 I think it's actually easiest just just to to write out and see what this is。

 but I'm going to write a convolution， which is in call。😊，With Z and weight。

And I'm going to look at so for actually， I'm going to copy above here what my。



![](img/0932df05d90d8e157333d6981e19c846_269.png)

![](img/0932df05d90d8e157333d6981e19c846_270.png)

Data was。Actually before I do that， I didn't actually do this。

 but one thing I can also do here is just time these solutions so I made a big deal of the timing of this before let's time this call what happened here。

😊。

![](img/0932df05d90d8e157333d6981e19c846_272.png)

![](img/0932df05d90d8e157333d6981e19c846_273.png)

![](img/0932df05d90d8e157333d6981e19c846_274.png)

Oh， I think I've created new matrices here。

![](img/0932df05d90d8e157333d6981e19c846_276.png)

And you do that， Okay， so I'm going to time the call here so it's。



![](img/0932df05d90d8e157333d6981e19c846_278.png)

4。2 and milliseconds。

![](img/0932df05d90d8e157333d6981e19c846_280.png)

Let me do a similar version that calls sort of our this is our old tiled one we'll do the same thing in a second with the Inta call one。

 but I'm going time our our old variants into this and so it's about you know it's quite a bit slower and we can improve on this so so we're going to improve in the bitit with our with our Inta call version we're not going to get it to 4。

2 they they do additional optimizations especially for really small kernels as is like that there's a lot of things you can do but we are going to bring it down from this here。

Okay， so sos let's just sort of go and look at kind of our our implementation here。

 let's copy these because we're going to want some of these same things here。😊。



![](img/0932df05d90d8e157333d6981e19c846_282.png)

![](img/0932df05d90d8e157333d6981e19c846_283.png)

To call this and we're also going to look at the strides。 So let's look at like HS。

 WS and Cs as the Z dot strides okay。AndNow let's talk about like do a few additional things that kind of are useful here。

 We're going to look at the the size that we want to have in our sort of matrix operation we want to sort of make this whole thing a bunch of batch matrix multiplies and again I would go through kind of the description here if this doesn't make too much sense。

 hopefully just the code makes sense， but what we're going to do is we're basically going to create sort of a tiled version of our matrix where of our input image where。

😊，We're going to make each， so I'm going to go back to this one thing for a second。

Going back to my to my Python or to my。

![](img/0932df05d90d8e157333d6981e19c846_285.png)

Code for a second。Okay。W I can't switch。

![](img/0932df05d90d8e157333d6981e19c846_287.png)

Here we go。Okay， so we're going to make a version of this thing where each of these is going to be a C in。



![](img/0932df05d90d8e157333d6981e19c846_289.png)

By sea out。Matrix and each of these is going to be sort of a properly size variant of the whole vector。

 right， So it's going to be like a。 so this whole matrix here an in would be a。

So this dimension here would be basically。It would be K by K by C in。 This would be C in by C out。

 and then this here would be， you know， whatever dimension we need sort of stack all the rows and columns together。

 Okay， that's that's the matrix we're to create here。



![](img/0932df05d90d8e157333d6981e19c846_291.png)

Alright， so let's see how we do that。 So we're gonna create all these strides here。

 So the first thing I'm going to do is I'm to talk about like what this。

 this inner dimension of like the size， the matrix we're gonna multiply here。

 So I'll call like inner dim to be equal to K times K times C in。

 that's going to be like the inner dimension。 like the the number of。😊，Columns in our final matrix。

 and I'm going to then make a as my as strideed call。Applied to Z， which is my image。

 The shape is going to be number of batches， shape equals number of batches times H minus k plus1。

 then with minus K plus1。 and the output size is going to be that we want of K is this inner dimension right。

 This is well sorry， actually， it's going to be K by K by C in。

 We're going to then reshape it to be the right dimension。Okay。

 that's that's gonna be the shape of my new matrix。

 I'm going to create early kind of a temporary sixth order tensor。

 And then I'm going to set the strides equal to， well。

 the strides are going be the number of just the normal stride of the batches。 that one't change。

 what I do with my things here is actually the exact same thing I did in the single dimensional case is's going to be equal to the stride in H the stride in width and then you repeat the strides in H and width again。

 So that's sort of like。😊，You know， that was essentially this thing up here。 We did the stride of。



![](img/0932df05d90d8e157333d6981e19c846_293.png)

In this case， this was the height stride， this was the with stride。

 and this is the height stride and it the width stride。

 and so we're just doing that same thing again。

![](img/0932df05d90d8e157333d6981e19c846_295.png)

![](img/0932df05d90d8e157333d6981e19c846_296.png)

And then we repeat the。

![](img/0932df05d90d8e157333d6981e19c846_298.png)

The channel stride as well。And that's our strides。RightThen we reshape this whole thing to be this the second dimension。

 the number of columns is the inner dimension。 So that sort of compresses these last three columns flattens them out。

 last two dimensions that kind of flattens them out。 and I'm going to set the。

First mentioned to be negative  one。Um。Then。I just multiply my。My output rather。Is a times。

My weight got reshape。Well， I want to flatten it in the kernel dimensions and I want to just leave the C outs dimension。

And finally。I want to return。A reshaped version of this， which is M H by H minus k plus 1。

And W minus k plus1 and C out。他在。So that's the entirety of the impol kind of reorganizing。

 kind of str and overlap and creating overlapping columns， all this kind of stuff。

 let's test it of course， let's say out to or out equals column reference。嗯。Z W， okay。

 else I think it's the same as with there out2 equals co in the call Z。And W。 And let's look at the。

Norm difference between them thats out。And again， it's numerically， numerical the same thing。So。

 so I think this is， this is， this is like like so cool， right， This is creating this like。😊。

Six order  six tensor that consists of overlapping blocks of the matrix all extracts all possible three by three blocks of the matrix。

 like with the proper channels and with the proper batch sizes and then does the whole convolution one single match multiplication and what we do find is that this is quite a bit faster now it's not going to touch the pitorrch version still。

 I think it's like， but I think it's going to be about twice as fast。

 probably as as doing the individual matrix multipl。 And that of course you know。



![](img/0932df05d90d8e157333d6981e19c846_300.png)

For for things like， especially if you have smaller batch sizes， the difference here grows because。

 you know， the， the more you can do kind of in one big multiply， the better so。

If I look at the time to get this one。The the time here is。



![](img/0932df05d90d8e157333d6981e19c846_302.png)

I think actually Pythtorch has optimized their thing a lot because last time I tried this on Pytorrch。

 this is about 25% slower than the Pyth implementation。

 but I think it's actually quite a bit slower now so 14。4 so remember our one above here。😊。



![](img/0932df05d90d8e157333d6981e19c846_304.png)

![](img/0932df05d90d8e157333d6981e19c846_305.png)

![](img/0932df05d90d8e157333d6981e19c846_306.png)

Was our sort of naive， not super naive， but the next most naive one was 27。

 So we've basically spit it up by 2x。 we've made it twice as fast， still not to the 4。

21 level but quite a bit faster。 Okay so hopefully that kind of gives you a rough kind of idea of how we go about optimizing these things with with impta call and the key idea here is that rather than sort of rearranged memory in some complicated fashion where you're supposed doing copies and things like that。

 you can do a lot of that with this one nice sort of compact as strideed call and you can create very complex tilings and overlapping tilings and also sort of stuff using just the asstr to call。

 the asstr call of of your numpi。😊。

![](img/0932df05d90d8e157333d6981e19c846_308.png)

![](img/0932df05d90d8e157333d6981e19c846_309.png)

![](img/0932df05d90d8e157333d6981e19c846_310.png)

![](img/0932df05d90d8e157333d6981e19c846_311.png)

![](img/0932df05d90d8e157333d6981e19c846_312.png)

Now one thing that is important， this is the final note of this sort of thing here hiding it with my head here is that the reshape call and the as contiguous array call。

 they hit a lot of logic and actually when you implement all of this in your own ND array library as you will in well you won't implement the convolutions that will be homework4 but you'll implement the calls like as str it in homework 3 when you implement the as contiguous array call or we call it compact to make a compact contiguous in memory array。

😊。

![](img/0932df05d90d8e157333d6981e19c846_314.png)

There is actually quite a bit of complexity。

![](img/0932df05d90d8e157333d6981e19c846_316.png)

There so so I'm writing this you know look look look how fast this convolution is it's just you know a few lines of code that's great。

 but you know the really two lines of actually meaningful code here right just the asronic call and and then the out call I guess you could have even wrapped this reshaping with the with the thing so。

😊，But a lot is happening in actually the ad are call not much is happening all you're just literally taking the exact same memory and just creating a new matrix that has different strides。

 so this call itself is essentially free， there's nothing that happens here。

Quite a bit happens in this call though in the reshape call because the reshape call that one compacts the array in memory and a lot is happening there and you will have to implement that compact call in homework3 and it does take some time especially for arbitrary size tensors to get this right you have to kind of use something like a stack or something like this so be aware of that there is quite a bit of hidden logic there but again the final thing which I think is just beautiful here is the an entire three by three convolution of you know multiple channel multiple batches no padding here just just no padding padding you can add separately this is all this two lines of Python in nuy there aren't that complex lines right there's no like hidden convolution there it's just using matrix manipulations and manipulating memory of matrices to call these things which I think is just really cool。

All right， so we'll see you next time when we talk about actually some more architectures in deep networks and some more things like that。

 but hopefully this gave you some idea of how powerful these sort of matrix manipulations really can be。

Thanks everyone and see you next time。

![](img/0932df05d90d8e157333d6981e19c846_318.png)
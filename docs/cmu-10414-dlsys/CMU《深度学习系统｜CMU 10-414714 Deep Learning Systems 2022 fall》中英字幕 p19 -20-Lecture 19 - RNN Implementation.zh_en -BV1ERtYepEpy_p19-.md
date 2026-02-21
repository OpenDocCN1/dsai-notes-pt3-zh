# CMU《深度学习系统｜CMU 10-414714 Deep Learning Systems 2022 fall》中英字幕 p19 -20-Lecture 19 - RNN Implementation.zh_en -BV1ERtYepEpy_p19-

All right， hi everyone。Welcome to Deep Learning Systems algorithms and implementationmment。

Today we're going to talk about implementation of recurrent neural networks。

 abicular implementation of an LSTM network。As we did with the convolutional neural network example。

 what we're going to do today is we're going to sort of start out by。

Illustrating what the LSTM looks like or just what the model looks like and the weight of the model in Pytorrch。

 and then we're going to implement a clone of that model using just pure nu pie and the idea here is to show the sort of guts of the implementation and ideally also to show that it's really not that complicated。

 so the basic idea of the LSTM is really quite simple。

So let's go ahead and get started here we have our blank。呃。Notbook and in the homework of course。

 you're going to implement this in needle， but here we're just going to implement it in nuie to give you a basic idea of the operations that are involved。

And then we will in the， of course， homework， you'll have to actually use this in an I differentiation tool to actually run this and train these models。

All right， so let's go ahead and get started， let's start by importing torch and importing the neural network library of torch。

And willll importump。All right， so let's start off with sort of looking at。

 let's put number as empty。Let's start off by looking at what a Pytorrch LSTM actually kind of kind of looks like here。

 So let's set our model to be an LSTM cell。 We're actually going to start off just implementing a single cell of the LSTM that's sort of one block of the of the operation there。

And the arguments for the LSTM cell are the hidden sizes for the input sizes， first of all。

 the hidden size。 So let's make the input size。Let's make it。20 followed by。Followed by a。

Hidden size of， say 100。Okay。Let's look at the sizes that are involved in this。

 so' if you look at the model here， there's actually going to be two weights that are of importance。

It's going to be the weight N N and the weight weight HH and the weight IH。

To understand these weights here， let's actually go to a moment to look at the LSTM documentation that we see in Pytorrch。



![](img/fedb479405b637e3d017ec260a8164aa_1.png)

So if look at the LLCM documentation in Pytorch it's actually it's a bit complicated here。

 they kind of write this whole thing out term by term。

 they write expressions for all the IFT and they use weight matrices too that are like one for each pair of possible possible things here。



![](img/fedb479405b637e3d017ec260a8164aa_3.png)

But we sort of know from experience that this is not actually that complicated right so we sort of remember from last time what we really said what's going on here is that what we really have is we have sort of。



![](img/fedb479405b637e3d017ec260a8164aa_5.png)

Intermediate hidden vector reformform， ITFT。GT and OT。

 and this whole thing is some nonlinearity and happens to be sigmoid。Sigmoid。And H。And sigmoid。

W times sort of one big matrix that multiplies really all these collections of hidden units there。

 so it's we called it W H， H times H。I minus-1。Plus， W H。X。X。

Is just say t minus1 c plus we had a B like a BH term also。Okay。

 that was what that was how we defined it and to be clear， kind of internally。



![](img/fedb479405b637e3d017ec260a8164aa_7.png)

Despite the documentation looking like this， and by the way。

 this documentation bothers me for many reasons because。For example， the inncs are flipped here。

 this should really be IH because it's the output is H and the input。

 the output is I and the input is H，Regardless。What， what Piytor is doing internally。

 just like we wrote it last time， is this really combining all these matrices into two big blocks here？



![](img/fedb479405b637e3d017ec260a8164aa_9.png)

So what's really happening is that we have model weight H H， let's print the size of this。

 let's's see what size this is， that shape。😊，We see that this is a 400 by 100 dimensional matrix。



![](img/fedb479405b637e3d017ec260a8164aa_11.png)

And so what's really happening here is this is actually exactly this matrix here。

 especially the transpose of that， they have it in the other in the flipation because remember our hidden size is 10s。

 this is 100 dimensional， so this thing here will be or rather this thing here。😊。

Willll be 400 dimensional。And that means this matrix here should be 400 by 100。This one here。

 by the way， should be 400。By 20。

![](img/fedb479405b637e3d017ec260a8164aa_13.png)

And P towards exactly stores kind of the flipped versions of these， so this one is the 400 by 100。

 I guess actually no it's nice it's not we're going flip it later ourselves。

 but to do the batch form of bit， but it's exactly this matrix here and similarly if we look at model do weight。

Guess it it's let's it call it IH that shape， this is the 400 by 21。

 so this is actually these matrices are exactly these two matrices here。



![](img/fedb479405b637e3d017ec260a8164aa_15.png)

Actually， exactly these two matricaces here。Okay， so we can actually look at what this looks like。

 so let's go ahead and now define kind of our implementation of a single LSTM cell。



![](img/fedb479405b637e3d017ec260a8164aa_17.png)

So single LSTM cell， we're going to implement this in Pytorrch。



![](img/fedb479405b637e3d017ec260a8164aa_19.png)

Sorry， in Npy。 And we're going to check that it's doing the same thing as the Pytorrch version。

 So let's start off by just defining the sigoid nu nonlinear the already。

 There's no built in function。 I think in in Npy for this。 let's just return one divided by one plus。



![](img/fedb479405b637e3d017ec260a8164aa_21.png)

呃。OnePlus。XNegative x， that's the standard sigmoid function。

Now let's define an LSTM cell we're going to define this just sort of functionally。

 and so that means that we're going to give as input X， the X， the input H， the previous hidden unit。

 C， the previous hidden cell state， I know that really both H and the cell state C or both the hidden state。

 but we're going to adopt the we're going to adopt the convention of。The LSTM here。

And then we're going to pass8 WHH， and I'll even use the WIH as the conventions。

 I'll forego things in a dot type or just notation here， and then our bias B。

Okay so that's going to be our conventions here and so how we actually go about forming this right so how do we actually go about about forming this well。

😊，We can actually form all IFG and0 by just taking WHH here and just multiplying it by H plus WIH times x plus B。

 but of course this is this should be。Oh， but of course this is now going to be a00 by 400 dimensional vector and so to split this into 100 dimensional vectors。

 we just call NPP dot split into four components。

![](img/fedb479405b637e3d017ec260a8164aa_23.png)

Okay， now we to， of course apply the on nonlinearities， so this doesn't， you know。

 if we just run this， it will just be a linear function。😊。

At least go ahead and do that by applying the non nonlinearators to each one。

 this is sigmoid of I really these are sort of the temporary versions of I， so this is sigmoid of I。

 this would be sigmoid。F， this would be tan0 H。Of G and this one is sigmoid of O。 All right。

 And next we have the two sort of main equations for have an LSTM。 So that would be these two。

 the cell state is this Ft， the forget gate times the previous cell state plus this term again。

 it's called the think the input gate times the cell gate again， these are just these are just terms。

 thats just intermediate terms， but its it's F times C， So we say that C out。😊。



![](img/fedb479405b637e3d017ec260a8164aa_25.png)

![](img/fedb479405b637e3d017ec260a8164aa_26.png)

![](img/fedb479405b637e3d017ec260a8164aa_27.png)

Equals F times C， the C that was the input to our function here plus I times G。 Again。

 these are element wise products。 So we're just using multiplication here， as you would in。In。

In nupi know element wise multiplication， and then the output hidden state would be equal to O times sorry yeah。

 it would be O times NP do1 H of C。Out， then we return the two hidden states here。

 return the out the hidden state and the cell state。 this actually is a。Finished LSTM。

 So let's go ahead and evaluate we go see what this looks like。 So what's set X to be a。😊。



![](img/fedb479405b637e3d017ec260a8164aa_29.png)

Random variable， which serve a vector of random random Gaussian entries。

 and let's make it actually just so we。Don't have any issues with PyTtorch conversion。

 let's make it a 32 bit。Floodating point number， same for H0 that will be。

This random that it'll be size 100。And C zero。Would be the same thing here。Not copy be your properly。

There we go， okay。And now let's actually look at what sort of the right answer is。

 I mean let's just compute the kind of the right answer。

 so H star and C star by inputting this into our ptorrch version of the LSTM cell okay。



![](img/fedb479405b637e3d017ec260a8164aa_31.png)

![](img/fedb479405b637e3d017ec260a8164aa_32.png)

And so this would actually be the exact same thing we're doing before we just convert to a tensor each of these。

 a torch do tensor x， torch dot tensor。H0， actually the convention for these things you have to pass sort of the hidden state and the still state as a tuple。

 so it'd be torch dot tensor， H0 and then torch。 tensor C0。

And that will output that sort of true H and it doesn't really matter what H is here。



![](img/fedb479405b637e3d017ec260a8164aa_34.png)

That's H sometorrch tensor。 And this is sort of our reference implementation of the LSTM though。

 Now we're gonna check our implementation against it。 and we'll see it is， in fact the same thing。

 One thing on those here is that I have this one here。

 that's the batch dimension right So in Ptorrch dimension for the input to LSTM cell the first dimension is the batch dimension。

 and we only this we've implemented at least so far for just a single just a single batch we'll talk about batching in a second when it comes to when it comes LSTMs。

 And so we're just going confirm that our output here is the same as what we got before。

 So let's try calling our LSTM cell。😊。

![](img/fedb479405b637e3d017ec260a8164aa_36.png)

![](img/fedb479405b637e3d017ec260a8164aa_37.png)

With F x， H0， C0， our weight， I don't here we'll just pass in。I insert a new line here。

 but model that weight。H， H。And we have we have to convert this to nuy， so detached dot nuy。

 and then our next thing， which is model。Weight， I H detach。安排。And finally， the bias term。 And again。

 torch something very weird here。 So if you look at the edge of documentation。

 there are two bias terms here that you add。 They both get the exact same gradient。

 They're both just added。 They're both those parameters。 I have no idea why they're doing this。

 I guess it's not that big a deal because ultimately they're just maybe they're matching some other weird reference implementation here it's very strange and you know I'll use P Hs's convention to to a degree。

 but I see no reason to add two separate bias terms。 So I'm just gonna to add those two together。

 So this is model bias。 let's see which one is it's bias。😊。



![](img/fedb479405b637e3d017ec260a8164aa_39.png)

![](img/fedb479405b637e3d017ec260a8164aa_40.png)

![](img/fedb479405b637e3d017ec260a8164aa_41.png)

![](img/fedb479405b637e3d017ec260a8164aa_42.png)

啊。Not that bias。H， H， and then model that bias。I H。Add those together and then detach them。

Where it's non by。

![](img/fedb479405b637e3d017ec260a8164aa_44.png)

Right。Think that's it， let's run this so we're getting an error there。



![](img/fedb479405b637e3d017ec260a8164aa_46.png)

Okay， so the size of this is wrong， Oh， of course I have to only pass in the first elements here。



![](img/fedb479405b637e3d017ec260a8164aa_48.png)

![](img/fedb479405b637e3d017ec260a8164aa_49.png)

There we go， okay。And now what we can see is if we look at。Difference between our。

Solution and the kind of reference solution， which is just the。

The zero element of that because this is again going to be a batch vector。

 we have to deach it and cover it's an nu。

![](img/fedb479405b637e3d017ec260a8164aa_51.png)

All right， if we did everything right here， we should see that it's to within numerical precision。

 So we are， in fact， and the same to be true the cellgate。

 So this is all that the implementation inside of Ptorrch is doing itself。 Okay。

 it's just computing these operations here。😊。

![](img/fedb479405b637e3d017ec260a8164aa_53.png)

All right， so let's let's now move to a slightly more complex version because this here is this is really just computing kind of a single LSTM cell right。

 which is not really what you typically want to do I mean computing a single LSTM cell is。😊。



![](img/fedb479405b637e3d017ec260a8164aa_55.png)

![](img/fedb479405b637e3d017ec260a8164aa_56.png)

I mean that's it's worth you have to do this， right to test out the first block， but of course。



![](img/fedb479405b637e3d017ec260a8164aa_58.png)

It's a full LSTM， and you can even come back see this， the Pytorch LSTM class。

 this is the one you typically use and it applies an LSTM to a whole sequence。

 not just to a single operation。

![](img/fedb479405b637e3d017ec260a8164aa_60.png)

Im sorry not touch to a single sort of hidden state and output state。

 you really apply it to the entire sequence there。😊。



![](img/fedb479405b637e3d017ec260a8164aa_62.png)

So let's take a look at that and see how this would do。 So now let's talk about。

Sort of a full sequence version of our LSTM。

![](img/fedb479405b637e3d017ec260a8164aa_64.png)

All how will we implement that？Well。Let's start with redefining our model to be Pythtorch as LSTM and LSTM。

 for some reason， I believe if you look at the docs here。

 the arguments are the input sizes first and the hidden size is second。



![](img/fedb479405b637e3d017ec260a8164aa_66.png)

![](img/fedb479405b637e3d017ec260a8164aa_67.png)

Unlike LSTM cell， for some reason I can't really understand。



![](img/fedb479405b637e3d017ec260a8164aa_69.png)

They have the hidden size first and the other size second。嗯。😊，Or I should that right， sorry。

 so it's the no input size first and the hidden size second， so that would be 20。😊。



![](img/fedb479405b637e3d017ec260a8164aa_71.png)

Hundred。Whereas thiso is is the same too， is this the same？



![](img/fedb479405b637e3d017ec260a8164aa_73.png)

Okay， yeah。 so it actually is the same。 I thought maybe maybe there's there's。

 it''s a different one I'm thinking of。 So anyway， yeah。

 LSTM has the hidden size and the input size and then the numb layers。😊。

It's an argument and we want numb layers equal to one。And so this is now a single layer LSTM。

 And as before we can run it on some on some data。 But here we're actually going on a whole sequence of data。

 Okay so rather than running it on sort of a single single input。

 we're going run this on a whole sequence of inputs I'm going to to note that or sort of emphasize that by making sure that we use uppercase x here to noteote a sequence of say 50 different time steps。

 So now each of the rows of this matrix is going to be a different time step and the C0 and an H and60 are still just one dimensional。

 of course， because they are just the initial state into our LSTM right this is sort of what we're doing here is we are computing an LSTM。

 which remember takes in。😊。

![](img/fedb479405b637e3d017ec260a8164aa_75.png)

![](img/fedb479405b637e3d017ec260a8164aa_76.png)

![](img/fedb479405b637e3d017ec260a8164aa_77.png)

Takes in sort of an H0 and a C0。C，0。Using this along with X1。To compute H1 and C1。

 that uses this to compute。H2 and C2， along with x2。



![](img/fedb479405b637e3d017ec260a8164aa_79.png)

Ea Okay， so we're going to write the code that implements this now。



![](img/fedb479405b637e3d017ec260a8164aa_81.png)

All right， so everything here actually looks very， very similar to before well actually。

I should take that back。's its it's just leveraging the same cell we had before。

 just applying it in sequence one after the other。 right so that's all that's really happening here。

 So let's define now rather than just our LSTM cell function。

 Let's define our LSTM function So let's define LSTM， which will take in this input X， still H and C。

 those are the sort of the initial states there， same inputs before W IH W HH and B。



![](img/fedb479405b637e3d017ec260a8164aa_83.png)

![](img/fedb479405b637e3d017ec260a8164aa_84.png)

Okay。First thing we're going to do is we're going to initialize kind of our set of all our hidden states and actually it turns out that we're going come out follow Ptorche convention here where we're only going to return the array or the sort of the tensor of all hidden states over all times for the H variable the C。

 the cell state we will just return the very last one Okay so that's the sort of convention。

I torch for again， kind of owing to the convention of LSTM does not return the whole cell state。

 It just returns the whole。Hidden state portion of the hidden state and then the last cell state and we'll see actually at the very end of this lecture why we return the last hidden state。

😊，Alright， so H is going to be equal to just we'll start to initialize it with zeros。

 so the zero should be x dot shape0。 so we want the same size as x。

 but then the output would be the same size as H so H itll be the number of rows and x and the number of columns that are in the size of H。

Okay。And now we're just going to iterate over our whole sequence， so for T and range x shape0。

We run our LSTM cell， so we set our hidden state and our cell state to be equal to the LSTM cell of。

X T so let's just take the teeth element of that H， C， W， H， H， W， I H and B。

 And then we're going to set H T to be equal to H。 and we're going to return the tensor。

 really just matrix here of all our hidden states and the last cell state。Okay。All right。

 so now let's again kind of run our LSTM first， actually the call is going to look very similar to this。

 I'm just going to copy this thing here。

![](img/fedb479405b637e3d017ec260a8164aa_86.png)

![](img/fedb479405b637e3d017ec260a8164aa_87.png)

![](img/fedb479405b637e3d017ec260a8164aa_88.png)

I'm going to copy that and input here now my whole X。Just the first hidden say。

 I'm still using the convention again， for Pytorrch's sake that you know we。

 we have a batch of these things， even though we'll again， get to batches in a second。

I'm going to pass this as our inputs there just for simplicity。

 and we're going to call this instead though LSTM and we're going to get the set of all the outputs。

😊，All right， so this is our call to our LSTM。

![](img/fedb479405b637e3d017ec260a8164aa_90.png)

Make sure that all runs Snope。

![](img/fedb479405b637e3d017ec260a8164aa_92.png)

We we're doing wrong here right， so the model does not have any more of these terms anymore。

 actually， what the model has is weight HH L0 because it's the zero layer。

That's when we replace these all with L0，0。L0 is0 and the same for the biases。

 so that's to replace L0 bias。

![](img/fedb479405b637e3d017ec260a8164aa_94.png)

And L0 by。And then it competes。Okay， so I'll now let's do the same thing for。

Talking about the sort of the reference solution， actually。Pytor returns。

Both the full matrix of hidden states and a tuple containing the last hidden state and the last cell state。

 so I'll say like the last hidden and the last cell。

 actually I'm mentioned call this CHL is more like C or some of that like the next hidden state or something。

And this is going to equal the， the model applied to the tensor。呃，X。

I' me just go up and copy what I have here。

![](img/fedb479405b637e3d017ec260a8164aa_96.png)

![](img/fedb479405b637e3d017ec260a8164aa_97.png)

Tensor。And。These things。And if you'll forgive me one bit of a trickery for now。

 I'm going to do one more thing here， I'm actually going to insert an extra dimension in there in the second dimension and we will immediately come back to that in the next section of why I'm doing that。

 but just know that for now you have to add a zero dimension in the second dimension or a zero sort of。

Colllumn of size one in the second dimension here for this to actually match。

 so I'm going to do this。

![](img/fedb479405b637e3d017ec260a8164aa_99.png)

And that should work， nope。

![](img/fedb479405b637e3d017ec260a8164aa_101.png)

啊。Close my brackets。And now we can similarly。Print the difference between。P。

Whatever I want to follow the print and the dot line knowledge。That norm H minus H。

And we want to similarly just take this。First entry there that attach。だ。Alright。

 and let's see what that looks like。 So again， we're within numerical precision in our implementation。

 So the LSTM model in Ptorrch is exactly just calling this thing。

 And we're going link that in nu by now， But you can， of course。

 implement the same thing as a module in needle。 and you'll have a module that does the same thing as your as your。

😊。

![](img/fedb479405b637e3d017ec260a8164aa_103.png)

![](img/fedb479405b637e3d017ec260a8164aa_104.png)

Pyth forellaS steel。And this is true with one little exception here， which is。

 I'm not going to come back to this weird batching now。Um。

Or this weird sort of expert dimension that I have here and talk about that。

And the reason this all comes up and sort of what's going on here。What's going on here？Is related to。



![](img/fedb479405b637e3d017ec260a8164aa_106.png)

How we batch。LSTMs。

![](img/fedb479405b637e3d017ec260a8164aa_108.png)

So。I want to talk a little bit about kind of again， kind of in theory about now that we've seen some。

 some discussion about sort of efficient implementations also when it comes to when it comes to sort of the the。

I guess you would say like the internals of major multiplication。

 we sort of know that multiplication works best when。Marices are contiguous together in memory。

In fact， in needle， the only way that we can really run matrix multiplication is by first compacting the matrix。

 then calling multiply and then having that compact matrix be the thing that we multiply and so if your sort of memory is scattered all around。

 then it's really sort of unclear how you go about doing the multiplication。

And this relates to this sort of， you know， what's happening here。So let me。

 let me kind of dive in this little， a little bit more here In some sense， for。

 for the case talked about before， we have this setting， right， where we have a matrix X。

 which we defined as， you know， being basically。

![](img/fedb479405b637e3d017ec260a8164aa_110.png)

T by by N， or I guess D， where D here is the， the size， the dimension， the hidden dimension。 Sorry。

 I guess x is N， right， X is the dimension of the input。 and T will be the sequence length， right。

 That's how we defined our， our。

![](img/fedb479405b637e3d017ec260a8164aa_112.png)

X input here。Now the question is suppose that I want to process multiple batches of this at once because the problem with this of course。

 right the problem with with this call that I'm doing right now is that even though I'm processing kind of a matrix of xs as input I'm still doing matrix vector products in my LSTM cell so my LSTM cell call is still calling individual is this hidden state at time t is still a vector and that of course is really sort of fundamental to LSTMs you can't know these things are vectors and so you can't compute H2 and C2 until you've computed H1 and C1 we'd like in some sense to be able to compute all of these simultaneously in one big batch but we can't do that these are vectors and the only way to compute these things is to do a matrixe the weights of our LSTM times this vector for each sort of slice of。



![](img/fedb479405b637e3d017ec260a8164aa_114.png)

![](img/fedb479405b637e3d017ec260a8164aa_115.png)

![](img/fedb479405b637e3d017ec260a8164aa_116.png)

![](img/fedb479405b637e3d017ec260a8164aa_117.png)

![](img/fedb479405b637e3d017ec260a8164aa_118.png)

Time。And we don't want to do that right， Of course， we want to really do matrix matrix operations。

 That was sort of the whole crux of of our linear algebra work that we did。

 and we saw that Pat lights multiplication were much faster than matrix vector products。😊。

And so the question is how do we go about doing that so how do we go about we would like to batch these somehow right to add another batch dimension and we want to ask kind of how would we go about really doing this？

😊。

![](img/fedb479405b637e3d017ec260a8164aa_120.png)

![](img/fedb479405b637e3d017ec260a8164aa_121.png)

Well， kind of the most obvious thing we could do is take our matrix here， which is sort of， you know。

 has a number of times and the number of dimensions and add a batch dimension like we are used to just add a batch dimension。

 which just describes the number of examples in our mini batch。

And we can do this and this is sort of this would be kind of normal pietorrch conventions for how you set up a matrix right in convolutional networks。

 the batch dimensions always first and MLPs， the batch is always first。

 it would make sense for the batch to be first here。But let's sort of think about this again， right。

 if we are laying out our memory in this form。And then we access kind of this element here。

 right so if we want to access all the elements at time one。

 that would be kind of this call here right call like this。And unfortunately， if this。

 if we're storing our x matrix and the same goes for the hidden states too if we're storing our x or our hidden states or any the other terms in this form。

Then a matrix like this， which again is sort of all the inputs at time one。

This would not be contiguous in memory。So if we want to do just a batch form of these expressions here。

 apply them to a multiple element of these expressions here， apply it to a whole matrix。



![](img/fedb479405b637e3d017ec260a8164aa_123.png)

![](img/fedb479405b637e3d017ec260a8164aa_124.png)

We'd be inputting as x and then eventually as H， some matrix looked like this。



![](img/fedb479405b637e3d017ec260a8164aa_126.png)

For different keys， so we do this equals 1， ts 2， etc。And that would not be contiguous in memory。

And so for that reason， when we batch things in。For input to an LSTM。We switch this around。

 We actually kind of breaking convention， store the time dimension first， then the batch dimension。

 then the hidden state dimension or the input dimension or the hidden state dimension。



![](img/fedb479405b637e3d017ec260a8164aa_128.png)

and you can actually see this in the documentation for Ptorrch2。

 so Ptorrch will talk about kind of the format that uses， I guess it uses n for the batch size。

 L for the length and HII for the hidden dimension。

 so a little bit different or H in for the input size。😊。



![](img/fedb479405b637e3d017ec260a8164aa_130.png)

Each out for the hind size。😊，But normally speaking。

 this will use this format unless you pass this batch first equals equals true flag here。

 But this is actually not the standard convention。 And you shouldn't do it this way。 at least not。

 not naively。 if you're using kind of a traditional image multiplication routine。

 because if you pass， if you pass kind of this form。



![](img/fedb479405b637e3d017ec260a8164aa_132.png)

Of batch matrix， you would end up having to processes a whole lot of images like this。

 which are not contiguous memories you yet to copy them over anyway before doing the matrix multiplication。

 and that would not be a very a very good thing。 So it's much better to input it in this form。

 and I guess in Pytorrch convention。 So if you boy what this was。TB。

And it's like in Pythorch convention， this is。

![](img/fedb479405b637e3d017ec260a8164aa_134.png)

What they call this， I think。

![](img/fedb479405b637e3d017ec260a8164aa_136.png)

They call this L N H I， I， L N H I I。No， H in。So sorry for the little different piece of ciation there。

 I think we've used this throughout the class so we'll keep doing that now but。

This is what they they call in Pytorch okay so this is how we're going to pass matrix C data and the nice thing about that is once we do that。

 we can just use a call like this to get all the batches at time T in a nice contiguous format。😊。

All right， so the only difference now is that we need to when we just， we have to， we have to。



![](img/fedb479405b637e3d017ec260a8164aa_138.png)

Use a different，'s slightly different definition of our LSTM cell now designed for batching。

 So just to emphasize this， I'll sort of give a set of these things。

 So actually know what I'm not gonna bother with that。 I have to change in bunch of places。

 So I won't do that。 But what I will do is define these is define these sort of separately。

 So what we actually have here would be H times W W。



![](img/fedb479405b637e3d017ec260a8164aa_140.png)

![](img/fedb479405b637e3d017ec260a8164aa_141.png)

Our convention is that actually this form is the actual form of the matrix。

 the other form was a transposed form， so keep we're going to keep that as the form we actually care about。

😊，But this is sort of our convention here， this form right was the form we care about。

 well similarly， we'll say X。😊，Times X， W I H will then have to actually transpose the pytorrch internal arrays to get them to look like this。

 Probably I really should have written originally like this because we typically said that when we multiply a matrix10 vector operations。

 we transpose them， but whatever I already ordered like this。 So that'll be okay for now。



![](img/fedb479405b637e3d017ec260a8164aa_143.png)

![](img/fedb479405b637e3d017ec260a8164aa_144.png)

But I'll transpose our weights before this。

![](img/fedb479405b637e3d017ec260a8164aa_146.png)

Everything else， the same only difference we asked to have to specify which axis we're splitting over。

 so these are all going to be matrices now。And we want to split over the like a normal sort of convention。

 the first dimension is going to be the batchsh dimension。

 second dimension is going to be hidden dimension。 So we want to split over the second dimension or axis equals one。

Everything else to say the same because these are all element wise products。

 we actually't need to change anything here so we get the same exact form。

 so let's just redefine our LTM cell like that and I think，😊。



![](img/fedb479405b637e3d017ec260a8164aa_148.png)

I think we actually can keep our LSTM even the same as before， but let me just make sure that's true。



![](img/fedb479405b637e3d017ec260a8164aa_150.png)

Where is our LSTM？

![](img/fedb479405b637e3d017ec260a8164aa_152.png)

No， we actually have to do a little a little different there。 you to define the size our of our。

Hidden safe to be different。So now our hidden state would be its first dimension would be x shape0。

 but now this is now the time dimension。The next is going to be the batch dimension like this。

 And then H is also。Two dimensional in our convention， right。

 so the first would be the batch dimension， second would be this dimension。

 so we want this of second dimension of H。Now we want to go for T in all the time。

 which is still the shape 0， this is still the total number of time steps。

 H and c equals LSTM cell that's all the same as before。

 and then H T equals T and I think this all stays the same as before。



![](img/fedb479405b637e3d017ec260a8164aa_154.png)

![](img/fedb479405b637e3d017ec260a8164aa_155.png)

Okay， so now let's go ahead and。

![](img/fedb479405b637e3d017ec260a8164aa_157.png)

Test out our batch version of our LSTM cell。 let's create some data。



![](img/fedb479405b637e3d017ec260a8164aa_159.png)

Let's say。Again， we're going to have 50 time steps， but now's add a batch size of 128。And of course。

 means we also need to have 128 different。hidden states and 128 different initial cell states。

 and we'll leave the last dimension here just for the sake of Pytorrch。



![](img/fedb479405b637e3d017ec260a8164aa_161.png)

Okay， so I think that's， that's about it。 It's actually even easier than before because we don't need to do this。

 play this weird game here with。

![](img/fedb479405b637e3d017ec260a8164aa_163.png)

![](img/fedb479405b637e3d017ec260a8164aa_164.png)

Tensor shapes and everything。 We have all our dimensions for pytor to be happy。

So let's input H H0 and C0。And let's see， okay。

![](img/fedb479405b637e3d017ec260a8164aa_166.png)

And now let's make our call so let's。Take our。

![](img/fedb479405b637e3d017ec260a8164aa_168.png)

Call of our hidden state and our next set of cell states。 make this an LSTM。

 We still have to say zero here because we still have this。Weird。Iues that's now a batch dimension。

 It's very odd how Pytor does these things。 This is like I guess a sequence dimension here。

 So you know we have sequence only of one for the hidden state。

 the initial hidden state initial cell state， but we'll pass in zeros for those。

 we do have to trans pose these。 So by our convention these weight miss are transpose versions of their old Theyre old selves。

 And I think this is let's see if that runs。😊。

![](img/fedb479405b637e3d017ec260a8164aa_170.png)

Okay， great。Now the big moment of truth here， let's see if， in fact。

 these two things correspond to each other， so let's find H minus H。Detaachump排。



![](img/fedb479405b637e3d017ec260a8164aa_172.png)

And oh， no。So the H， which one it be。

![](img/fedb479405b637e3d017ec260a8164aa_174.png)

Let's see what shapes they are。

![](img/fedb479405b637e3d017ec260a8164aa_176.png)

Okay， so that's that shape。 Let's see。So the same things。



![](img/fedb479405b637e3d017ec260a8164aa_178.png)

嗯。

![](img/fedb479405b637e3d017ec260a8164aa_180.png)

Ys。There we go。 Okay， and as long as I don't call， you know， a module by accident。

 I'm trying to call a norm。 everything works。 So these things still work and。



![](img/fedb479405b637e3d017ec260a8164aa_182.png)

![](img/fedb479405b637e3d017ec260a8164aa_183.png)

We have now a full implementation of a batched LSTM。



![](img/fedb479405b637e3d017ec260a8164aa_185.png)

Exactly the same sort of mirroring piey implementation to numerical precision in， you know。

 was that like 1010 lines of code here，13 lines of code， not too bad。

 And I could reappbbreviate it more， right， I could， I could， I could cheat some and like。😊。



![](img/fedb479405b637e3d017ec260a8164aa_187.png)

![](img/fedb479405b637e3d017ec260a8164aa_188.png)

Make it even shorter But the point is this is a really。

 really simple operation and sort of the mathematical form might look a little bit a little bit hairy there。

 I mean sort of you know looking at these equations， it probably would take。

 you know more lines of latex code to write this code out than it takes just to write it in in code itself to actually implement this' that's pretty nice right？

😊。

![](img/fedb479405b637e3d017ec260a8164aa_190.png)

![](img/fedb479405b637e3d017ec260a8164aa_191.png)

![](img/fedb479405b637e3d017ec260a8164aa_192.png)

Okay now that actually is the majority of what I want to talk about that I'm actually going to evaluate here in the notebook that's so the majority of what you'll sort of what I can validate and check here without having automatic differentiation tool about backing this whole thing。

 but I want to talk a little bit just sort of writing the code but know not being able to run it because we're not going to write this in needle about training LSTMs I'm going just I want to just kind of conceptually talk about what does it mean to actually train LSTMs and in particular there's sort of one there is one sort of subtle key when it comes to training them。



![](img/fedb479405b637e3d017ec260a8164aa_194.png)

Which I'll talk about a little bit， I alluded to it last time and I had to do with what something called truncated back propagation through time。

 but we'll get to this in a second。So all right， let let me first talk about how we might train an LSTM to accomplish some task right and the basic idea is that I want to be quite sort of simple and straightforward here and you know to define a routine like train LSTM that will take as input X H0 C0 so that sort of is the input to run the LSTM but then we'' take y。

 which is going to be like the target output of our hidden state now in reality you might what you really might want to do is have an extra layer on top of the LSTM that actually computes you know a projection to the same dimension as y or something like that。

 but I'm going to ignore that or rather what I'm going to do is really is I'm going to sort of bundle that all in some loss function。

So I'm going to give a target Y， and then WH H， WIHB， and then something like an optimizer。

 this is all conceptual， so I'm not going to worry too much about the details here。

Now what I would do to train this LSTM， the nice thing about this is that this is incredibly simple。

 so I would just basically call H and CN equals my LSTM of X， H0， C0， W， H， H， W，IH。B， all right。

 so I just would call my LSTM and then I would compute some loss between my hidden state and my target output and that could be a loss that involves you know one more transformation of the hidden state by another linear layer something like that I'm not going to worry too much but that or it could just be trying to directly predict the hidden state from the y from the hidden state it's something。

 but it's some loss function， sort of a simple loss function just compares each sort of individual H and each y。

And then。In the beauty of automatic differentiation。

 if I've implemented all of these calls in needle right so if I just replace this this NPA implementation with the implementation and needle and you have to add a few more things to this by the way。

 you have to add which you will do in the homework is add things like split and stuff like that you have to you have to add support for that。

😊。

![](img/fedb479405b637e3d017ec260a8164aa_196.png)

![](img/fedb479405b637e3d017ec260a8164aa_197.png)

And I mean TH actually isn't too bad because we already had exponentials。



![](img/fedb479405b637e3d017ec260a8164aa_199.png)

As long as you do all that and implement it in yield。

 then to get the gradients with respect to all your parameters， you just call lost out backward。

And you know， opt that step， right， where， where opts here would be like an optimizer setup up。

 You know， opt would be something like。SGD with， you know， the parameters is equal to like W。

 H H and WI H and B or something like that。 It's just again， this is just sort of an illustration。



![](img/fedb479405b637e3d017ec260a8164aa_201.png)

![](img/fedb479405b637e3d017ec260a8164aa_202.png)

I'm not going this code will not， of course run， I guess that will run。Defining it， though。

It can't call it。あん。Okay， so that's sort of how I want to set things up to start with。

The next thing the only last thing I want to say about training is that if we have a deep LSTM。

 so suppose we have an LSTM that is multi layered right， so we have8 H。



![](img/fedb479405b637e3d017ec260a8164aa_204.png)

Z for the first layer going into H1 for the first layer， going to H2 for the first layer， et cetera。

 and this takes x1， and this takes x2， and then I have some other layer here， so H。2。That's one。

And then H2。H。That was actually correct to H22。 And then I have some initial hidden state here H02 here I'm actually going to forego the the LSTM。

 the cell state portion。 I'm just going talk conceptually about a a deep layer here。

 they're actually， I have a little bit of options here now right。

 if I want to compute this element here， I actually everything I need to compute the second layer for this time after I've computed this element here right。

 So I could compute kind of this whole thing layer by layer。😊。

And then compute it sort of time slice by time slice。

 so I could iterate kind of layer by layer and then iterate time by time， but because the LSTM call。

Calls an LSTM over a whole time sequence。 It's much more common to sort of compute this whole layer here and then use that to compute this whole layer there for a deep multilay。

 LSTM or a multilayer RN in general。

![](img/fedb479405b637e3d017ec260a8164aa_206.png)

Right， so that's what I'm going to do here。 I'm going to define， you know。

 a function like train beep， LSTM。And I'll have x y or x H0， C0 Y these would now be， I guess。

 as of all my H zeros and all my c zeros right， And then I would have W H H W I HB。

 these are not going to be lists or tensors of all my different weights and then I'll still have opt。

 which is like over all of them and so what that would be is I would have something like。Actually。

 I'm yeah， so I just set the initial state actually even just x for convenience。

 and then it's my the initial input the first LSTM is of course， X and then so for D in range depth。

 I guess like depth equals。😊，Equals something like。Length of。



![](img/fedb479405b637e3d017ec260a8164aa_208.png)

WH or something like that。 you would say that H。H。And C， N equals LSTM apply to H H 0， D。

 the depth element of that， C 0， D。And then WHHD， WIHD。And B。D right again， this is all conceptual。

 so I I might be making a typo here。Hopefully not， but。

We would finally compute some loss between our output and the input there and on the target there。

 L equals some loss， and then we would just say L dot backward and opt that step。



![](img/fedb479405b637e3d017ec260a8164aa_210.png)

Okay， so that would be our training of a deep LSTM。Okay。

 and that actually is infrastructurefr training except for one sort of subtle but actually very important point that comes up when training LSTMs。

 especially on very long sequences。So let's suppose that you had an LSTM training。



![](img/fedb479405b637e3d017ec260a8164aa_212.png)

And you want to train it over a sequence x。It goes from x1。You know， x2。All the way up to x， like 10。

000。You could just do this now I could call my same call I had before。

But it would probably run out of memory， right， because I'm creating， you know all。

 I have to maintain a memory around like because I'm running I'm running here kind of running this all in Autode framework。

 I have to keep around kind of all my intermediate states。So that when I call lost up。Backward。

 I can propagate through all of it。Right， and that's not very good， right。

 That's sort of a bad thing。 that's that's definitely going to be kind of a。You know。

 sort of a subop thing。 or we， we just can't do it。 And so there's a few options， right， we could。

 we could you know。Try to use a smaller network， just use smaller sequences， whatever。But。

The most common thing to do。Is to run again， what's called back propagation through time。

 So those those those training routines that we had you know。

 completing the gradient is taking a step， that's called back propagation through time。

But what we can do is just and what we can do with this procedure instead of running it through the entire time sequence of 10。

000 examples。We just take some length， like 100。And just sort of truncate there。

So there is obviously an x101。But I'm going to call my LSTM。Only on the I could be the loss。

Only on the first00。Okay， so again I'm just going to write this now in terms of a generic RNNs。

 so I'm only going to have one hidden state and even a single layer one。All right。

 so I generate those and I made some predictions from that。

But the point is I'm going to create my RNN。With just the first00 time steps。

 and I'll use like H zero， you know， normally like like like I would have all zero something like that because that's the start of the sequence。

Right。So just truncate things。I run my loss there。And now。I move to my next sort of sub sequence。

 let's say， you know。

![](img/fedb479405b637e3d017ec260a8164aa_214.png)

Something like 100 to hidden hiding up there， but fortunately， it's not too important。

So it would be 101。To say 200。喂。ITunk it again。AndSo I compute， no。My H。Hundred1。To。H 200。

And I compute my loss base on this， and I just do that。

This is a procedure kind of generally speaking called truncated back propagation through time because you take your whole sequence and you just sort of。

Chhoop it into chunks。And train the LSTM on these chunks。Now。

 you're rightly would sort of be right to kind of question whether this is a good idea or not， right。

 because I mean， after all， like there's a really important。Connection between those two things。

 like you're just ignoring it here， like you're just sort of throwing it out entirely。

 and so this seems like a really bad idea。But the reality is it's not that bad an idea。

 even just doing this where you just ignore entirely。

 just chop up into independent chunks and just train it entirely separately。

 that actually works probably okay， things aren't too bad but we can't make it just ever so slightly better than than just that。

And what we do to do that is a technique called hidden unit repackaging。So the idea here。

 the core intuition here is that when we started our LSTM， we started at this H0。

 which is just say equal to zero， we just initialize it， say with all zeros。

And when we trained this first portion， we just called it with the H0 again， this is sort of。

 you know， and by H0 here， I really mean， you know， this H0 fed into the into this function， right。

 that was just this。

![](img/fedb479405b637e3d017ec260a8164aa_216.png)

![](img/fedb479405b637e3d017ec260a8164aa_217.png)

Zero is at first。But then the question is when I feed in my H0 for this portion for training this next portion here。

What should I feed in my H0。I could feed in0 again， right， I could just treat the H0 again as0。

 you know， so basically feed， you would do something like， you know feed。H0 equals zero to there。

That would be fine， but we can do something a little bit better， right。

 We know the value of our hidden state and when for an LSTM。

 we know both the hidden and the and the cell state， of course， it's just this。

 We know sort of the last value of the hidden state in that sequence is just H 100。

 And so what we're going to do in。😊，In what's called hidden unit or hidden cell or hidden unit repackaging。

Is one take this value？And we're going to copy it。Into the H0 for this next sequence。

Okay now importantly， we are not。I'm going to draw this some like red or something like that。

 We are not。Actually creating one big long compute graph through this。

 what we're actually doing is is taking the value of H100 and feeding into the initial value of our next sequence。

Because of this， no gradients flow through this， so we don't get a sense of how will changing the weights affect how x100 affects H101。

 but we do see for the previous weights， right for the previous value of the weights。

 how is that x100， know whatever effect it has on H100 is propagated through for those that have seen sort of similar calls before this is also called a stop gradient call and things like this。

 you basically keep the value of your last hidden state as the initial value for your next sequence？



![](img/fedb479405b637e3d017ec260a8164aa_219.png)

But you don't。Proroppagate the full compute graph through。



![](img/fedb479405b637e3d017ec260a8164aa_221.png)

And that's the idea of hidden unit reppackaging。

![](img/fedb479405b637e3d017ec260a8164aa_223.png)

So what that looks like is actually very simple， what that looks like would be something like the following and you can actually even call it。

😊，You can actually even call it like you would with with a with a。



![](img/fedb479405b637e3d017ec260a8164aa_225.png)

![](img/fedb479405b637e3d017ec260a8164aa_226.png)

You can call it by sort of calling these training procedures as subroutines now and the way we kind of work is you would first define the initial H0 and C0 as zeros of some dimension right actually now officially abandon all attempts to write proper code here。



![](img/fedb479405b637e3d017ec260a8164aa_228.png)

![](img/fedb479405b637e3d017ec260a8164aa_229.png)

![](img/fedb479405b637e3d017ec260a8164aa_230.png)

And what I would do is I would sort of block my whole sequence。Into some number of blocks， right。

 So I would say something like rather than iterating over my whole time。

 I would say something like for I in the range of the number of blocks I have。

 That's the total number dimensions time divided by a block size。 Maybe I'll even write that。

 So like， you know， this is like sequence length。

![](img/fedb479405b637e3d017ec260a8164aa_232.png)

Length。Divided by。Block。Size。And what I would do is I would say， you know， I'll do a few things。

 first of all， first of all， I would actually sort of store the old hidden states here。

 so I would actually do something like store the hidden state I or D rather would be equal to like the last value of the hidden state here。

 this is a dot detaach。😊，Thatt copy or something like this， right？

So I'm going to detach it from my compute graph and then just copy the value and then same for。

For the hiddens， the cell state， this beN that deach。



![](img/fedb479405b637e3d017ec260a8164aa_234.png)

This is by the way， why Pytorch returned the last hidden state and the last cell state for the LSTM so you can detach them and repackage them for your training procedure。



![](img/fedb479405b637e3d017ec260a8164aa_236.png)

![](img/fedb479405b637e3d017ec260a8164aa_237.png)

![](img/fedb479405b637e3d017ec260a8164aa_238.png)

And then I always like return my hidden state and my C state。Okay， and so now on my training loop。

 I would sort of keep track of these things in my trained ELSTM， and I would feed into it。not。

The entire sequence， but just like the sequence of I times the block size to。

It's two like i plus one。Time of the block size。Right and then H0， C0。嗯。Why with the same size here。

And of course I could also include a batch I mean this is this is just the sequence dimension right。

 so this is like the first dimension there of course also are batch dimensions after this and then something like the WHH。

 WIHB。😊，So again， this is just sort of conceptual is down here。

But hopefully this convey is kind of the notion of what you actually mean when you want to really train a。



![](img/fedb479405b637e3d017ec260a8164aa_240.png)

LSTM on or really any RNN on a large sequence like this。

 what you want to do is you want to split it up into different blocks。

And you want to train each of these blocks。You，With gradients flowing through for just the block size。

But then rather than start completely anew with a brand new hidden state。

 you start with the previous hidden state and the previous cell state from LSTM。

 just a version that is kind of detached from the compute graph so you're just really copying the value。

 not the whole graph。Okay， and that is about what you need to know to implement the LSTM on your homework4 assignment。

So next lecturelet， we're going to move to our last sort of unit on different architectures and deep networks and talk about transformers。

 So see you all then。

![](img/fedb479405b637e3d017ec260a8164aa_242.png)
# 【麻省理工】高效机器学习 MIT 6.5940 EfficientML 2024 年秋季 p08 P08 Lecture 5 - Quantization Part I -BV1o7jzzwEST_p8-

Okay， welcome everybody， let's get started with lecture5 of Efficient M of AI。

 so today we are going to jump into a new chapter about quantization。So last lecture。

 we learned about cooling to reduce the number of parameters in an network。

If you think about the total size of a model of a neuralna model。

 that equal to the number of parameters times the bandwidth width。

 the number of bits per parameter right so you multily them together that gave you the total size of the model。

So if you want to reduce the size of the model on one side。

 we can reduce the number of parameters that is by using pruning。

And the other side would be trying to reduce the precision， the number of bits for each parameter。

 so that is quant。We are going to spend two lectures about composition， and here is our agenda。

We will first review the numeric type data types， including the integers， the floating points。

 the in8，32 and 16 and in4 and before。We are also going to learn the concepts of neural network pruning quantization。

Followed by three types of quantsition approach。So we are going to talk about K means based quantation and linear quantation today in the next lecture we are going to cover binaryry andterernary quantation。

So let's start with why do we need quantation？So a little bit operators are actually much cheaper。

 so if you compare the energy of the operation。The。From 8 bit to 32 bit， actually。

 the 8 bit integer operation is much cheaper compared with the 32 bit or the 32 bit integer operation or the 32 bit floating point operation。

That's from the operation perspective， from the memory perspective。

Every data movement is actually data movement is also quite expensive here。

 so each memory access equal hundreds of arithmetic operations so if you can reduce the size of the model we can reduce the memory traffic as well。

So less number of bandwidthwa will result in less energy consumption。

So' in order to understand how do we quantize neural networks， let's first talk about the data types。

 how is the numer data represented in modern computing system。So let's start with integer。

 Okay so integer is most common representation easiest representation。

 we have Einsign and also signed integer Okay so in the Einsstein version。

Each didnt represent total to power of zero to the power1 all way total the power of7 if we have anything things。

So this number I here represents 49。But these are hiinstein， if you want to add a signine base。

 we have one bit in the top so that the remaining bit ranges from2 to power to0 all the way through power of six。

And here we can find actually we have an overlap， both all the zeros and 10，00。

 they both represent zero。So in order to remove that duplication。

 a better way to represent a sign integer is by using this toolsth complement representation。

So what that means is the first bit actually means total minus total power of7 and the remaining bits are positive from total power0 total power1 to the power of six。

 only the first bit is total power of seven。In this case， 0，0，0 equal indicates 0， but 1，0，0。

0 no longer indicate0 by total power of。N minus1。With that， we can talk about fixed point number。

So here we have a decimal point。So this inal point about that， we have entered bit below that。

 we have a fraction bit。So from the smallest the mass mobility represents total power of zero and then total power of one。

맞아 맞아。Since this is too complement representation， the first bit is always negative。

And after the dense movement， it represents two of the power from minus-1 minus2 all the way with -4。

Another way to tell which number it represents is still using everything starting from zero。

 to2 power of zero， all the way to total power of six。把就失血。By the， the number of。Fraactctional bits。

 which is four so shift everything by four， and we can see the represented number is still the same using both interpretations。

So that's the F point number。Let's get more complicated to represent a larger range。

 larger dynamic range。People invented this floating point number。

And here we are showing example of 32 bits， floating point number in actually 7，54， so about 32 bits。

 we have one sign bits in the front。And then8 bit of exponent。

And then 23 bits of fraction is also called significant bit or the Matisza bit。

And the relationship between these list is that the definition of this number is。-1 to powers this。

Hey this is the sign base。The one plus the fraction of this。

It's a fraction date euro pi times two to the power of exponent minus the bias here the bias is 12。

And how is that calculated， we have8 bits of each exponent bit。

And the bias is calculated by2 to the power of the exponent bit minus1， minus1。So for eight bits。

 we have22 power of7 minus1， which is 1。7， which is a concept number。

As long as we are using 32 big floating point view。so fraction bit correspond to the yellow part。

 expon bit corresponding to the blue part。Given such definition。

 we can easily calculate how to represent this number。0。26，56，25。

The representation would be first converted into one plus fraction。One plus fraction。

 so the fraction here is 0102-625。So want point something。Times 2 to the power of minus-2。And here。

 since the bias is 127， the exponent bit should be 125。

So the exponent it should be 125 using this88 in blue， and then the 0。

0625 is represented by the1 and the fourth position。Right。So first。

 converted into one plus something to do the power of something？Any questions about this example？

说话说歌。So let's see how do we represent zero since if we have to be forced to use one plus something to represent a number。

 then how do we represent zero？Actually， people define this subnormal number。

 and previously we were talking about this representation actually。

Dction to the poweron minus the five。We we call it normal number。The4 doesn't equal to zero。

Here we design a special pace where it fallen bits the blue part。As we frozen to zero in that area。

 for particular for that area where exponent bits are zero， when you define it as sub normal number。

And the equation is a little different rather than one class correction here， we just use correction。

系。And rather than to power of exponant minus 127 here we。Have a two to power 1 minus127。

so the fraction bit is only variable here， we no longer have the expondent bit because here the expondent bit forced or frozen to be all zeros。

So now if the fraction bit is all0， then no matter if the sine bit is0 or1。

The final result would be zero。So that's how we represent zeros。

And how do we define those subnormal numbers？So let's see。

 what is the smallest and largest positive subnormal value using the subnormal representation on the rightt hand side？

So first of all， if it is a normal number， the only bit can not be zero。So in this example。

 the expondent bit is1 and then the fraction bit is0， so the number of B15 0？

Times2 to the power of1 minus 127。And the final result is total to power of-126。 so that's the。

Normal number for subnormal number， the exponent bit is pro than to be0。嗯。The fraction bit。给是万。

This is total power of。inus 23， so this is total power of minus23 times。Tot total power of minus 126。

 126， this is a constant because this is by definition， 1 minus 127。

So this is the smallest number we can represent。In the south normalmal region。So this is constant。

 this is also constant so only the fraction bit right here。

 so actually you can see this is very similar to the this is a linear representation。

so right here is grounding by here it being。What about the largest positive subnormal value？

So on the right hand side， we just feel all the fraction bit to be wire。In this stage。

 total power minus 23。Cl class to the power of。one， so sum sum it up。

 we get one minus to the power of minus 23。And then here we have the bias。

Time total power of minus126， that is the largest number we can represent in the soft normal region。

There are other two cases where if all the exp bit。Are all one。If the s bit is0。

 we use that to represent positive infinity。If the s beta is one。

 we use that to represent negative infinity。So that is the case。For representing the infin all the。

Fraracction bid has to be zero。배 has to be完。What about the s bit is one。

 but the remaining base is non zero， we use that to represent not a number。

So I say there is a big waste。Because no matter what the values are in the fraction bay。

 they all represent not a number。So actually we're going to revisit this in SA representation。

So these are two extreme cases for the mostly coming from an exponent bit， if they' are all zero。

 then that sub normal number， if they are all one， that use either infinity or not a number。

 depending on the fractional bit。Soan talk a lot。 Let's put summary right here。

To summarize what we have learned so far for the floating point representation。First。

 most most importantly。你ポーなで。The blue Park， right？If it is zero or if it' is9 zero。

 or if it is all what。9ine zero or not the largest number， then that's the normal okay。

 so the representation would be minus1 to power of sine bit one plus the fraction times2 total power of exp minus the bias that' a simple case。

And then we have two corner cases， if the exponent is all zero。

 then we will look at a fraction of bit。Zero， they represent zero， if they're not zero。

 then they are selfnmal numbers。So normal numbers representation differ by y。

One plus versus just ref fractionction right here。And here the constant is to to power of 1 minus 127。

 so that's exponentialon equal to zero。The third case the exponent is all what？

And that either represent positive or negative infinity or not a number。

 depending on the fraction of it。I mean， if you see the number of representation from small numbers to the largest number。

 we divide them into two rids。The soft normal values versus the normal values。

In the sub normal value， the distance between cent is constant is linear upon。

Versus in the normal value， the size become larger and larger。

So it's good at expressing very large numbers。So people have been keeping improving the efficiency by pushing the precision to lower and lower precision。

So。From attributeP32 to LP16 to B16。So the expondent width actually represent the range。

 how much range you can represent so that is。Using mostly by using the exposure。

And a fraction would it indicates the precision， indicates the precision。So for A 32。

 we have eight bits for the exponent。P3 bits for the fractional bits。

 and altogether we have 31 plus the first sign bit， altogether we have 32 bit。Well。

 for the I half precision， which is using 60bit to represent。We have less number of exponents。

 only five bits for exponent。And 1 bit for the fraction。AndLater， Google demanded this new type。

 which is BF16， bringing floatloat 16。And that is trying to match。第一。Exponent bits。

 not of the exponent bit， with the A 32， they are using both eight bits for the exponent。

And we sacrifice the precision。 It sacrifice the precision。By using fewer number， fewer number of。

Our fraction bits。So we have eight bits for the exponent seven bits for the fraction plus one bit on the top。

 altogether we have six。So notice the exposure for the P32 and Bf16 are the same。Therefore， usually。

 when we are training large scale neural networks， if P16 sometimes will diverge。

 then the good solution usually is to use PF16。Okay， so the question here。

 what is the following P16 number indenmo， so let's do a practice？We were given a。嗯。

Representation right here。5 bits of s1 bit of fraction， that's the standard IIIE P16 precision。

So for L 16， what is the bias？5 big phi minus1 is four total power4 minus1 that's 15。

 and so the pi should be 15。So we can use the equation， first of all， the sign bit。マナ。

And then the expent would be 10001 minus the bias right here， which is 17 minus5 15， which is 2。

And the next will be calculating the fraction bits。

The fractionction bill is one line followed by a bunch of zeros。

You find your representation that is 0。75。This 0。5， 0。25， adding them together， we have 0。2 plus 75。

And we use the equation， sign bit， one plus the fraction bit。Times took power of so。

It would probably be07 of5 it probably2， and altogether we have minus7。いんですか。So this。好。

F point number I should represent minus7。So let's do a reverse example。We have a bicycle number。

Which is two and a2。How to represented in brain F 16。I'll give you1 minute to think about it。

First of all， it' brain F 16。So it's one bit of signine base。

 a bit of exponent and seven be of fraction。The first thing would be to calculate the bias。

8 bit of exponent and the bias equal2 to the power of exponent minus1 minus-1。

Pal power 7 minus-1 plus 127。so we have a。Exponent bias。And remember。

 we have to represent the number by one point something into the power of something。So1 to1。25。

判 two to power one，该 two很快。And then we should represent。就是头发也很难说完。First of all。

 the assignment should be positive。And then the exponent binary。Right here is。

1 plus 127 because the final result should be1， and then the bias is 127。

 therefore the exponent binary should be 1 plus 127， which is 128。AndHow we represent 128？

It was a representation。Next。The fraction open bits。The fraction bits should be 0。25。Here is 0。

5 and here is 0。25， the final representation is 010。件。

So we can fill in 0100 to the fraction bits and fill in 1000 to the excluded bits and finally we have the。

Representation in BF16 for the number2 and2。Any questions here？对的。

So people want to continue to push the frontier by going here to lower and lower precision。

Newer the media has。Is FP8 using8 bit floating point to represent a number starting from the Hopper H100 GPU。

 so H100 was super popular。那个。Cic commodity these days at 100， 200 purely out of stock。

People are even using these GPSUs。Its collaterals to get financing。嗯。And recently。

 even before it's coming to the market， the blackwell B100。

你说你还 demand so what is actually happen here。So IP8 can further reduce the precision and increase the throughput。

Since we have so。So few number of bits， we have to be extremely careful how to allocate。

This number of picks。So first of all， we need a sign bit， so altogether eight bit。

 one business it designated for sign bit， so we are left with only seven bits。47 bits。

 we have so many choices， we can do0 plus seven，1 plus6， two plus。5，3 plus 4。Four3， et cetera。

So I trade these are the two popular views。You narrow precision fors。4 bit exponent Ri Mantia。

 E4 and 3， or E5 and2， five bits for the exponent and2 bits for the Mantia。

So what is a pros and cons？For E13 versus E5 and2。So remember the exponent bit。

It is for expressing larger magnitude。哎拉着 dynamic bridge。Versus the Matisa business is for precision。

So if we have five bits for exponent， and it's a larger dynamic fringe， a lower precision。

Whereasus E4 and3， we have a smaller dynamic range and a better precision。In this for this reason。

P8 in Fhaland， is really used for representing the gradient in the backward path。Okay。

 so one year later， I meanda has this black wh， okay， so black wh introduced IP4。

 four bit protein point。Is doubling or even making the through for even higher。

So with only four of it。We have how many choices we have。We can have these following four choices。

For these three threes。We can either have everything。As themanisa， okay， so no exponently。

 that's basically。So we can represent from zero to。2 seven for the Manza Park， plus the sign bit。

 we represent from minus8 all the way to plus 7， so that's 16 values to204 from minus8 to positive7。

These spaces are equally distance。linearer contactです。

So allocate those four bits another way to do1 one Im2， okay， we have one exp bit plus to my T bit。

And the number they can represent is actually very similar to in。

So we can have sub normalormal region where the exponentialonent is zero。

So we use this equation to look power the bias is 0， sub0。5。Versus the normal region one plus。

 so this is 0。75 times2 power of my 1 minus0 is3。5。So we can represent the numbers from 0 0。5。-1。

 minus-1。5 all the way to 3。5。so it's also linearly distance。So it's pretty much the same as in。

 except that they scale by 0。5。So E want2 is basically the same as seen4。Plus， it's wasting one slot。

 we have a positive zero and a negative zero。系い。So E1 m2 is the same as in4 except for that is wasting one slot for zero。

 it can represent。Rather than 16 numbers， it can represent 15 numbers because zero is overlap。

One plus two，我 can also have two plus one， so E E two and one。

Two bits for the exponent and only one bit for the Macquia。

 we can imagine this number will have a larger dynamic range。And less precision。

So we'll give two examples， 001 versus 111 so 001 that's in the sub normal region because has exponent bitta all0。

 so the equation will be like this， the bias would be 1， the fraction is also 1。

 so the number represented here is 0。5。For the normal region， the exponent is。3 and5 is one。

The Macquia is one， so it's one plus zero half。So this is one I mean is 0。5。

So this memory is actually what？大可以说下。Find the representation of all these values is actually from。0。

 half， one， one and half， or06。啊，你 go出。- zero， minus-1， minus-4， minus-3。

 minus- 12 and still in like00 and five。So indeed， it has a larger dynamic range it can represent all the wave to 12。

 rather than previously it can only represent all all the age of7。

So the extreme case would be using E3 and0， all the bits now becomes the exponent bits。So或者。

For these values and we have everything has exponent。

So this is a small whereas one exponent 1 minus-7， this is a big exponent7 minus3。

So we can see the representation as the largest。Wri is no longer equal distance。

These things become larger and larger， as said I and larger。

The largest video can represent here is 167。So that's the E3 and0。Okay。

 so so far we talked about everything about quantization about different numerical representations from in 8 toP32。

 MPP 16， B F16，P8， now IPP4 and in4， any questions so far？Good， with no question。

 let's move to the next part， what is compensation？

So quantization is a process of ensuring the input from a continuous and also large set of values to a discrete set of values。

For example， given this signal on the left hand side originally in the value is continuous。

And now we want to convert it to a discrete set。So， we。Dubine region by five lines，1， two， three。

 four，5。And we quantize the signal to the closest。Rdge， for example， can only from 0， this is 2，2，1。

0， minus-2，0。 Okay they are quantized to discrete value。Given this example。

 this is the original image。空 image。16 colors， you can see the color map becomes discrete。

And the difference between the input value and its quantas value is referred to as the quantization error。

 and our goal is try to minimize this quantization error。So this is the agenda for the lecture。

 so initially we start with something that is a floating point。

Using a floating form arithmetic to do the computation and using a floating point to represent the weights。

Then we're first going to introduce K means based quantization， so we have a code book。

Pobook there can be anything only store the index within that codebook。

So the storage is equal two parts。They their weights。

It's no longer14 point in integer together with a14 point of code。

And the computation will be done using floating point arithmetic。Sobody is good。In fact。

 so the good thing about it is that we are saving the storage by users in ways。

And the de is that we are not saving the documentation。

 we're still requiring to use the floating point arithmetic since we have the decoder weights。

So let's jump deeper into how do we deal with。This pay means contribution。This is example matrix。

A4 by four away the metrics。Representative。Using 32 floating points。

So we don't need the numbers to be so accurate。2。19，2。12，1。92，1 points。87。

We don't care at height precision， we can just approximate everything to two， okay。

 so that's the design philosophy。So what we do here is we do the K means classroom。To。呃上一。

A color to each value， for example， everything that is close to， we assign a blue color like 2。09，2。

12，1。921。87。And similarly， we do that for other colors。

 everything that's closer to that is very close to minus1。We看人估的。Part grid， 0。98，1。08，1。3，0。91。

 we all point0 from2 minus1。I classroom。So what we store here is the index into the centroid。

 okay so this is central0， central 123， so for this 2。

09 since this closer closes to the blue centroid and that blue centroid has index of three。

 so here we only need to store the index3 on the top。SoPrevious we are stor a 32 bit， 13。2。9。

 now we only store a2 bit integer index， but it's going to index into this code。Similarly。

 we can do it for the rest of the weights， let's to one more example， we have 1。48， 1。53， 1。49。

 they're all very close to 1。5。Where is 1。5， that's the second century？What is the index that is 2。

 so instead of floor 1。48， you sort the index2。Any one level of interaction。

So how do we reconstruct the weight matrix using the codebook？So on the red hand side。

 it's showing the reconstructed weights。So for example， here we have index1 and one。

 we look into the table one natural indicates zero， so we put0 in the corresponding location。

So we can now calculate the quant error， which is subtracting。

Between this original weight versus this writtencon weight。We can get this quantization  error。

What about the storage， so originally each bit， each weight is represented using 32 bit floating。

And how many manuals are there？We have four by four and that's 60 values。Al there's five。

 12 bits or 64 bytes since each byte equal to eight bits。What about after？So we have two portions。

 one is index， one is the centuriesries。For the index。How many bits do we have for each index？

Four values to two bit are enough to represent the index。How many indexes are there。

 we have 16 index。So altogether， 12 or2 times 16， we need only 32 bits。后面嘅班。Only four lits。

 is a lot smaller。Compared with the original storage。But don't forget。

 you also need to store the codebook。こボ。就是共。High precision。

So each entry in the codebook is represented there 32 bit。4 entries。So time four。

 I' watch my head bit。我。16een bikes。You can on the map， four bytes plus 16 bytes。Altogether。

 we need 20 biketes。Using this cameian classroom of quant。Which is about 3。

2 times smaller compared with the original size。So this is the。This is just an example case。

 in the calling scenario， assuming we have n bit quantization and the number of parameters equal to M。

 which is much larger than 2 to power of n。Which is all usually common in the case where we have。

Very big matrix， much larger than 16。I4 by four， but the code book is the same。In that case。

Originally， each weight is represented using 32 bit， and we M weights， we have 32 m bits。但说的。

AndN bits now nowadays， we have nbits， in this case， two bits。Two bits times M， so that's NM bits。

Plus。The codebook， each entry is using 32 bit， we have two power of N， here is total power of2。

 which is four entries in the codebook， so that's total power of N task。And plus  five bit。

And since M is much larger than2 to the power for N， we can ignore the second term。

So the compression ratio would be 32 divided by n times smaller。If N equal to two in this case。

 this matrix is super large。Then the saving would be 32 divided by 2 or 16 times。

If we have four bits， which we are going to implement that in the homework。We have four bids。

 we have 16 entries in the codebook， then was the conversion ratio。

That's 32 divided by 4 that's 8 bit compression， smaller。该收。This is representation。

 how do we fine tune the model that is quantized using K quantization。

 okay we will get a gradient matrix。So as about propagation， we got gradient matrix。

So we are going to color them using the same color as the weight。の。Green， red， blue， green， red。

 is the same color。And then we going to do a group by operation to group the same color together at zero point。

So these four blue valuess are grouped together。And these red values are grouped together。

 so corresponding they correspond to the same centroid， we're going to reduce them by suming them up。

 summing them up， and then modifiedpl by the learning rates subtracted from the original centroid。

 then we get the fine human centroid， so that's one equation of SGD on a K quantized neural network。

It refers to a group line operation and then do a reduction by some of the map multiplied by the ro rate that which aretract from the original century。

That will give you the update essentially。How does that work with respect to the accuracy。

 so this is showing the quantization only whether it model size， racial compression。

And go much smaller。And this is accuracy degradation and feel about 10%， 11%。

 we have very low accuracy degradation， and after that， the accuracy is through。Drop very quickly。

How does it compare with pruning only， so this line is showing the pruning only result in purple。

 and we can find that they are pretty much closer roughly around 10% the accuracy begins to drop。

But the good thing is that。Pruning and quantization can be combined together。

 And we can do both pruning and then quantization that gave you the highest concentration。

And just a few percent。The accuracy is too very well maintained， which is a book thing。

So practically should we do pruning first or should we do consation first？

What does the model size ratio mean in full quantization。

 so if the original model size is 100 megabytes now is 10 megabytes， then the ratio will be 10%。

If originally you are using 32 bit and the model is 100 mebyte， now you are using 8 bit。

 the model size will be 25 mebytes， and the ratio will be 25%。A means conservation by。The gradients。

你认不是。So actually that depends on the number the reduction can be done by let me see actually。

 right here we are calculatedulating the mean。I let me double check， this is just doing the song。

 I believe， yes， this is just doing the song because they are all updating to the same central。

A lot of people want to nudge the same central， therefore pre the mark。

Somehow they can be partially cancelled by quantifying with the learning rate。

 but really matters how many numbers will go through the same bucket。

The more number of you want to go into the same bucket， the more you want to match the weight。

 so therefore we are doing the sound。You're very welcome to try the。T to the mean average。

Thus the beauty of deep learning is not a fixed。Science or edge engineering。 So basically use the。

The method that works the best。Its not necessary is it best approach if that's just what I did。

In the paper，5 years ago。So back to our question， should we do pruning first or should we do quantization？

Right， that's the point since you want to do quantization pruning first because you want to first eliminate a lot of redundant weights okay so you have fewer number of weights to quantize reducing your workload to quantize and potentially reducing the quantization error。

 so first get rid of those redundant weights before the quant。

So this is the way distribution after fine tuning may prune the model。

Why there's a wind bump here because everything codes to zero are pruned。

Using our magnitude based pruning approach okay。Everything close to zero， they are set to zero。

 so these areas get flatter because after fine tu， they become flatter。

So what does it look like after quant， the values becomes discrete？

So rather than continuous distribution， they become theses， so only a couple of cent。

 this is centroid， this is one， this is not a one。そなのわ。Censroid the value becomes discrete。Quion。

Can you repeat the question。Any situation where quantization would be more preferable than pruning。嗯。

Depending on the pruning granularity， of course， growing the pruning。

I knew how the work acceleratedated。So its fact to combine them both。

 I don't see any scenario where you don't want to combine co brain pruning with quantization unless your hardware doesn't have any low precision unit。

你看我的都 cool。But I don't see a reason where you cannot do pruning but only do quantization at this you can do qua grain structured proof。

So the remaining weight are still best。Okay， so after the fineunion， we can see a slight difference。

Right here between these two slides， you can see the sunroid shifted a little bit。

第二第二个三 choice shift to the labor。That is due to when we are updating the weights。Right here。

 just quick question。We are cop gradient some the map since all these blue gradients are trying to update the blue centroid。

 we want to sum them map， apply the large， apply the change altogether to change this centroid。

AndCroid will get changed after a couple of inter iterations。And we， indeed。

Observed that change between these two sidess。This is before， this is after。

Before this is after you can see the slight change about the position of the century。

And another question is。Kd is the assignment。Able to get changed。 and that is so true。

 If the nudge is so big， one value might might also become another bucket。 So the assignment。

 the color assignment might also change。 we are going to implement that in lab2。

 which we are going to release next week。 actually， we are already release it。

 So feel free to try it out。To implement this K means quantization by yourself。And finally。

 how many bits do we need in practice previously we are showing two bits for illustration purpose。

 in practice we find for this for accident convolally before after four bits。

 the accuracy is going to drop very sharply， but before that the accuracy can be very boil。

For the absolute layers， after two bits， two bits。Before two bits。

 the accuracy is still well maintained for the top five and top five accuracy。

And you practice nowadays for large language models。We are going to see that you have four。

Forbit is very enough， is quite good maintaining the accuracy of large language models。

 is transforming models。So another idea。Proosing this deep compression paper is using halfmanco to further compress it since the weight distribution is now uniform。

 so some of the weights appear very frequently， some of the weight doesn't appear very frequently。

So we can encode the weights using different number of fields。Different weights。

They can use different variable length encoding。Fewer bids for the more frequently appearing one and use more number of bits for those or less frequently appear with。

So put them together， we have this three stage pipeline。

 for deep compression versus including to reduce the number of weights by。T model re it repeated。

And then by quantization， we first cluster the weights using K meanss。

A classroom generate a code book， 16 entries， four bits or four entries， two bits。

Then we quantize the widths with a code book， returntrain the code book， and repeat this process。

Finally， we can encode the weight using different bits for different weights。And as a result。

 we can achieve very high temperature pressure ratio across different neural nets。40 times 4 mass。

 39 times5， 35 times AlN， even the Google NsNe is compressed by order of magnitude。

I've visited the model science before and after the quant。

This is original accuracy and compressed accuracy。The accuracy can be very well maintained。

Even for very small and compact neural nets， like squeeze nets。

We're going to be introducing the newarchctic Hy search session。It's very small to begin with like 0。

47 megates。Begin with its4。 8 mi Bs to begin with。Compar with an Ana that is already 35 times smaller。

Thank think you two times smaller。with exactly the same accuracy。

But even that can be compressed by deep compressionion by a order of magnitude， so 10 times smaller。

Maintaining the accuracy while the model is only 0。47 megabytes and put in your pocket。快去。平民。

Okay just。Yes， that's the hyperparmeter and how to find that hyperparmeter。

 we' going to find where the accuracy is the drop。You know， the accuracy dropped at four bit。

 it's okay equal equal to 16。Hereafters the Dr Kbin。就可以这个付。We're going to play with that。question。

All right， so how do we compute on a k mean space the weight the quantization。

 we have to decomprise it by mapping it from the index into the original weight。

So here we have the code bone， we have the quantized way。

 we have the first decoded from unsigned ins， which is just the index into the floating point weight。

 and all the remaining operations will be done in floating point， so it save the storage。

 but it doesn't save the computation。But it's still very helpful for the modern transformers and large language models。

 because for single user for。generation phase is completely memory bounded， not compute bonded。

 So using F 16 is fully fine by reducing the。The memory footprint by four times compared with F 16。

 is super helpful。Okay， let's take a short break before we jump into the next part。

 which is linear quant。All right， welcome back。 So let's continue the discussion about。

A linear quant。 So now we want to use。啊庭去认为。A integer which to represent the values。

 and also we want to use the integer arithmetic。To do the computation so that we want to get acceleration and also get a storage safe。

So I see what is linear quant， this is very widely used if you're using a mobile phone running AI application locally and the highly possible linear quant is used here。

So what is linear quant。 So given。This is our familiar matrix， four by four weight matrix。

 so now we want to quantize them into only inteter values right here is。10 is minus211， minus1，0，00。

0 y equal to one。So now this is the quantized the version of the original matrix so 2。

09 becomes 1 minus 0。98 becomes minus2。So here we have two parameters where Im going to learn how to determine these parameters and let's just see how that works。

We have to define zero points and a scalr and a scale factor。So we multi or we subtract。

 the matrix was a zero point。Modify the scaling vector。And we get the reconstructed。With metrics。

So 2。09 becomes 2。14 minus 2。98， now becomes minus 1。07 and this is the quantization area。

 it's quite small， so there are roughly very well correlates between and after quantization。

So the magic here is how do we fund， how do we calculate？There's zero point。

2 big s integer versus scale， which is a 32 big poll hole number。说的是。0 point。And scaling factor。

 So we are going to map this integer value Q， integer value Q subtracted from the integer zero point。

And multily by the scaling factor， we get the protein point value。So basically z。

 which is the zero point。啊，那。Its allow a real number r equal to 0。

 which r equal to0 to be actually represented by a quantized integer Z， so z will be mapped to zero。

And then we have another scalingating factor to scale the dynamic range。

What that means is that we have a。F can point that any range from armine to arm max。

 this is the range shall build the weight values。We also have a dynamic range for the integer value from Q mean to Q max。

And the zero point maps z to zero from integer space to floating points。To points。R。

So this is corresponding to a different number of bits， you have two bits， the Q mean minus2。

 Q max equals to1， you have three bits or minus four to positive three。So the integer。

Q面 and Q max are fixed。So how do we calculate the scaling factor， Okay。

 so Q mean has to be mapped to R mean and  Q max has to be marked mapped to R max using the equation where we map Q max minus z go by S。

 we get R max。Q being minus z scaled by I， we get Rine， we can subtract them and then divide it。

 we can get the scalingkating factor equal to R max minus Rmin。Which is here。

X minusus R mean the dynamic range of the focan point range。

Divided by the Q max minus Q me the dynamic range of thete integers scale。はい。

So s can be calculated in this way， our max minus rv divided by 2 max minus 2b。So given our matrix。

 this is our familiar matrix， the max value is 2。12， me a is minus 1。08s。

 we use this equation to calculate the dynamic range the dynamic range of the floating point versus the dynamic range of the integer。

 and now we can get a scalingating vector would be 1。07。That's how we calculate the skin factor。

Now we can calculate the Z okay， so since we already have s， we can plug in s to get the Z。

And there has to be an integer， therefore we have to run it to the closest integer value。

In our example， QB is minus 1。08 in the right part， we plug in the equation and then we can。法庭修呃。

But you Q me， it was is minus2， sinceti only two bits。2 Army is  minus108。

as we already calculated is 1。07 we it to z。0 point is minus-。

So now let's talk about linear quantized matrix modification。 So how do we use integer unit。

 only use integer unit to calculate the matrix modification。

So linear quantization is an i find mapping from integers to real numbers using the equation we just talked about。

So consider the following。Mattrix modification y equals to W x。Originally。

 there are floating point values now we want to convert convert it into integer values。

 We are going to implement in the lab， so I will pay ready attention to the derivation。

For the remaining 20 minutes。So we plug the equation with R equal s times  Q minus z。

Times Q minus z output for the wave for the importer activation plug in。

 and then we rearrange them sub by moving S Y to the right hand side。

 moving z y to the right hand side。And then we can expand the equation from this role to this role。

All the way we get is four different terms， so far， very simple derivation。So we want to use M bit。

For example，8 bit。Integer modificationplication。I use 32 bit integer addition。To prevent overflow。

So first of all， the skating factor。And then we have this M integer addition。

 and then this yellow part are all constant， the weight is constant。The zero point is the constant。

ItPro zero point is constant， so all of these can be pre computed， it's not in the runtime。

 no runtime overhead and now let's focus on the scanning factor。So empirically。

 the scalingating factor is w is x divided by S y is between0 and1。

And from this paper here it can be represented by truth of the power of minus n times in value。

 a fixed point value between 0。5 and1。嗯。This modification can be done with a fixed point modification。

And the total power minus n can be done by a simple bit shift， so we don't need protein point unit。

最朋。It's blue part。So for this part， we scale them to em inte， this part can be precomputed。

And last part is the integer addition。And let's look at the middle part， the Zw times the  QX。

 so the zero point of the weight。What is distribution like？

So it's roughly following a normal distribution okay？So roughly centered around zero。

 so we can simply set zw to be0 because it's nervoussymmetric。Andだ。Roughly zero is map to zero。

 so we set zw to be 0。And what that mean is that originally Z map to0 now0 map to0 from。

The fixed point to the floating by range。In that case we can simplify the equation where now z becomes0。

 so the scaling factor will be using the actual value of the R divided by total to power n minus one much simpler calculation for the scaling factor。

 they have to do this calculation。To map it， now we just do a much simpler。C to market。So， we can。

Safely get rid of this。Green party。ZW is0， it's symmetric， okay then we are left to only。

these two terms。The first term， which is can be done by8 bit integer multiplication， the QX and QW。

 that's where the most of the weight lifting is happening in the computation。And we can。

 since D W is0， we are only left with a single term， these are constant because z is a constant。

Without to quant the weight， the weight is also constant。And we only left with the ZY。

And the blue part is the bulk of the computation where the bulk of the computation happens。

Now let's consider adding back。The bias， okay， so far we are ignoring the bias now we consider。

Following the fully connect layer with the bias。So the bias can be also with target equation right here。

 the bias can be also represented by subtraction the bias and then multiply with the scaling factor of that bias。

Since previously we mentioned Zw is 0， it' following in a normal distribution， we can set ZW to be 0。

 so integer 0 maps to the 1 floating。0。We can eliminate everything associated with the ZW。

 so we are left with the project here。We can force this sizeB。See you again。

The s factor for the bias versus the sian factor for weight and activation versus the ZB。

Similar to the weight the distribution of the bias is also following a normal distribution can so we can set z B to be0。

CB土。We force SG to be equal to Sw times Sx so that the equation can be simplified in this way。

 we absorb QB together with these two curve。Andhor， as PD photo， SW times S X。

So like this continuous elevation， we're going to move Sy to the right hand side and move z Y to the right hand side。

 so we are left with this equation。So QB zxqW quant wave the point of the activation。啊八月十号。

The biasers， they're all constant， so we can precompute them。

And we define the QB minus theqW to the Q bias， since it's a constant。

 then we can simplify all the equation to something like this。As look closer into this equation。

 the blue part is bulk of the computation， most of the weight this is happening in the blue part。

 but low bit integer modification。And we can rescaleale the scaling factor to n bit integer。

 like 8 bit integer followed by shift， we just discuss about it。And finally。

 we have M in teacher app。So now everything can be cast into a low precision integer operation。我的复议啊。

Use convolution rather than fully connectedly。Compared with fully connectedor layer。

 now we run the convolution， essentially， then revision is pretty much the same。

You're going to visit in the lab which just replace modificationplication with convol in Alin okay so flu part is where。

This green part is where most of the competition is happening。

So this is a computation diagram where we have previously the quantized weight。

 this is the quantized input activation， we do need to， the convolution was added with a bias。

 the sum in sum using a 32 bit register for the summation to prevent overflow so it it begins 32 bit in for the。

Subation register。Thesalm is thin in 32 bit。At the bias scale that the scaling factor and then add the zero point and finally we get the quant tie off。

So what's the difference with the payments quantization previously we are using？

32 floating point to do all the computation。 Now we will use the integer to do all the computation。

So we are saving not only the storage， but also we are saving the computer。

So we are going to implement this in lab two to make sure you understand the lecture here。

I'll pause a little bit for you to in case you have any questions for the derivation。the rain。Yeah。

 for red do we basically have nothing on the。Nothing on the on the left。

 So we are waitingting half of the dynamic range。If you set the buyers。

 the zero point of the buyers to be zero， which is this case。It weighs the half of the Bearick rich。

If no more questions， let's see， how does the accuracy compare with the floating point？

This figure is showing the floating point versus is basically。Okay。

 so this is the latency versus the accuracy。 ideally， we want something like the top left corner。

And consistently。It is having a better tradeoff on the plot compared with the IP。

The floating point counterpart， higher accuracy， same latency or same accuracy lower than。

On the left hand side， it's showing for random 2 is73， the floating point versus integer at risk。

And nowadays， this8 bit quantization becomes very mature。

Does the solution to accelerate and compress neural net。And most of the hardware have8 inte unit。

 so that's very widely used if you're using。Running neural nets on the phone。

 on a microcontroller on an edge device， this is a very critical solution。All right。

 so that concludes our second part， which is the linear quantization。

 so different from quantization which only save storage， but doesn't save computation。

 linear quantization can save both storage and the quantization。

So what is next can we go even lower precision， so we are going to talk about binary turnernary quantization in the next lecture。

 only use one bit or two bits to present each。Okay， so let's summarize today's lecture。

 we first reviewed， introduced the data types， floating point， what is integer。

 what is a floating point representation。What is the expondent bit， what is the Manquiza bit。

 what is sub normalormal region， how do we represent are big numbers， what is FP4， F8。

 different configurations， E2 M4。第三床。E5 and2， et cetera。

 And also we visited the basic concept of neuralnaural quantization to turn。

Convert weight and activations。To discrete values。And then we introduced two types of quantization。

 one is K beanss quantization， we're going to see them in the homework and also the linearium quantization。

 we went through a long derivation， make sure we can translate them into the code in map2。

And here are some references。呃。That's all for today's lecture。Thank you。


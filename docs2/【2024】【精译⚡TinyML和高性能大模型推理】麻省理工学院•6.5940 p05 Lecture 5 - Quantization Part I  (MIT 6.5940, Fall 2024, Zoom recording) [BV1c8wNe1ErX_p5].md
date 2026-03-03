# 【2024】【精译⚡TinyML和高性能大模型推理】麻省理工学院•6.5940 p05 Lecture 5 - Quantization Part I  (MIT 6.5940, Fall 2024, Zoom recording) [BV1c8wNe1ErX_p5]

Okay， welcome everybody， let's get started with lecture five of Eient ML AI。

 so today we are going to jump into a new chapter about quantization。

So last lecture we learned about footing to reduce the number of parameters in a neural network if you think about the total size of a model of a neural network of model that equal to the number of parameters times the bit width the number of bits per parameter right so you multiply them together that gave you the total size of the model。

So if we want to reduce the size of the model on one side， we can reduce the number of parameters。

 that is by using pruning and the other side will be trying to reduce the precision。

 the number of bits for each parameter so that is quantization。

We are going to spend two lectures about compensation and here is our agenda。

We will first review the numeric type data types， including the integers， the floating point。

 the inte8， at bit 32， at bit 16 at in4 and at before。

We are also going to learn the concepts of neuralnaural pruning quantization。

Followed by three types of quant approach。So we are going to talk about K means based quantization and linear quantization today in the next lecture。

 we are going to cover binary andterernary quantization。

So let's start with why do we need quantization？So little bit operators are actually much cheaper。

 so if you compare the energy of the operation from 8 bit to 32 bit。

 actually the8 bit integer operation is much cheaper compared with the 32 bit or the 32 bit in integer operation or the 32 bit rooting point operation。



![](img/042e2120f660692e50037b41ab6d208f_1.png)

![](img/042e2120f660692e50037b41ab6d208f_2.png)

That from the operation perspective， from the memory perspective。

 every data movement is actually data movement is also quite expensive here。

 so each memory memory access equals to hundreds of arithmetic operations so if you can reduce the size of the model we can reduce the memory traffic as well。

So less a number of bandwidthwa will result in less energy consumption。

So let's in order to understand how do we quantize neural networks。

 let's first talk about the data types， how is the numeric data represented in modern computing system？

So let's start with integer okay so integer is most common representation easiest representation we have ein signed and also signed integer okay so in the einsstein version each digit represents total power zero to power one all the way total the power of7 if we have eight bits right here so this number actually represent 49。



![](img/042e2120f660692e50037b41ab6d208f_4.png)

![](img/042e2120f660692e50037b41ab6d208f_5.png)

But these are einstein， if you want to add a sign bits with have one bit in the top so that the remaining bits ranges from two to power zero。

 otherwise with a power of six。

![](img/042e2120f660692e50037b41ab6d208f_7.png)

![](img/042e2120f660692e50037b41ab6d208f_8.png)

And here we can find actually we have overlap， both of zeros and 1000， they both represent zero。



![](img/042e2120f660692e50037b41ab6d208f_10.png)

![](img/042e2120f660692e50037b41ab6d208f_11.png)

So in order to remove that duplication， a better way to represent a sign integer is by using this tools complement representation。



![](img/042e2120f660692e50037b41ab6d208f_13.png)

So what that means is the first bit actually means total minus22 power of seven okay and the remaining bits are positive from total power zero to the power one to two power of six。

 only the first bit is total power of seven。

![](img/042e2120f660692e50037b41ab6d208f_15.png)

![](img/042e2120f660692e50037b41ab6d208f_16.png)

In this case， 000 equal indicate 0 but 1000 no longer indicate0 by total to power of n minus one。



![](img/042e2120f660692e50037b41ab6d208f_18.png)

With that， we can talk about fixed point number， so here we have a decimal point。



![](img/042e2120f660692e50037b41ab6d208f_20.png)

So this decimal point above that， we have the integer bit below that， we have the fraction bit。

So from the smallest density mobility represents total to the power of zero and then total to the power of one going larger and larger。

Since this is to complement representation， the first fit is always negative。

And after the decimal bid， it represents total the power from minus1。

 minus2 all the way to minus4 in this case。

![](img/042e2120f660692e50037b41ab6d208f_22.png)

Another way to tell which number it represents is still using everything starting from zero。

 total power of zero， all the way to total power of6。



![](img/042e2120f660692e50037b41ab6d208f_24.png)

A to shift it by the number of。Fraactctional bits， which is four and to shift everything by four and we can see the represented number is still the same using both interpretations。



![](img/042e2120f660692e50037b41ab6d208f_26.png)

So that's the fifth point number。Let's get more complicated to represent a larger range。

 larger dynamic range。People invented it floating point number and here we are showing example of 32 bit。

 floating point number in actually 754 okay， so among these 32 bits we have one sign bits in the front。



![](img/042e2120f660692e50037b41ab6d208f_28.png)

And then8 bits of exponent。And then 23 bits of fraction is also called significant bit or the Montetia bit。



![](img/042e2120f660692e50037b41ab6d208f_30.png)

The relationship between these bits is that the definition of this number is minus one to or s bits。



![](img/042e2120f660692e50037b41ab6d208f_32.png)

And this is the sign bit。The one plus the fraction bit， this is the fraction bit。

 yellow pie times2 to the power of exponent minus the bias here the bias is 127。

And how is that calculated， we have8 bits of an exponent bit。

And the bias is calculated by2 to the power of exponent bit minus1 minus1 so for eight bits。

 we have two to power of seven minus1， which is127， which is a constant number。

 as long as we are using 32 bit floating point new presentation so fraction bit correspond to the yellow part exponent bit correspondinging to the blue part。



![](img/042e2120f660692e50037b41ab6d208f_34.png)

Given such definition， we can easily calculate how to represent this number。



![](img/042e2120f660692e50037b41ab6d208f_36.png)

0。265625。

![](img/042e2120f660692e50037b41ab6d208f_38.png)

The representation would be first converted into one plus fraction， one plus fraction。

 so the fraction here is 0。02625。

![](img/042e2120f660692e50037b41ab6d208f_40.png)

One point， something。Times two to the power of minus2。AndHere， since the bias is 127。

 the exponent bit should be 125， so the exponent bit should be 125 using these eight bits in the blue and then the 0。

06 to5 is represented by a1 the fourth position。

![](img/042e2120f660692e50037b41ab6d208f_42.png)

嗯。So first， converted into one plus something to do the power of something， okay？

Any questions for this example。说放首歌。All right。So let's see how do we represent zero since we have to if we have to be forced to use one plus something to represent a number and then how do we represent zero？



![](img/042e2120f660692e50037b41ab6d208f_44.png)

![](img/042e2120f660692e50037b41ab6d208f_45.png)

Actually people define this subnormal number previously say we were talking about this representation okay well I'm flat fraction to the power of exponentialon and minus the bias we call it normal numbers sp doesn't equal to zero。



![](img/042e2120f660692e50037b41ab6d208f_47.png)

Here we design special pad where the explosion bits of blue Park。As we frozen to zero in that area。

 for particular for that area where exponent bits are zero， we defined it as subdomormal numbers。

And the equation is a little different， rather than one past fraction here， we just use fraction。

Okay and rather than two power of exponent minus 127 here we need。

Have a total power1 minus 127 so the fraction bit is only variable here we no longer have the expondent bit because here the expondent bit are force but frozen to be all zeros。



![](img/042e2120f660692e50037b41ab6d208f_49.png)

![](img/042e2120f660692e50037b41ab6d208f_50.png)

So now if the fraction bit is all0， then no matter if the s bit is0 or1。

The final result would be zero。

![](img/042e2120f660692e50037b41ab6d208f_52.png)

So that's how we represent zeros and how do we define those subnormal numbers？So let's see。

 what is the smallest and largest positive subnormal value using the subnormal representation on the right side？

So first of all， if it is a normal number right the exponent bit and L is0 okay so in this example。

 the exponent bit is1 and then the fraction bit is0 so the number of B1 plus0 times22 power 1 minus now 127。



![](img/042e2120f660692e50037b41ab6d208f_54.png)

![](img/042e2120f660692e50037b41ab6d208f_55.png)

![](img/042e2120f660692e50037b41ab6d208f_56.png)

And the final result is total power of-126。 So that's the normal number for sub normalormal number。

 the expondent bit is frozen to be 0。 Can you only be。



![](img/042e2120f660692e50037b41ab6d208f_58.png)

![](img/042e2120f660692e50037b41ab6d208f_59.png)

The fraction days。Is what relative。And this is total power of。in- 23， so this is total power of。

Mus 23 times total total power of minus 126， 126， this is a constant because this is by definition。

  one minus 127。

![](img/042e2120f660692e50037b41ab6d208f_61.png)

![](img/042e2120f660692e50037b41ab6d208f_62.png)

![](img/042e2120f660692e50037b41ab6d208f_63.png)

Okay， so this is the smallest number we can represent。



![](img/042e2120f660692e50037b41ab6d208f_65.png)

The soft normal region。So this is constant， this is also constant。

 so only the fraction bit right here， so actually we can see this is very similar to the this is a linear representation。



![](img/042e2120f660692e50037b41ab6d208f_67.png)

so right here is now nearby here it's vi。What about the largest positive subnormal value Okay so on the rank hand side we just feel all the fraction bit to be one and in this case to power minus23。



![](img/042e2120f660692e50037b41ab6d208f_69.png)

Plus plus total power of minus1， so sum sum it up， we get one minus total power of minus 23。

And then here we have the bias times total power of minus 126。

 that is the largest number we can represent in the soft normalmal region。



![](img/042e2120f660692e50037b41ab6d208f_71.png)

![](img/042e2120f660692e50037b41ab6d208f_72.png)

There are other two cases where if all the exponent bit。Are all one？If the sine be0。

 we use that to represent positive infinity。If the sign bit is y。

 we use that to represent negative infinity。

![](img/042e2120f660692e50037b41ab6d208f_74.png)

so that is the case for representing the infinity， or the fraction bit has to be zero。

 or the sign of the exponent bit has to be one。

![](img/042e2120f660692e50037b41ab6d208f_76.png)

What about the s bit is one， but the remaining base is90。

 we use that to represent not a number okay so I there is a big waste because no matter what the values are in a fraction bit。

 they all represent value not a number。

![](img/042e2120f660692e50037b41ab6d208f_78.png)

So actually， we are going to revisit this E SP8 representation。



![](img/042e2120f660692e50037b41ab6d208f_80.png)

So these are the two extreme cases for the mostly coming from an exponent bit， if they're all zero。

 then that subnmal number， if they're all one， there is either infinity or not a number depending on the fractional bit。



![](img/042e2120f660692e50037b41ab6d208f_82.png)

So we can talk a lot。 Let's put a summary here。To summarize what we have learned so far for the floating representation。



![](img/042e2120f660692e50037b41ab6d208f_84.png)

First， most importantly。Exoding bit the blue part right if it is zero or if it is9 zero or if it is all what okay if it is。

9 zero or not the largest number， then that's the normal level okay。

 so the representation would be minus one to the power of sign bit one plus the fraction times to the power being exponent minus the bias that's the simple case。

And then we have two corner cases if the exponent is all zero。

Then we will look at the fractional bit， because there's zero， then represent represent zero。

 if they're not zero， then there are subnomal numbers。

So no numbers representation differ by one one plus versus just ref fractionction when here and here the constant is total to power of 1 minus 1207。

Okay so that's the exponent equal to zero。Third case is exponent is all what， okay？

And either represent positive or negative infinity or not a number， depending on the fraction of it。



![](img/042e2120f660692e50037b41ab6d208f_86.png)

![](img/042e2120f660692e50037b41ab6d208f_87.png)

And if you see the number of representation from small number to the largest number。

 we divide into two rids。The sub normal values versus the normal values。In the sub normal value。

 the distance between cent is constant is linear context versus in the normal value。

 the size become larger and larger。

![](img/042e2120f660692e50037b41ab6d208f_89.png)

So it's good at expressing very large numbers。So people have been。

In keeping improving the efficiency by pushing the precision to lower and lower precision。



![](img/042e2120f660692e50037b41ab6d208f_91.png)

So from IPP32 toP16 to B flow 16。

![](img/042e2120f660692e50037b41ab6d208f_93.png)

So the exponent width actually represent a range， how much range you can represent。

 so that is using mostly using the exponent。

![](img/042e2120f660692e50037b41ab6d208f_95.png)

And a fraction width indicates the precision indicates the precision。



![](img/042e2120f660692e50037b41ab6d208f_97.png)

So for AP 32， we have eight bits for the exponent and 23 bits for the fractional bits。

 and altogether we have 31 plus the first sign bit， altogether we have 32 bits。



![](img/042e2120f660692e50037b41ab6d208f_99.png)

![](img/042e2120f660692e50037b41ab6d208f_100.png)

Well， for the I half precision， which is within 16 bit to represent。

 we have less number of exponents， only five bits per exponent。



![](img/042e2120f660692e50037b41ab6d208f_102.png)

And 10 bits for a fraction。

![](img/042e2120f660692e50037b41ab6d208f_104.png)

Later， Google demanded this new time， which is B F16 brain floatloat 16。



![](img/042e2120f660692e50037b41ab6d208f_106.png)

And that is trying to match the。Exponent bit， number of exponent bits with the RP 32。

 they are using both8 bits for the exponent。We sacrifice the precision， we sacrifice the precision。



![](img/042e2120f660692e50037b41ab6d208f_108.png)

By using fewer number of fraction bits， so we have eight bits for the exponent seven bits for the fraction plus one bit on the top。

 altogether we have 16 bits。

![](img/042e2120f660692e50037b41ab6d208f_110.png)

![](img/042e2120f660692e50037b41ab6d208f_111.png)

So notice the exponent bit for the IP32 and Bf16 are the same。Therefore。

 usually when we are training a large scale of neural networks， if FP16 sometimes we' diverge。

 then the good solution usually is to use EF16。Okay， so a question here。

 what is the following FP16 number in D， so let's do a practice？We were given a。



![](img/042e2120f660692e50037b41ab6d208f_113.png)

Representation right here， we have。F bit of1 fraction， that's the standard atOEP16 precision。

So for IPP 16， what is the bias？five bits，5 minus one is4 total power4 minus1 that's 15。

 hence the pi should be 15。

![](img/042e2120f660692e50037b41ab6d208f_115.png)

![](img/042e2120f660692e50037b41ab6d208f_116.png)

So we can use the equation first off， all the sine bit is minus when the exponent would be 10001 minus the bias right here。

 between is 17 minus 5 15， which is 2。

![](img/042e2120f660692e50037b41ab6d208f_118.png)

And the next we'll be calculating the fraction bits。

 the fraction bit is  one1 followed by a bunch of zeros。



![](img/042e2120f660692e50037b41ab6d208f_120.png)

In binary a representation that is 0。75， so this is 0。5， 0。25， adding them together， we have 0。2。

7 five。

![](img/042e2120f660692e50037b41ab6d208f_122.png)

![](img/042e2120f660692e50037b41ab6d208f_123.png)

And we use the equation sign bit one plus the fraction bit times total total power of spoonent bit。

 it would plug in the max cell I would plug two， and altogether we have minus seven。



![](img/042e2120f660692e50037b41ab6d208f_125.png)

In this case， so if。哦。F point number I should represent minus7。The next two word reverse example。

We have a decimal number， which is two and half。Outre in brain Ft 16。

I'll give you one minute to think about it。First of all， it's brain float 16 right。

 so it's one bit of sign bit， eight bit of exponent and seven bit of fraction。

The first thing would be to calculate the bias， right？



![](img/042e2120f660692e50037b41ab6d208f_127.png)

A bit of exponent and the biaser equal total power。Exponent -1，-1 total power 7-1 plus 1，27。 Okay。

 so we have the。

![](img/042e2120f660692e50037b41ab6d208f_129.png)

Exponent bias。

![](img/042e2120f660692e50037b41ab6d208f_131.png)

And remember， we have to represent the number by one point something to the power of something。Also1。

25， I heard。

![](img/042e2120f660692e50037b41ab6d208f_133.png)

Times 2 to power1， that is 2。5。And then we should represent02 five and also what。First of all。

 the assignment should be positive。And then the expdent binary right here is。



![](img/042e2120f660692e50037b41ab6d208f_135.png)

One plus 127 because the final result should be one and then the bias is 127。

 therefore the expdent binary should be1 plus 127， which is 128。



![](img/042e2120f660692e50037b41ab6d208f_137.png)

All would represent 128， so this is a representation。Next。The fractional bits， okay。

 the fraction bits should be 0。25， which is。

![](img/042e2120f660692e50037b41ab6d208f_139.png)

Here is 0。5 and here is 0。25， the binary representation is 01，000 bunch of zeros。



![](img/042e2120f660692e50037b41ab6d208f_141.png)

So we can fill in 0100 to the fractionction bits， building in 1000 to the exponent bits。

 and finally we have the representation in BF 16 for the number12。



![](img/042e2120f660692e50037b41ab6d208f_143.png)

![](img/042e2120f660692e50037b41ab6d208f_144.png)

Any questions here？对，6。So people want to continue push the frontier by going fuel to lower and lower precision so later Dominia has this FP8 using 8 bit floating point to represent a number starting from the hopper H100 GPU so H100 was super popular in the C committee these days H100200 purely auto stock and people are even using these GPUs it's collaterals to get financing。

嗯。AndRecently， even before it's coming to the market， the blackwell B100 in high demand。

 so what is actually is happening here？So IP8 can further reduce the precision and increase the through force。

Since we have so。So few number of bits， we have to be extremely careful how to allocate this number of bits。

So first of all， we need a sign bit， so altogether eight bit， one bit is designated for sign bit。

 so we are left with only seven bits。For the seven bits， we have so many choices。

 we can do zero plus seven， one plus6， two plus five， three plus four。For or three， et cetera。

So actually， these are too popular used。

![](img/042e2120f660692e50037b41ab6d208f_146.png)

In numerical precisions for IPAs。4 bit exponent， Riby Mantia， E4 and3 or E5 and two。

 five bits for be exponent and two bits for the Mantia。



![](img/042e2120f660692e50037b41ab6d208f_148.png)

So what is the pros and con？For E4 and3 versus E5 and two。Remember the exponent bit。

It is for expressing larger magnitude。诶， larger dynamic bridge。



![](img/042e2120f660692e50037b41ab6d208f_150.png)

Versus the Manteza bed is for precision， so we have five bits for exponent。

 that's a larger dynamic fri， a lower precision。

![](img/042e2120f660692e50037b41ab6d208f_152.png)

Whereus E43， we have a smaller dynamic range and a better precision。



![](img/042e2120f660692e50037b41ab6d208f_154.png)

In this for this reason， define find who is really used for representing the grid in the backward class。



![](img/042e2120f660692e50037b41ab6d208f_156.png)

Okay， so one year later， A has this blackwell okay so blackwell introduced IP44 bit floating point is doubling or even making the through for even higher okay。

So with only four bits， we have how many choices do we have？We can have these volume four choices。



![](img/042e2120f660692e50037b41ab6d208f_158.png)

For these three threes。We can either have everything。As themanza， okay， so no exponent wave。

 that's basically into4。So we can represent from zero to to seven for the mentea part plus the sign bit。

 we can represent from minus8 all the way to class7 okay。

 so that's 16 values to two color4 from minus8 to positive seven。



![](img/042e2120f660692e50037b41ab6d208f_160.png)

And these spaces are equally distanced， so it's linear context。



![](img/042e2120f660692e50037b41ab6d208f_162.png)

To allocate those four bits， another way is to do11 and2， and we have one expent bit。

 but to my Ts bits。

![](img/042e2120f660692e50037b41ab6d208f_164.png)

And the number they can represent is actually very similar to in number。

 so we can have sub normalormal region where the exp is zero。



![](img/042e2120f660692e50037b41ab6d208f_166.png)

So we use this equation to power the bias 0， so this is 0。5 versus the normal region one plus。

 so this is 0。75 times total power of 1 minus0 is3。5。



![](img/042e2120f660692e50037b41ab6d208f_168.png)

So we can represent the numbers from 0 0。5， minus1， minus 1。5 followed the way to 3。5。



![](img/042e2120f660692e50037b41ab6d208f_170.png)

![](img/042e2120f660692e50037b41ab6d208f_171.png)

Okay， so it's also linearly distanced， so it's pretty much the same as in4 except that we are scaled by 0。

5。

![](img/042e2120f660692e50037b41ab6d208f_173.png)

Okay， so Yan2 is basically the same as in full。Plus， it's wasting one slot。

 you have a positive zero and a negative zero。

![](img/042e2120f660692e50037b41ab6d208f_175.png)

8。😊，So U1M is the same as in four except for that is wasting one slot for zero， it can represent。

Rather than 60 numbers， they can represent 15 numbers because zero is overlap。



![](img/042e2120f660692e50037b41ab6d208f_177.png)

One plus two， we can also have two plus one and so E E two and y。

 two bit for the exponent and only one bit for the Mata。

 we can imagine this number will have a larger dynamic range and less precision。

So we'll give two examples001 versus 111 okay， so 001 that's in the subn normalmal region because the exponent bits are r0。

 so the equation will be like this， the bias would be one。The fraction is also one。

 so the number of the diameter here is 0。5。For the normal region， the exponent is3 and the five is1。

 the mantea is1， so it's one plus 0 and2， so this is one minus is 0。5。

 so this number is actually1 okay。

![](img/042e2120f660692e50037b41ab6d208f_179.png)

In that case， we can find the representation for all these values， especially from。



![](img/042e2120f660692e50037b41ab6d208f_181.png)

嗯。0ero， half， one， one and a half， on six。

![](img/042e2120f660692e50037b41ab6d208f_183.png)

And we go to。

![](img/042e2120f660692e50037b41ab6d208f_185.png)

- zero， minus1， minus4， minus3， minus- 12 and scaled it by and zero and five。



![](img/042e2120f660692e50037b41ab6d208f_187.png)

So indeed， it has a larger dynamic range it can represent all the way to 12 rather than previous it can only represent all all the way to seven。



![](img/042e2120f660692e50037b41ab6d208f_189.png)

![](img/042e2120f660692e50037b41ab6d208f_190.png)

So the extreme case will be using E3M0 and all the bits becomes now becomes the exponent bit。



![](img/042e2120f660692e50037b41ab6d208f_192.png)

![](img/042e2120f660692e50037b41ab6d208f_193.png)

So for these values， we have everything as exponent。



![](img/042e2120f660692e50037b41ab6d208f_195.png)

So this is a very small exponent，1 minus seven， this is a big exponent， seven minus three。



![](img/042e2120f660692e50037b41ab6d208f_197.png)

哎。So we can see the representation as the largest dynamic which is no longer equal distance。

 but the distance becomes larger and larger as the value and larger。



![](img/042e2120f660692e50037b41ab6d208f_199.png)

The largest value pillar present here is 167。

![](img/042e2120f660692e50037b41ab6d208f_201.png)

嗯。So that's the E3 and0。Okay， so so far we talk about everything about quantization about different numerical representations from into8 to FP32。

 FP 16， Bf 16， FP 8， now IP4 and84， any questions so far？Okay， good， no question。

 let's move to the next part， what is computation？So quantization is the process of innstruing the input from a continuous and also large set of values to a discrete set of values。

 for example given this signal on left hand side originally the value is continuous。

And now we want to convert it to a discrete set。So we divide region by five lines， a one， two， three。

 four， five。And we quantize the signal to the closest rid， for example， only from zero， this is2，2，1。

0 minus2，0 okay， they are quantize to discrete value。



![](img/042e2120f660692e50037b41ab6d208f_203.png)

![](img/042e2120f660692e50037b41ab6d208f_204.png)

Given this example， this is the original image， this is a quantized image in 16 colors。

 you can see the other map becomes discrete。And the difference between the input value and its quantized value is referred to as the quantization error。

And our goal is try to minimize this quantization error。So this is the agenda for the lecture。

 so initially we start with something that is a floating point using point arithmetic the computation and using floating point to represent the weights。

Then we're first going to introduce k means based quantization， so we have a code book。Or codebook。

 that can be anything only store the index within that codebook。



![](img/042e2120f660692e50037b41ab6d208f_206.png)

So the storage is including two parts， the integer weights。It's no longer 14。

8 integer together with a 14 point code。

![](img/042e2120f660692e50037b41ab6d208f_208.png)

And the computation will be done using floating point arithmetic in this case。

So what is good and bad， so the good thing about it is that we are saving the storage by using integer ways。



![](img/042e2120f660692e50037b41ab6d208f_210.png)

And the limitation is that we are not saving the limitation。

 but still requiring to use the floating point arithmetic since we have a deco of it。



![](img/042e2120f660692e50037b41ab6d208f_212.png)

So let's deeper her into how do we deal with this he means quant。This is an example matrix。

 a four by four weight matrix。

![](img/042e2120f660692e50037b41ab6d208f_214.png)

Represented into using a 32 bit proteinte point。

![](img/042e2120f660692e50037b41ab6d208f_216.png)

So we don't need the numbers to be so accurate， we have 2。09， 2。12， 1。92，1。87。

We don't care such high precision， we can just approximate everything to two， okay。

 so that's the design philosophy。So what we do here is we do the K means classroom。To。

Assign a color to each value， for example， everything that is close to we assign a blue color like 2。

19，2。121。921。87 okay。

![](img/042e2120f660692e50037b41ab6d208f_218.png)

![](img/042e2120f660692e50037b41ab6d208f_219.png)

![](img/042e2120f660692e50037b41ab6d208f_220.png)

And similarly， we do that for other colors， everything that's closer to that is very close to minus one。

We color them in gray。

![](img/042e2120f660692e50037b41ab6d208f_222.png)

It would color the mean grid like 0。98， 1。08，1。13，0。91， we all quant them to minus1 by classroom。



![](img/042e2120f660692e50037b41ab6d208f_224.png)

So what we store here is the index into the centroid， okay， so this is central0， central 123。

 so for this 2。09 since it's closer poses to the blue centroid and that blue centroid has index of three。

 so here we only need to store the index three on the top。



![](img/042e2120f660692e50037b41ab6d208f_226.png)

![](img/042e2120f660692e50037b41ab6d208f_227.png)

Previously we are storing a 32 bit floating point2。09。

 now we only store a2 bit integer index that is going to index into this code。



![](img/042e2120f660692e50037b41ab6d208f_229.png)

![](img/042e2120f660692e50037b41ab6d208f_230.png)

Similarly， we can do it for the rest of the weights， next to one more example， we have 1。48， 1。53， 1。

49， they're all very close to 1。5。

![](img/042e2120f660692e50037b41ab6d208f_232.png)

Where is 1。5 that's the  second century。What is the index that is true so instead of Storing 1。48。

 we store the index to in one level of indirect。

![](img/042e2120f660692e50037b41ab6d208f_234.png)

So how do we reconstruct the weight matrix using the codebook？So on the right hand side。

 it's showing the reconstructed weights。

![](img/042e2120f660692e50037b41ab6d208f_236.png)

Okay， so for example， here we have index one and one。

 we look into the table one actually indicates zero， we put zero in the corresponding location。



![](img/042e2120f660692e50037b41ab6d208f_238.png)

![](img/042e2120f660692e50037b41ab6d208f_239.png)

So we can now calculate the quant error， which is subtracting。



![](img/042e2120f660692e50037b41ab6d208f_241.png)

Between this original weight versus this reconstructed weight， and we can get this quant error。

What about the storage， so originally each bit， each weight is represented using 32 bit floating point。

And how many values are there？We have four by four that's 16 by， altogether that's 5。

 12 bits or 64 bytes since each by equal to8 bits。What about after？So we have two portions。

 one is index， one is the centrals for the index。

![](img/042e2120f660692e50037b41ab6d208f_243.png)

How many bits do we have for each of the next？Po values so two biting are enough to represent the index。



![](img/042e2120f660692e50037b41ab6d208f_245.png)

How many indexes are there， we have 16 index。So altogether， about 12 or two times 16。

 we need only 32 bits。

![](img/042e2120f660692e50037b41ab6d208f_247.png)

How many bytes are there， only four bytes， it is a lot smaller compared with the original storage。



![](img/042e2120f660692e50037b41ab6d208f_249.png)

But don't forget， we also need to store the codebook。



![](img/042e2120f660692e50037b41ab6d208f_251.png)

So a foot book。It's full point。Iigh precision so which ensure in the codebook is representative user there so good。

We four entries okay two times 4 those 128 bits。

![](img/042e2120f660692e50037b41ab6d208f_253.png)

Or six impacts。If we sum them up， four bytes plus 16 bytes。Altogether。

 we need 20 bikes using this K means classroom compensationden。Which is about 3。

2 times smaller compared with the original size。So this is the。

This is just an simple case in a common scenario， assuming we have n bit quant and the number of parameters equal to m。

 which is much larger than total power of n， which is usually common the case where we have。



![](img/042e2120f660692e50037b41ab6d208f_255.png)

Very big matrix， much larger than 16 than four by four， but the old book will the same。



![](img/042e2120f660692e50037b41ab6d208f_257.png)

In that case， originally， each weight is represented using 32 bit M weights， 32 m bits。



![](img/042e2120f660692e50037b41ab6d208f_259.png)

After that， we have。啊。And Mbits， now nowadays， we have Mbits， in this case， two bits。

Two bits times m， so that's an m bits。Plus。The codebook， each entry is using 32 bit。

 we have total power of N here is total power of2， which is four entries in the codebook。

 so it has total power of n n plus five bits。

![](img/042e2120f660692e50037b41ab6d208f_261.png)

And since M is much larger than two to the power of N， we can ignore the second term。

So the compression ratio would be 32 divided by n times smaller。If n equal to2 in this case。

 this matrix is super large， the the saving would be 32 divided by2 thats 16 times。



![](img/042e2120f660692e50037b41ab6d208f_263.png)

![](img/042e2120f660692e50037b41ab6d208f_264.png)

If we have four bits， which were going to implement that in the homework。



![](img/042e2120f660692e50037b41ab6d208f_266.png)

We have four bids， we have 60 entries in the plugbook， then with the conversion ratio。

Is 32 divided by4 and'8 big compression， smaller。

![](img/042e2120f660692e50037b41ab6d208f_268.png)

Thank you。This is representation， how do we find tune the model that is quantized using any quantization？

We will get a gradient matrix。

![](img/042e2120f660692e50037b41ab6d208f_270.png)

So after that propagation， we've got a gradient matrix。

So we are going to color them using the system color as the weight okay。So blue， green， red， blue。

 green red， using the same color， and then we' going to do a group by operation to look the same color together so these four blue values are grouped together。



![](img/042e2120f660692e50037b41ab6d208f_272.png)

![](img/042e2120f660692e50037b41ab6d208f_273.png)

![](img/042e2120f660692e50037b41ab6d208f_274.png)

and these red values are grouped together， so corresponding they correspond to the same centroid。

 we're going to reduce them by summing them up， summing them up okay and then multiplied by the vary rate subtracted from the original centroid then we get the fine tune the centroid so there's one iteration of the SGD on a k is quantized neural network。



![](img/042e2120f660692e50037b41ab6d208f_276.png)

![](img/042e2120f660692e50037b41ab6d208f_277.png)

So first do a group by operation and then do a reduction by suming the map multiplied by the learning rate subtract it from the original century that will give you a big update of the century。

How does that work with respect to the accuracy， so this is showing the quantization only what is model size。

 visual out compression so you can go much smaller and this is the accuracy degradation we feel about 10%。

 11% we have very low accuracy degradation and after that the accuracy is going to drop very quickly。



![](img/042e2120f660692e50037b41ab6d208f_279.png)

![](img/042e2120f660692e50037b41ab6d208f_280.png)

![](img/042e2120f660692e50037b41ab6d208f_281.png)

How does it compare with pruning only so this line is showing the pruning only result in purple and we can find that they are pretty much much closer roughly around 10% the accuracy begins to drop。

But the good thing is that。Pruruning and quantization can be combined together。

 and you can do both pruning and then quantization that give you the highest configuration。

I think just a few percent， the accuracy is still very well maintained， which is a good thing。

So practically， should we do ping first or should we do consation first？

What does the model size ratio mean for quantization。

 so if the original model size is 100 megabytes now is 10 megabytes， then the ratio will be 10%。

If originally you're using 32 bit and the model is 100 megabyte， now you're using 8 bit。

 the model size will be 25 megabytes and the ratio will be 25%。

Where by you had the experiences and never able。So there is actually。

But depends on the number of the reduction can be done by let me see actually right here we had calculated on the me let me see。

 let me double check this is just doing the sum， I believe， yes。

 this is just doing the sum because they are all updated to the same central。

A lot of people want to nudge the same centrally， therefore we sum them up。

Somehow they can be partially canceled by a bodyp with the learning rate。

 but really matters is how many numbers will go to the same bucket。

 the more number of going want to go to the same bucket。

 the more you want to nu to the weight so they're probably doing the sun right here。

You're very welcome to try point to the mean the average。

That' the beauty of deep learning is not a fixed science nor edge engineering， so basically use it。

No matter that works the best。Not necessarily， this is the best approach because just what I did。

In the bank many0 years ago。So back to our question。

 should we do pruning first or should we do quantization first？Okay。嗯楚。对。研と。here fine。Right。

 that's a good point。 since you want to do quant prun first。

 because you want to first eliminate a lot of。Rundant weights， okay。

 so you have fewer number of weights to quantize reducing your workload。

A to contest and potentially reducing the quantization error。 So first。

 get rid of those redundant ways before the contest。

So this is the way distribution after fine tuning they prune the model。



![](img/042e2120f660692e50037b41ab6d208f_283.png)

Why there is a big bump here because everything close to zero are approvedruned。



![](img/042e2120f660692e50037b41ab6d208f_285.png)

Using our magnitude based polluting approach， okay？Everything close to zero。

 they are set to zero so these areas get flatter because after fine tuning they become flatter okay so what does it look like after quantization the values becomes discrete rather than continuous distribution they become discrete only a couple of cent this is cent this is one this is another one。



![](img/042e2120f660692e50037b41ab6d208f_287.png)

![](img/042e2120f660692e50037b41ab6d208f_288.png)

Is there another one is another essential one， and the becomes discrete。保春。呃， repeat的 question。

Any situation where quantization would be more preferable than th。啱。

Depending on the pruning granularity， of course， growing the pruning。

Any hardware can accelerated so it's best to combine them both I don't see any scenario where you don't want to combine pausesp pruning with with quantization unless your hardware doesn't have any low precision units you can only do pruning。

But I don't see a reason where you cannot do pruning but only do quant at this you can do quase grain structured pruning。

So the remaining weights are still death。Okay， so after the fineuning。

 we can see a slight difference。Right here between these two slides。

 you can see the sroid shifted a little bit from here here the sroid shifted a little bit that is due to when we are updating the weights remember right here just down have per questionion。

We are often gradient some of the mo since all these blue gradient are trying to update the blue centroid。

 we want to sum the map， apply the nudge， apply the change altogether together to change this centroid。



![](img/042e2120f660692e50037b41ab6d208f_290.png)

![](img/042e2120f660692e50037b41ab6d208f_291.png)

Wu Sananroidroid will get changed after a couple of virtual theseerations。And we indeed。

Observed that change between these two slides。This is before， this is after。

 before this is after it has seen a slight change about the position of aity。And another question is。

And is the assignment able to get changed and that is so true if the nudge is so big one value also might also become another bucket。

 so the assignment the color assignment might also change we are going to implement that in lab two which we are going to release next week actually we already release it so feel free to try it out to implement this came means quantization by yourself。

And finally， how many bits do we need in practice previously we are showing two bits for illustration purpose in practice we find for this is for an extended convolution layer before after four bits。

 the accuracy is going to drop rather sharpen， but before that the accuracy can be very well maintained。



![](img/042e2120f660692e50037b41ab6d208f_293.png)

But F layers after two bits， two bits。

![](img/042e2120f660692e50037b41ab6d208f_295.png)

Before two bit， the accuracy is still well maintained for the top five and top1 accuracy。

And in practice nowadays for large language models。We are going to see that in La four。

Forbitit is very enough， is quite good maintaining the accuracy of large language models is transforming analysis。

So another idea。Composing this deep compression paper is using halfmancoing to further compress it since the weight distribution is not uniform okay so some of the weights appear very frequently。

 some of the weight doesn't appear very frequently。

 so we can input the weights using different number of weights。



![](img/042e2120f660692e50037b41ab6d208f_297.png)

![](img/042e2120f660692e50037b41ab6d208f_298.png)

For different weights。They can use different variable length en codingd。

 so we can use fewer bits for the more frequently appearing one and use more number of bits for those less frequently appearing rates。



![](img/042e2120f660692e50037b41ab6d208f_300.png)

![](img/042e2120f660692e50037b41ab6d208f_301.png)

So put them together， we have this three stage pipeline4 deep compression first using pruning to reduce the number of weights by the train the model。

 pruning retrain it repeatedly。

![](img/042e2120f660692e50037b41ab6d208f_303.png)

And then by quantization， when first cluster the weight using K means a passing。

 generate a code book， 16 entries， four bits or four entries， two bits。

Then we quantize the widths with a code book， retrievetrain the code book， and repeat this process。



![](img/042e2120f660692e50037b41ab6d208f_305.png)

And finally， we can encode the weights using different bits for different weights。



![](img/042e2120f660692e50037b41ab6d208f_307.png)

And as a result， we can achieve a high compression ratio across different neural networkss。



![](img/042e2120f660692e50037b41ab6d208f_309.png)

40 times for the math， 39 times for the net5， 45 times a likeNe。

 even the Google resonnet can be compressrised by an order of magnitude。



![](img/042e2120f660692e50037b41ab6d208f_311.png)

And this is the model size before and after the quantation。

 this is original accuracy and the compressed accuracy， the accuracy can be very well maintained。



![](img/042e2120f660692e50037b41ab6d208f_313.png)

![](img/042e2120f660692e50037b41ab6d208f_314.png)

Even for very small and compact neural nets like squeeze nets。

 we're going to introduce in the neuroarch search session。



![](img/042e2120f660692e50037b41ab6d208f_316.png)

It's very small to begin with like 0。47 megabytes begin with its 4。

8 megabytes to begin with compared with Alex that is already 50 times smaller and 50 times smaller compared with Alex that with exactly the same accuracy。

 but even that can be compressed by deep compression by a hundred of magnitude so 10 times smaller。



![](img/042e2120f660692e50037b41ab6d208f_318.png)

Maintaining the accuracy of the model is only as 0。40 nanobytes and put it in the pocket。



![](img/042e2120f660692e50037b41ab6d208f_320.png)

Yes， that's the hyperparmeter and how to find that hyperparameter we're going to find where the axis believe the are。



![](img/042e2120f660692e50037b41ab6d208f_322.png)

Here we get the accuracy drop at four bit， so K equal to 16。Here I drop by two bits。

 so K equal to four。

![](img/042e2120f660692e50037b41ab6d208f_324.png)

We are going to play with that in their homework。Good question。All right。

 so how do we compute on a K means based the weight the quantization。

 we have to decomprise it okay by mapping it from the index into the original weight。

 so here we have the codebook， we have the quantized weight we have the first decod it from unsigned end which is just the index into the floating point weight and all the remaining operations will be done in floating point so it save the storage。

 but it doesn't save the computation。

![](img/042e2120f660692e50037b41ab6d208f_326.png)

![](img/042e2120f660692e50037b41ab6d208f_327.png)

![](img/042e2120f660692e50037b41ab6d208f_328.png)

But it's still very helpful for in the modern transformers and large language models。

 because for single user for。A generation phase completely memory bonded， not compute bonded。

 so using IP16 is totally fine but reducing the memory footprint by four times compared with IP16 is super helpful。

Okay， let's take a short break before we jump into the next part， which is linear quantization。Yeah。

All right， welcome back， so let's continue the discussion about linear quantization。

 So now we want to use integer weight integer weights to represent the values and also we want to use the integer arithmetic。



![](img/042e2120f660692e50037b41ab6d208f_330.png)

To do the computation so that we want to get an acceleration and also get a storage saving so let's see what is linear quant This is very widely used if you're using a mobile phone running an application locally that's highly possible linear quantization is used here。



![](img/042e2120f660692e50037b41ab6d208f_332.png)

So what is linear quantization， So given。This is our familiar matrix four by four weight matrix。

 so now we want to quantize them into only integer values okay right here is10 is minus2 by1 minus10000 y equal to 1 okay so now this is the quant the version of the original matrix so 2。

09 becomes 1 minus 0。98 becomes minus2。

![](img/042e2120f660692e50037b41ab6d208f_334.png)

![](img/042e2120f660692e50037b41ab6d208f_335.png)

![](img/042e2120f660692e50037b41ab6d208f_336.png)

![](img/042e2120f660692e50037b41ab6d208f_337.png)

![](img/042e2120f660692e50037b41ab6d208f_338.png)

So here we have two parameters where I'm going to learn how to determine these parameters but let's just see how that works。

We have to define zero point and a scalar and a scale factor。

So we or you subtract the matrix with the zero point， multiply the skating factor。

And we get the reconstructed width matrix， so 2。09 becomes 2。14 minus 0。98 now becomes minus 1。

07 and this is the quantization error quite small so they are roughly very well correlates between and after quantization so the magic here is how do we find how do we calculate this zero point。



![](img/042e2120f660692e50037b41ab6d208f_340.png)

![](img/042e2120f660692e50037b41ab6d208f_341.png)

2 bit s integer versus the scale， which is a 32 bit floating point number。



![](img/042e2120f660692e50037b41ab6d208f_343.png)

So what is a？Zero point。And scalingkating factor so we are going to map this integer value Q integer value Q subtracted from the integer zero point and multiply by the scalingkating factor we get the floating point value so basically z。

 which is the zero point。

![](img/042e2120f660692e50037b41ab6d208f_345.png)

![](img/042e2120f660692e50037b41ab6d208f_346.png)

![](img/042e2120f660692e50037b41ab6d208f_347.png)

嗯那。It allow a real number r equal to zero， which r equal to zero to be exactly represented by a quantized integer Z。

 so z will be mapped to zero okay。

![](img/042e2120f660692e50037b41ab6d208f_349.png)

And then we have another scale factor to scale the dynamic bridge。



![](img/042e2120f660692e50037b41ab6d208f_351.png)

What that means is that we have a floating point dynamic range from R mean to R max。

 this is the range of the beta values。We also have a dynamic range for the integer value from Q mean to Q max。

And the zero point maps z to zero from integer space to floating point stage to1 floating point。



![](img/042e2120f660692e50037b41ab6d208f_353.png)

![](img/042e2120f660692e50037b41ab6d208f_354.png)

Great。

![](img/042e2120f660692e50037b41ab6d208f_356.png)

So this is corresponding to a different number of bits， you have two bits。

 the QB equal minus2 Q max max equals to1， you have three bits or minus4 positive three。

 so the integer。

![](img/042e2120f660692e50037b41ab6d208f_358.png)

Q me and Q max are fixed。So how do we calculate the scaling factor okay。

 so Q mean has to be mapped to army mean and Q max has to be mapped to R max using the equation where we map  Q max minus z0 by s we get R max。



![](img/042e2120f660692e50037b41ab6d208f_360.png)

Q me minus z scaled by s， we get Rine， we can subtract them and then divide it。

 we can get the scalingating factor equal to r max minus Rine， which is here R max minus R mean。

 the dynamic range of the14 point range。

![](img/042e2120f660692e50037b41ab6d208f_362.png)

![](img/042e2120f660692e50037b41ab6d208f_363.png)

Divided by the Q max minusq me， the dynamic range of thete integer scale。



![](img/042e2120f660692e50037b41ab6d208f_365.png)

![](img/042e2120f660692e50037b41ab6d208f_366.png)

So s can be calculated this way R max minus r me divided by 2 minus minus qb。



![](img/042e2120f660692e50037b41ab6d208f_368.png)

So given our matrix， this is our familiar matrix， the max value is 2。12 me value is minus 1。08。

 we use this equation to calculate the dynamic range of the floatinging point versus the dynamic range of the eachteger。

 and now we can get a sc factor to be 1。07。

![](img/042e2120f660692e50037b41ab6d208f_370.png)

![](img/042e2120f660692e50037b41ab6d208f_371.png)

That's how we calculate the skin factor。Now we can calculate the Z， okay， so since we already have s。

 we can plug in s to get the Z。And it has to be an integer。

 therefore we have surroundeded to the closest integer value。In our example， Q min is minus 1。

08 in the right part， we plug in the equation。

![](img/042e2120f660692e50037b41ab6d208f_373.png)

And then we can one too。pl in the Q mean which is minus2， since we have only two bits， two minus2。

 army is minus 908， minus 908， as we already calculated is 1。07。

 and we round it with Z0 points is minus1。

![](img/042e2120f660692e50037b41ab6d208f_375.png)

So now let's talk about linear quantized matrix multiplication， so how do we use integer unit。

 only use integer unit to calculate the matrix modification。

So linear quantization is I find mapping from integers to real numbers using the equation we just talked about。

So consider the following matrix modelation y equal to Wx。

Originally there are1 floating form values now we want to convert them convert it into integer values we are going to implement in the lab。

 so I will pay ready attention to the derivation for the remaining 20 minutes。



![](img/042e2120f660692e50037b41ab6d208f_377.png)

So we plug in the equation where r equal to s times  Q minus z s times q minus z for the output for the weight for the input activation plug them in。

 and then we rearrange them by sub by moving Sy to the right hand side。

 moving z y to the right hand side。

![](img/042e2120f660692e50037b41ab6d208f_379.png)

![](img/042e2120f660692e50037b41ab6d208f_380.png)

And then we can expand the equation from this rule to this rule from all the way we get is four different terms。

 so far， a very simple derivation。

![](img/042e2120f660692e50037b41ab6d208f_382.png)

So we want to use Mbit。😡，For example，8 bit integer multiplication。And use 32 bit integer addition。

Will prevent overflow。So first of all， the skating factor。

And then we have this integer addition and then these yellow part are all constant。

 the weight is constant。

![](img/042e2120f660692e50037b41ab6d208f_384.png)

At the zero point is a constant。

![](img/042e2120f660692e50037b41ab6d208f_386.png)

Profille zero points is constant so all these can be pre computed it's not in the runtime。

 no runtime overhead and now let's focus on the scaling factor。So empirically。

 the scalingating factor as w S x divided by Sy is between zero and1。



![](img/042e2120f660692e50037b41ab6d208f_388.png)

And from this paper here can be represented by22 power of minus n times in value。

 okay a fixed point value between 0。5 and one。And this modification can be done with a fixed point modification。



![](img/042e2120f660692e50037b41ab6d208f_390.png)

And the total power of minus n can be done by a simple bit shift。

 so we don't need floating point unit。To implement this blue part。



![](img/042e2120f660692e50037b41ab6d208f_392.png)

So for this part， we scale them to em integer， this part can be pretty computeutd。

 and the last part is the em integer addition。

![](img/042e2120f660692e50037b41ab6d208f_394.png)

And let's look at the middle part， the Zw times the  Qx， so the zero point of the weight。

What is distribution like？

![](img/042e2120f660692e50037b41ab6d208f_396.png)

So it's roughly following a normal distribution， okay？So roughly centered at10。 Okay。

 so we can safely set Z W to be 0 because it's very symmetric and。



![](img/042e2120f660692e50037b41ab6d208f_398.png)

Roughpha0 is map to0， and so we set zw to be0。And what I mean is that originally C map to0。

 now zero map to zero from the fixed point to the floating point range。



![](img/042e2120f660692e50037b41ab6d208f_400.png)

![](img/042e2120f660692e50037b41ab6d208f_401.png)

![](img/042e2120f660692e50037b41ab6d208f_402.png)

In that case， we can simplify the equation where now z becomes zero。

 so the scalingating factor will be using the absolute value of the R divided by total power of n minus one much simpler calculation or the scaling factor previously we have to do this calculation。



![](img/042e2120f660692e50037b41ab6d208f_404.png)

![](img/042e2120f660692e50037b41ab6d208f_405.png)

![](img/042e2120f660692e50037b41ab6d208f_406.png)

To map it now we just do a much simpler calculation to map it。



![](img/042e2120f660692e50037b41ab6d208f_408.png)

So we can。

![](img/042e2120f660692e50037b41ab6d208f_410.png)

Safely get rid of for part since ZW is0， it'ssymmetric then we are left only with。These two terms。



![](img/042e2120f660692e50037b41ab6d208f_412.png)

The first term， which is can be done by a bit integer multiplication， the QX and QW。

 that's where the most of the weight lifting is happening in the computation。And we can since zw is0。

 we are only left with a single term is a constant because z is a constant QW to quantize the weight。

 the weight is also constant。

![](img/042e2120f660692e50037b41ab6d208f_414.png)

![](img/042e2120f660692e50037b41ab6d208f_415.png)

But we are only left with the ZY。And the blue part is the bulk of the computation where the bulk of the computation happens。

Now let's consider adding back。The bias okay so far we are economic bias now we consider following the fully connector layer with the bias okay so the bias can be also with plugging equation right here the bias can be also represented by subtracting the bias and then multiplied with the scalingating factor of that bias。



![](img/042e2120f660692e50037b41ab6d208f_417.png)

![](img/042e2120f660692e50037b41ab6d208f_418.png)

Since previously we mentioned ZW is0， it's following a normal distribution， we can set ZW to be 0。

 so integer 0 map to the 14。0。

![](img/042e2120f660692e50037b41ab6d208f_420.png)

I think eliminateinate everything associated with the ZW， so we are left with the equation here。



![](img/042e2120f660692e50037b41ab6d208f_422.png)

We can force this SB。你哋咩啊。

![](img/042e2120f660692e50037b41ab6d208f_424.png)

The scaling factor for the bias versus the scaling factor of the weight and activation versus the ZB。



![](img/042e2120f660692e50037b41ab6d208f_426.png)

Similar to the weight， the distribution of the bias is also following a normal distribution which is so we can set zb to be0 we can set zb to0 and we force SB to be equal to sw times as x so that the equation can be simplified this way we absorb2 B together when these two terms x so we force SB equal to Sw times S x。



![](img/042e2120f660692e50037b41ab6d208f_428.png)

![](img/042e2120f660692e50037b41ab6d208f_429.png)

It says like this， continue with that renovation。

![](img/042e2120f660692e50037b41ab6d208f_431.png)

We are going to move X y to the right hand side and move z Y to the right hand side。

 so we are left to this equation。

![](img/042e2120f660692e50037b41ab6d208f_433.png)

![](img/042e2120f660692e50037b41ab6d208f_434.png)

So QB Z XQW quant weight， the point of activation bias the biasers。

 they are all constant so we can precompute them。

![](img/042e2120f660692e50037b41ab6d208f_436.png)

And we define the QB minus the2W to the Q bias since it's a constant。

 then we can simplify all the equation to something like this。



![](img/042e2120f660692e50037b41ab6d208f_438.png)

![](img/042e2120f660692e50037b41ab6d208f_439.png)

![](img/042e2120f660692e50037b41ab6d208f_440.png)

As look closer into this equation， the blue part is the bulkcott of the computation。

 most of the weightlifting is happening in the blue part， but low bit integer multiplication。



![](img/042e2120f660692e50037b41ab6d208f_442.png)

![](img/042e2120f660692e50037b41ab6d208f_443.png)

And we can rescale the scalingating factor to n bit integer like8 bit integer followed by shift to just discuss about it。



![](img/042e2120f660692e50037b41ab6d208f_445.png)

![](img/042e2120f660692e50037b41ab6d208f_446.png)

And finally， we have MB integer ad。Okay， so now everything can be cast into a low precision integer operation。

我哋会议啊。Use convolution rather than a fully connected layer。



![](img/042e2120f660692e50037b41ab6d208f_448.png)

So compared with the fully connected layer now we run the convolution essentially the revision is pretty much the same you' are going to visit in the lab。

 we just replace multiplication with convolution， we're all linear okay so blue part is where the green part is where most of the computationnot is happening。



![](img/042e2120f660692e50037b41ab6d208f_450.png)

So this is a computation diagram where we have previously the quantized weight。

 this is the quantized input calculation we do into the con。

 the convolution is added with the bias the sum in sum using a 32 bit register for the summation to prevent overflow so it begins it be 32 bit in for the summation register and all the sum is done in 32 bit and the bias scale by the scalingating factor and then add the zero point and finally we get the quantized output。

So what's the difference with the K means quantization previously we are using。

32 bit bullet point to do all the computation。 Now we are using integer to do all the computation。

So we are saving not only the storage， but also we are saving the compute。

So we are going to implement this in lab two， so make sure you understand the lecture here。

 I'll pause a little bit for you to in case you have any questions for the derogation。It。Yeah。

 for Redlu， you basically have nothing on the。Nothing on the on the left so you are wasting half of the dynamic range if you set the bias the zero point of the bias to be0。

 which is this case， you weigh the half of the dynamic range。

If no more questions let's see how does the accuracy compare with the floating point so the this figure is showing the floating point versus8 inger so this is the latency versus the accuracy ideally we want something on the top and left corner and consistently the8。



![](img/042e2120f660692e50037b41ab6d208f_452.png)

![](img/042e2120f660692e50037b41ab6d208f_453.png)

Is having a better trade off on the plot compared with the IPP。

The floating point counterpart higher your accuracy， same latency or same accuracy lower la。



![](img/042e2120f660692e50037b41ab6d208f_455.png)

![](img/042e2120f660692e50037b41ab6d208f_456.png)

On the left hand side is showing for rather 15 inception V3。

 the1 floating point Brazil the integer accuracy。

![](img/042e2120f660692e50037b41ab6d208f_458.png)

But nowadays， this8 bit quantization becomes very mature。

That's the solution to accelerate and compress neural。And most of the hardware have 88 integer units。

 so that's very widely used if you're using running neuralnets on the phone on a microcontroller on an apps device。

 this is a very critical solution。All right， so that concludes our second part。

 which is the linear quantization， so different from he quantization which only save storage but doesn't save computation。

 linear quantization can save both storage and the quantization。



![](img/042e2120f660692e50037b41ab6d208f_460.png)

![](img/042e2120f660692e50037b41ab6d208f_461.png)

So what is next， Can we go even lower precision， So we are going to talk about binary turnernary quantization in the next lecture。

 only use one bit or two bit to present each。Okay， so let's summarize today's lecture。

 we first review， introduce the data types floating point， what is integer。

 what is a floating point representation。What is the exponent bit， what is the9a bit。

 what is sub normalormal origin， how do we represent very big numbers， what is FP4， F8。

 different configurations， E2M4， eta。E5M2， et cea， and also we visited the basic concept of neuralnaural quantization to turn convert weight and activations to discrete values。

And then we introduce two types of quantization， one is K meanss quantization。

 when to see them in the homework and also the linear quantization。

 we went through a long derivation， make sure you can translate them into the code in lab2。

And here are some references。And that's all for today's lecture。



![](img/042e2120f660692e50037b41ab6d208f_463.png)

Thank you。
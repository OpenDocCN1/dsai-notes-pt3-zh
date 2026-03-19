# 【麻省理工】高效机器学习 MIT 6.5940 EfficientML 2024 年秋季 p09 P09 Lecture 5 - Quantization Part I -BV1o7jzzwEST_p9-

Okay， welcome everybody， let's get started with lecture five of Eient ML AI。

 so today we are going to jump into a new chapter about quantization。

So last lecture we learned about footing to reduce the number of parameters in a neural network if you think about the total size of a model of a neural network of model that equal to the number of parameters times the bit width the number of bits per parameter right so you multiply them together that gave you the total size of the model。

So if we want to reduce the size of the model on one side， we can reduce the number of parameters。

 that is by using pruning， and the other side will be trying to reduce the precision。

 the number of bits for each parameter so that is quant。

We are going to spend two lectures about compensation and here is our agenda。

We will first review the numeric type data types， including the integers， the floating points。

 the in8， at P 32， at bid 16 at in4 and night before。

We are also going to learn the concepts of neuralna pruning quantization。

Followed by three types of quantation approach。So we are going to talk about K means based quantization and linear quantization today in the next lecture。

 we are going to cover binary and turnern rate quantization。So let's start with why do we need quant？

So little bit operators are actually much cheaper， so if you compare the energy of the operation from 8 bit to 32 bit。

 actually the8 bit integer operation is much cheaper compared with the 32 bit or the 32 bit integer operation or the 32 bit gling point operation。

That from the operation perspective， from the memory perspective。

 every data movement is actually data movement is also quite expensive here。

 so each memory access equals to hundreds of ariically operations so if you can reduce the size of the model we can reduce the memory traffic as well。

So less a number of bandwidth wave will result in less energy consumption。

So let's in order to understand how do we quantize neural networks。

 let's first talk about the data types， how is the numeric data represented in modern computing system？

So let's start with integer okay so integer is most common representation easiest representation we have ein signed and also signed integer okay so in the einsstein version each digit represents total power zero to power one all the way to to power of7 if we have eight bits right here so this number actually three represent 49。



![](img/7709f67508e9b6473189b0f9a1be397e_1.png)

![](img/7709f67508e9b6473189b0f9a1be397e_2.png)

But these are einstein， if you want to add a sign bits with a one bit in the top so that the remaining bits ranges from two to power of0。

 always with a power of six。

![](img/7709f67508e9b6473189b0f9a1be397e_4.png)

![](img/7709f67508e9b6473189b0f9a1be397e_5.png)

And here we can find actually we have overlap， both all zeros and 1000， they both represent zero。

So in order to remove that duplication， a better way to represent a sign integer is by using this tools complement representation。



![](img/7709f67508e9b6473189b0f9a1be397e_7.png)

So what that means is the first bit actually means total minus total power of seven okay and the remaining bits are positive from total power to0 to the power one to power of six。

 only the first bit is total power of seven。

![](img/7709f67508e9b6473189b0f9a1be397e_9.png)

![](img/7709f67508e9b6473189b0f9a1be397e_10.png)

In this case， 000 equal indicate 0， but 1000 no longer indicate0 by total power of n minus one。



![](img/7709f67508e9b6473189b0f9a1be397e_12.png)

With that， we can talk about fixed point number， so here we have a decimal point。



![](img/7709f67508e9b6473189b0f9a1be397e_14.png)

So this decimal point above that， we have the integer bit below that， we have the fraction bit。

So from the smallest the dense model represents two to the power of zero and then two to the power of one。

 larger and larger。Since this is to complement representation， the first fit is always negative。

And after the denimmo bid， it represents total the power from minus1。

 minus2 all the way to minus4 in this case。

![](img/7709f67508e9b6473189b0f9a1be397e_16.png)

Another way to tell which number it represents is still using everything starting from zero。

 total power of zero， all the way to total power of six。



![](img/7709f67508e9b6473189b0f9a1be397e_18.png)

But to shift it by the number of。Fraactctional bits。

 which is four and we shift everything by four and we can see the represented number is still the same using both interpretations。



![](img/7709f67508e9b6473189b0f9a1be397e_20.png)

So that's the fifth point number。Let's get more complicated to represent a larger range。

 larger dynamic range。People invented it floating point number and here we are showing example of 32 bit。

 floating point number in actually 754 Okay， so among is 32 bits we have one sign bits in the front。



![](img/7709f67508e9b6473189b0f9a1be397e_22.png)

And then8 bit of exponent。And then 23 bits of fraction is also called significant bit or the Mattia bit。



![](img/7709f67508e9b6473189b0f9a1be397e_24.png)

The relationship between these bits is that the definition of this number is minus one to or s bits。



![](img/7709f67508e9b6473189b0f9a1be397e_26.png)

And this is the sign bit。then one plus the fraction bit， this is the fraction bit。

 yellow pie times2 to the power of exponent minus the bias here the bias is 127。

And how is that calculated， we have8 bits of an expon bit。

And the bias is calculated by2 to the power of exponent bit minus1 minus1 so for eight bits。

 we have two to power of seven minus1， which is 127， which is a constant number。

 as long as we are using 32 bit floating point new presentation。

 so fraction bit correspond to the yellow part exponent bit correspondinging to the blue part。



![](img/7709f67508e9b6473189b0f9a1be397e_28.png)

Given such definition， we can easily calculate how to represent this number。



![](img/7709f67508e9b6473189b0f9a1be397e_30.png)

0。265 six35。

![](img/7709f67508e9b6473189b0f9a1be397e_32.png)

The representation would be first converted into one plus fraction， one plus fraction。

 so the fraction here is 0。02625。

![](img/7709f67508e9b6473189b0f9a1be397e_34.png)

One point something。Times two to the power of minus2。Here， since the bias is 127。

 the exponent bit should be 125， so the exponent bit should be 120 by using these eight bits in the blue。

 and then the 0。0，625 is represented by a1， the fourth position。



![](img/7709f67508e9b6473189b0f9a1be397e_36.png)

系。So first， converted into one plus something to do the power of something， okay？

Any questions for this example？说放首歌。All right。So let's see how do we represent zero since we have to if we have to be forced to use one plus something to represent a number and then how do we represent zero？



![](img/7709f67508e9b6473189b0f9a1be397e_38.png)

![](img/7709f67508e9b6473189b0f9a1be397e_39.png)

Actually people define this subnormal number previously we were talking about this representation okay well I'm flat fraction to the power of exp exponentialonent minus the bias we call it normal numbers。

onent doesn't equal to zero。

![](img/7709f67508e9b6473189b0f9a1be397e_41.png)

Here we design a special place where the explosion bits the blue Park。

As we frozen to zero in that area， for particular for that area where exponent bits are zero。

 we defined it as subnormal numbers。And the equation is a little different。

 rather than one plus fraction here， we just use fraction。

Okay and rather than two power of exponent minus 127 here we need。

Have a total power1 minus 127 so the fraction bit is only variable here。

 we no longer have the expondent bit because here the expondent bit are force but frozen to be all zeros。



![](img/7709f67508e9b6473189b0f9a1be397e_43.png)

![](img/7709f67508e9b6473189b0f9a1be397e_44.png)

So now if the fraction bit is all0， then no matter if the sine be is0 or1。

The final result would be zero。

![](img/7709f67508e9b6473189b0f9a1be397e_46.png)

So that's how we represent zeros and how do we define those subnormal numbers。So let's see。

 what is the smallest and largest positive subnormal value using the sub normalormal representation on the right side？

So first of all， if it is a normal number right the exponent bit and'll be0 okay so in this example the exponent bit is one and then the fraction bit is 0 so the number of B1 plus0 times total total power1 minus now 127。



![](img/7709f67508e9b6473189b0f9a1be397e_48.png)

![](img/7709f67508e9b6473189b0f9a1be397e_49.png)

![](img/7709f67508e9b6473189b0f9a1be397e_50.png)

And the final result is total power of-126。 So that's the normal number for sub normalormal number。

 the expondent bit is frozen to be 0。 and you only be。



![](img/7709f67508e9b6473189b0f9a1be397e_52.png)

![](img/7709f67508e9b6473189b0f9a1be397e_53.png)

The fraction days。Is what relative。And this is total power of。in- 23， so this is total power of。

Mus 23 times total total power of minus 126， 126， this is a constant because this is by definition。

 one minus 127。

![](img/7709f67508e9b6473189b0f9a1be397e_55.png)

![](img/7709f67508e9b6473189b0f9a1be397e_56.png)

![](img/7709f67508e9b6473189b0f9a1be397e_57.png)

Okay， so this is the smallest number we can represent。



![](img/7709f67508e9b6473189b0f9a1be397e_59.png)

The soft normal region。So this is constant， this is also constant。

 so only the fraction bit right here， so actually we can see this is very similar to the this is a linear representation。



![](img/7709f67508e9b6473189b0f9a1be397e_61.png)

So right here is now linear nearby here it's ven。What about the largest positive subnormal value Okay so on the rank hand side we just feel all the fraction bit to be one and in this case total power minus23。



![](img/7709f67508e9b6473189b0f9a1be397e_63.png)

Plus plus total the power of minus-1， so sum sum it up， we get one minus2 the power of minus 23。

And then here we have the bias times total power of minus 126。

 that is the largest number we can represent in the soft normalmal region。



![](img/7709f67508e9b6473189b0f9a1be397e_65.png)

![](img/7709f67508e9b6473189b0f9a1be397e_66.png)

There are other two cases where if all the exponent bit。Are all one？If the sine be0。

 we use that to represent positive infinity。If the sign bit is y。

 we use that to represent negative infinity。

![](img/7709f67508e9b6473189b0f9a1be397e_68.png)

so that is the case for representing the infinity， or the fraction bit has to be zero。

 or the sign of the exponent bit has to be one。

![](img/7709f67508e9b6473189b0f9a1be397e_70.png)

What about the sign bit is one， but the Roman base is90。

 we use that to represent not a number okay so I'm there is a big waste because no matter what the value are in the fraction bit。

 they all represent value not a number。

![](img/7709f67508e9b6473189b0f9a1be397e_72.png)

So actually we are going to revisit this the Ss representation。



![](img/7709f67508e9b6473189b0f9a1be397e_74.png)

So these are the two extreme cases for the mostly coming from the exponent bit， if they're all zero。

 then that subnmal number， if they're all one， they use either infinity or not a number。

 depending on the fractional bit。

![](img/7709f67508e9b6473189b0f9a1be397e_76.png)

So we can talk a lot， Let's put a summary here。To summarize what we have learned so far for the floating representation。



![](img/7709f67508e9b6473189b0f9a1be397e_78.png)

First， most importantly。Exoding bit， the blue part right if it is zero or if it is9 zero or if it is all what okay if it is。

9 zero or not the largest number， then that's the normal weather okay so the representation would be minus one to the power of sign bit one plus the fraction times to the power being exponent minus the bias。

 that's the simple case。And then we have two corner cases if the exponent is all zero。

Then we will look at the fractional bit， if there's zero， then represent represent zero。

 if they're not zero， then there are subnomal numbers。

So no numbers representation differ by one one plus versus just a fractionction when here and here the constant is two to power of 1 minus 1207。

Okay so that's the exponent equal to zero。Third case is exponent is all what， okay？

And that either represent positive or negative infinity or not a number。

 depending on the fractional it。

![](img/7709f67508e9b6473189b0f9a1be397e_80.png)

And if you see the number of representation from small number to the largest number。

 we divide into two rids。

![](img/7709f67508e9b6473189b0f9a1be397e_82.png)

The sub normal values versus the normal values。In the sub normal value。

 the distance between cent is constant is linear quant versus in the normal value。

 the size become larger and larger。

![](img/7709f67508e9b6473189b0f9a1be397e_84.png)

So it's good at expressing very large numbers。So， people have been。

In keeping improving the efficiency by pushing the precision to lower and lower precision。

So from IP32 toP16 to B flow 16。So the exponent width actually represent the range。

 how much range you can represent， so that is using mostly using the exponent。



![](img/7709f67508e9b6473189b0f9a1be397e_86.png)

And a fraction width indicates the precision indicates the precision。



![](img/7709f67508e9b6473189b0f9a1be397e_88.png)

So for AP 32， we have eight bits for the exponent and 23 bits for the fractional bits。

 and altogether we have 31 plus the first sign bit， altogether we have 32 bits。



![](img/7709f67508e9b6473189b0f9a1be397e_90.png)

![](img/7709f67508e9b6473189b0f9a1be397e_91.png)

Well， for the I half precision， which is within 16 bit to represent。

 we have less number of exponents， only five bits per exponent。



![](img/7709f67508e9b6473189b0f9a1be397e_93.png)

And 10 bits for a fraction。

![](img/7709f67508e9b6473189b0f9a1be397e_95.png)

Later， Google demanded this new time， which is BF160 brain floatloat 16。



![](img/7709f67508e9b6473189b0f9a1be397e_97.png)

And that is trying to match the。Exponent bit， number of exponent bits with the FP 32。

 they are using both8 bits for the exponent。We sacrifice the precision。

 we sacrifice the precision using fewer fewer number of fraction bits。

 so we have eight bits for the exponent seven bits for the fraction plus one bit on the top。

 altogether we have 16 bits。

![](img/7709f67508e9b6473189b0f9a1be397e_99.png)

![](img/7709f67508e9b6473189b0f9a1be397e_100.png)

![](img/7709f67508e9b6473189b0f9a1be397e_101.png)

So notice the exponent bit for the IP32 and Bf16 are the same。Therefore。

 usually when we are training a large scale neural networks， BFP16， sometimes we'll diverge。

 then the good solution usually is to use PF16。Okay， so a question here。

 what is the following FP16 number in， so let's do a practice？We were given a。



![](img/7709f67508e9b6473189b0f9a1be397e_103.png)

Representation right here， we have。5 bits of10 bit of fraction， that's the standard at P16 precision。

So for IPP 16， what is the bias five bits5 minus1 is four， total power 4 minus1 that's 15。

 and so bias should be 15。

![](img/7709f67508e9b6473189b0f9a1be397e_105.png)

![](img/7709f67508e9b6473189b0f9a1be397e_106.png)

So we can use the equation first off， all the sine bit is minus when the exponent would be 10001 minus the bias right here equal is 17 minus 5 15。

 which is 2。

![](img/7709f67508e9b6473189b0f9a1be397e_108.png)

And the next we'll be calculating the fraction bits。

 a fraction bit is  one1 followed by a bunch of zeros。



![](img/7709f67508e9b6473189b0f9a1be397e_110.png)

WeBut a presentation that is 0。75， so this is 0。5， 0。25， adding them together， we have 0。2。7 five。



![](img/7709f67508e9b6473189b0f9a1be397e_112.png)

![](img/7709f67508e9b6473189b0f9a1be397e_113.png)

And we use the equation sign bit one plus the fraction bit times total total power of spoon bit。

 it would plug in the max cell I would plug in two， and altogether we have minus seven。



![](img/7709f67508e9b6473189b0f9a1be397e_115.png)

In this case， so if。哦。F point number I should represent minus7。So let's do a reverse example。

We have a decimal number， which is two and half。Outre in brain F 16。

I'll give you one minute to think about it。First of all， it's brain float 16， right。

 so it's one bit of sign bit， eight bit of exponent and seven bit of fraction。

The first thing would be to calculate the bias， right？



![](img/7709f67508e9b6473189b0f9a1be397e_117.png)

A bit of exponent and the buyer simple to total power。Exponent -1， -1 total power 7-1 plus 1，27。

 Okay， so we have the。

![](img/7709f67508e9b6473189b0f9a1be397e_119.png)

Exponent bias。

![](img/7709f67508e9b6473189b0f9a1be397e_121.png)

And remember， we have to represent the number by one point something to the power of something。

Also  one1。25， I afraid。

![](img/7709f67508e9b6473189b0f9a1be397e_123.png)

Times 2 to power1， that is 2。5。And then we should represent025 and also what。First of all。

 the assignment should be positive。And then the expoddent binary right here is。



![](img/7709f67508e9b6473189b0f9a1be397e_125.png)

One plus 127 because the final result should be one and then the bias is 127。

 therefore the expent binary should be one plus 127， which is 128。



![](img/7709f67508e9b6473189b0f9a1be397e_127.png)

How would replace 128， so this is a representation。Next。The fractional bits， okay。

 the fraction bits should be 0。25， which is。

![](img/7709f67508e9b6473189b0f9a1be397e_129.png)

Here is 0。5 and here is 0。25， the binary representation is 01，0001 of zeros。



![](img/7709f67508e9b6473189b0f9a1be397e_131.png)

So we can fill in 0100 to the fractionction bits， building in 1000 to the exponent bits。

 and finally we have the representation in BF 16 for the number1 half。



![](img/7709f67508e9b6473189b0f9a1be397e_133.png)

![](img/7709f67508e9b6473189b0f9a1be397e_134.png)

Any questions here？Okay， good。So people want to continue push the frontier by going fuel to lower and lower precision so later Arminia has this FP8 using 8 bit floating point to represent a number starting from the Hopper H100 GPU so H100 was super popular and the Ccom these days H100200 purely auto stock and people are even using these GPUs it's collaterals to get financing。

嗯。AndRecently， even before it's coming to the market， the blackwell B100 in high demand。

 so what is actually is happening here？So IP8 can further reduce the precision and increase the through force。

Since we have so。So few number of bits， we have to be extremely careful how to allocate this number of bits。

So first of all， we need a sign bit， so altogether eight bit， one bit is designated for sign bit。

 so we are left with only seven bits。For these seven bits。

 we have so many choices we can do zero plus seven， one plus6， two plus five， three plus four。

For of three， et cetera。So actually， these are the two popular used。



![](img/7709f67508e9b6473189b0f9a1be397e_136.png)

You numerical precisions for IPAs。4 bit exponent Ribi Mantia， E4 and3 or E5 and two。

 five bits will be exponent and two bits for the Mantia。



![](img/7709f67508e9b6473189b0f9a1be397e_138.png)

So what is the pros and con？For E4 and3 versus E5 and2。Remember the exponent bit。

It is for expressing larger magnitude。诶， larger dynamic bridge。



![](img/7709f67508e9b6473189b0f9a1be397e_140.png)

Versus the Manteza bay is for precision， so we have five bits for exponent。

 that's a larger dynamic fringe， a lower precision。



![](img/7709f67508e9b6473189b0f9a1be397e_142.png)

Whereus E43， we have a smaller dynamic range and a better precision。



![](img/7709f67508e9b6473189b0f9a1be397e_144.png)

In this for this reason， we found who is really used for representing the grid in the backward class。



![](img/7709f67508e9b6473189b0f9a1be397e_146.png)

Okay， so one year later， Ada has this blackwell， okay。

 so blackwell introduced IP4 four bit floating point is doubling or even making the through for even higher okay。

So with only four bits， we have how many choices do we have？We can have these volume four choices。



![](img/7709f67508e9b6473189b0f9a1be397e_148.png)

For these three raveits， we can either have everything。As themanza， okay， so no exponent wind。

 that's basically four into4。So we can represent from zero to2 seven for the mentea part plus the sign bit。

 we can represent from minus8 all the way to class7 okay。

 so that's 16 values to two color4 from minus8 to positive seven。



![](img/7709f67508e9b6473189b0f9a1be397e_150.png)

And these spaces are equally distanced， so it's linear context。To allocate those four bits。

 another way is to do11 and2， and we have one expent bit but to my Ts bit。

And the number they can represent is actually very similar to in number。

 so we can have sub normalormal region where the exponent is zero。



![](img/7709f67508e9b6473189b0f9a1be397e_152.png)

So we use this equation to power the bias 0， so this is 0。5 versus the normal region one plus。

 so this is 0。75 times total power of 1 minus0 is3。5。



![](img/7709f67508e9b6473189b0f9a1be397e_154.png)

So you can represent the numbers from 0， 0。5 minus1， minus 1。5 all the way to 3。5。



![](img/7709f67508e9b6473189b0f9a1be397e_156.png)

![](img/7709f67508e9b6473189b0f9a1be397e_157.png)

Okay， so it's also linearly distanced， so it's pretty much the same as in except that we are scaled by 0。

5。

![](img/7709f67508e9b6473189b0f9a1be397e_159.png)

Okay， so Y want2 is basically the same as in4。Plus， it's wasting one slot。

 you have a positive zero and a negative zero。

![](img/7709f67508e9b6473189b0f9a1be397e_161.png)

8。😊，So U1M is the same as in four except for that is wasting one slot for zero， it can represent。

Rather than 60 numbers， they can represent 15 numbers because zero is overlap。



![](img/7709f67508e9b6473189b0f9a1be397e_163.png)

One plus two， we also have two plus one， and so E E two and y。

 two bit for the exponent and only one bit for the Mata。

 we can imagine this number will have a larger dynamic range and less precision。

So we'll give two examples001 versus 111 okay， so 001 that's in the subn normalmal region because the exponent bits are all0。

 so the equation will be like this， the bias would be one。The fraction is also one。

 so the number of examine here is 0。5。For the normal region， the exponent is3 and the five is1。

 the manteia is1， so it's  one plus 0 and2， so this is1 minus 0。5， so this number is actually1 okay。



![](img/7709f67508e9b6473189b0f9a1be397e_165.png)

In that case， we can find the representations for all these values essentially from。



![](img/7709f67508e9b6473189b0f9a1be397e_167.png)

嗯。0ero， half， one， one and a half， followed over6。

![](img/7709f67508e9b6473189b0f9a1be397e_169.png)

你 go to。

![](img/7709f67508e9b6473189b0f9a1be397e_171.png)

- zero， minus1， minus4 minus3， minus- 12 and scaled it by and zero and five。



![](img/7709f67508e9b6473189b0f9a1be397e_173.png)

So indeed， it has a larger dynamic range it can represent all the way to 12 rather than previous it can only represent all all the way to seven。



![](img/7709f67508e9b6473189b0f9a1be397e_175.png)

![](img/7709f67508e9b6473189b0f9a1be397e_176.png)

So the extreme case will be using E3M0 and all the bits becomes now becomes the exponent bits。



![](img/7709f67508e9b6473189b0f9a1be397e_178.png)

![](img/7709f67508e9b6473189b0f9a1be397e_179.png)

So for these values， we have everything as exponent。



![](img/7709f67508e9b6473189b0f9a1be397e_181.png)

So this is a very small exponent， one minus seven， this is a big exponent， seven minus three。



![](img/7709f67508e9b6473189b0f9a1be397e_183.png)

哎。So we can see the representation as the largest dynamic bridge is no longer equal distance。

 but the distance becomes larger and larger as the value and larger。



![](img/7709f67508e9b6473189b0f9a1be397e_185.png)

The largest value can represent here is 167。

![](img/7709f67508e9b6473189b0f9a1be397e_187.png)

嗯。So that's the E3 and0。Okay， so so far we talk about everything about quantization about different numerical representations from into 8 to FP32。

 FP 16， Bf16， FP8， now IP4 and E4， any questions so far？Okay， good， no question。

 let's move to the max part， what is quant？So quantization is the process of consuminging the input from a continuous and also large set of values to a discrete set of values。

 for example， given this signal on left hand side， originally the value is continuous。

But now we want to convert it to a discrete set。

![](img/7709f67508e9b6473189b0f9a1be397e_189.png)

So we divide region by five lines， a one， two， three， four， or five。



![](img/7709f67508e9b6473189b0f9a1be397e_191.png)

And we quantize the signal to the closest reach， for example， not only from zero， this is2，2，1，0。

 minus2，0 okay， they are quantized to discrete value。



![](img/7709f67508e9b6473189b0f9a1be397e_193.png)

![](img/7709f67508e9b6473189b0f9a1be397e_194.png)

![](img/7709f67508e9b6473189b0f9a1be397e_195.png)

Given this example， this is the original image， this is a quantized image in 16 colors。

 you can see the other map becomes discrete。

![](img/7709f67508e9b6473189b0f9a1be397e_197.png)

And the difference between the input value and its quantized value is referred to as the quantization error。

And our goal is try to minimize this quantization error。So this is the agenda for the lecture。

 so initially we start with something that is a floating point using arithmetic to the computation and using floating point to represent the weights。

Then we're first going to introduce k means based quantization， so we have a code book。The codebook。

 there can be anything only store the index within that codebook。



![](img/7709f67508e9b6473189b0f9a1be397e_199.png)

So the storage is including two parts， the integer weights。

It's no longer 14 point in integer together with a 14 point code。



![](img/7709f67508e9b6473189b0f9a1be397e_201.png)

And the computation will be done using floating point arithmetic in this case。

So what is good and bad， so the good thing about it is that we are saving the storage by using integer waste。



![](img/7709f67508e9b6473189b0f9a1be397e_203.png)

And the limitation is that we are not saving the limitation。

 but still requiring to use the floating point arithmetic since we have a deco of this。



![](img/7709f67508e9b6473189b0f9a1be397e_205.png)

So let's deep her into how do we deal with this he means quant。This is the example matrix。

 a four by four weight matrix。

![](img/7709f67508e9b6473189b0f9a1be397e_207.png)

Represented into using a 32 bit proteinte point。

![](img/7709f67508e9b6473189b0f9a1be397e_209.png)

So we don't need the numbers to be so accurate， we have 2。09， 2。12， 1。92，1。87。

We don't care such high precision， we can just approximate everything to two okay。

 so that's the design philosophy。So what we do here is we do the K means classroom。To。

Assign a color to each value， for example， everything that is close to。

 we assign a blue color like 2。19，2。121。921。87。

![](img/7709f67508e9b6473189b0f9a1be397e_211.png)

![](img/7709f67508e9b6473189b0f9a1be397e_212.png)

![](img/7709f67508e9b6473189b0f9a1be397e_213.png)

And similarly， we do that for other colors， everything that's closer to that is very close to minus one。

We color them in gray。

![](img/7709f67508e9b6473189b0f9a1be397e_215.png)

We would color them in grid like 0。98，1。08，1。13，0。91， we all quant them to minus1 by classroom。



![](img/7709f67508e9b6473189b0f9a1be397e_217.png)

So what we store here is the index into the centralroid， okay so this is central 0， central 123。

 so for this 2。09 since it's closer closes to the blue centroid and that blue centroid has index of three。

 so here we only need to store the index three on the top。



![](img/7709f67508e9b6473189b0f9a1be397e_219.png)

![](img/7709f67508e9b6473189b0f9a1be397e_220.png)

Previously we are storing a 32 bit floating point2。09。

 now we only store a2 bit integer index that is going to index into this code。



![](img/7709f67508e9b6473189b0f9a1be397e_222.png)

![](img/7709f67508e9b6473189b0f9a1be397e_223.png)

Similarly， we can do it for the rest of the weights， next to one more example， we have 1。48， 1。53， 1。

49， they're all very close to 1。5。

![](img/7709f67508e9b6473189b0f9a1be397e_225.png)

Where is 1。5， That's the 2 century。What is the index that is true， so instead of Storing 1。48。

 we store the index to in one level of indirect。

![](img/7709f67508e9b6473189b0f9a1be397e_227.png)

So how do we reconstruct the weight matrix using the codebook？So on the right hand side。

 it's showing the reconstructed weights。

![](img/7709f67508e9b6473189b0f9a1be397e_229.png)

Okay， so for example， here we have index one and one。

 we look into the table one actually indicates zero， we put zero in the corresponding location。



![](img/7709f67508e9b6473189b0f9a1be397e_231.png)

![](img/7709f67508e9b6473189b0f9a1be397e_232.png)

So we can now calculate the quant error， which is subtracting。



![](img/7709f67508e9b6473189b0f9a1be397e_234.png)

Between this original weight versus this reconstruct weight， and we can get this quant error。

What about the storage， so originally each bit， each weight is represented using 32 bit floating point。

And how many values are there？We have four by four that's 160 by， altogether that's 5。

 12 bits or 64 bytes since each by equal to8 bits。What about after？So we have two portions。

 one is index， one is the centrals for the index。

![](img/7709f67508e9b6473189b0f9a1be397e_236.png)

How many bits do we have for each of the next？Poour values to two bit are enough to represent the index。



![](img/7709f67508e9b6473189b0f9a1be397e_238.png)

How many indexes are there， we have 16 index。So altogether， about 12 or two times 16。

 we need only 32 bits。

![](img/7709f67508e9b6473189b0f9a1be397e_240.png)

How many bytes are there， only four bytes， it is a lot smaller compared with the original storage。



![](img/7709f67508e9b6473189b0f9a1be397e_242.png)

But don't forget， we also need to store the codebook。



![](img/7709f67508e9b6473189b0f9a1be397e_244.png)

So a good book。It's floating很 point。Iigh precision so each entry in the code book is represented user3 tool bit。

For four entries， Okay sometimes4 and 1，28 bits。

![](img/7709f67508e9b6473189b0f9a1be397e_246.png)

Or six impacts。If we sum them up， four bytes plus 16 bytes。Altogether。

 we need 20 bikes using this K means classroom compensation。Which is about 3。

2 times smaller compared with the original size。So this is the。

This is just an simple case in a common scenario assuming we have n bit quant and the number of parameters equal to m。

 which is much larger than total power of n， which is usually common the case where we have。



![](img/7709f67508e9b6473189b0f9a1be397e_248.png)

Very big matrix much larger than 16 than four by four， but the quote book is the same。



![](img/7709f67508e9b6473189b0f9a1be397e_250.png)

In that case， originally， each weight is represented using 32 bit， M weights， 32 m bits。



![](img/7709f67508e9b6473189b0f9a1be397e_252.png)

After that we have。啊。And Mbits， now nowadays， we have Mbits， in this case， two bits。Two bits times m。

 so that's an m bits。Plus。The codebook， each entry is using 32 bit。

 we have total power of N here is total power of2， which is four entries in the codebook。

 so it has total power of n plus n plus five bits。

![](img/7709f67508e9b6473189b0f9a1be397e_254.png)

And since M is much larger than to to do power N， we can ignore the second term。

So the compression ratio would be 32 divided by n times smaller。If any equal2 in this case。

 this matrix is super large， then the saving would be 32 divided by2 that's 16 times。



![](img/7709f67508e9b6473189b0f9a1be397e_256.png)

![](img/7709f67508e9b6473189b0f9a1be397e_257.png)

If we have four bits， which we are going to implement that in the homework。



![](img/7709f67508e9b6473189b0f9a1be397e_259.png)

We have four bids， we have 60 entriest in the cookbook， then what's the conversion ratio。

Is 32 divided by48 big compression， smaller。

![](img/7709f67508e9b6473189b0f9a1be397e_261.png)

Thank you。This is representation， how do we find tune the model that is quantized using pen quantization。

 we will get gradient matrix。

![](img/7709f67508e9b6473189b0f9a1be397e_263.png)

So after that propagation， we've got a gradient matrix。

So we are going to color them using the system color as the weight okay。So blue， green， red， blue。

 green red， using the same color， and then we do good' going to do a group by operation to look the same color together so these four blue values are grouped together。



![](img/7709f67508e9b6473189b0f9a1be397e_265.png)

![](img/7709f67508e9b6473189b0f9a1be397e_266.png)

![](img/7709f67508e9b6473189b0f9a1be397e_267.png)

and these red values are group together， so they corresponding they correspond to the same centroid。

 we're going to reduce them by summing them up， summing them up okay and then multiplied by the vary rate subtracted from the original centroid then we get the fine tune the centroid so there's one iteration of the IGD on a k is quantized neural network。



![](img/7709f67508e9b6473189b0f9a1be397e_269.png)

![](img/7709f67508e9b6473189b0f9a1be397e_270.png)

So first do a group by operation and then do a reduction by suming the map multiplied by the learning rate and subtracted from the original centroid that will give you a the update of the cent。

How does that work with respect to the accuracy， so this is throwing the quantization only what is model size visual out compression so you can go much smaller and this is the accuracy degradation we feel about 10%。

 11% we have very low accuracy degradation and after that the accuracy is going to drop very quickly。



![](img/7709f67508e9b6473189b0f9a1be397e_272.png)

![](img/7709f67508e9b6473189b0f9a1be397e_273.png)

How does it compare with pruning only so this line is showing the pruning only result in purple and we can find that they are pretty much much closer roughly around 10% the accuracy begins to drop。

But the good thing is that。Pruning and quantization can be combined together。

 and you can do both pruning and then quantization that give you the highest concentration ratio。

I think just a few percent， the accuracy is still very well maintained， which is a good thing。

So practically， should we do ping first or should we do consation first？

What does the model size ratio mean for quantization。

 so if the original model size is 100 megabytes now is 10 megabytes， then the ratio will be 10%。对。

If originally you're using 32 bit and the model is 100 mebytes， now you're using 8 bit。

 the model size would be 25 mebytes and the ratio should be 25%。Where why we had our。

So there is actually。That depends on the number of the reduction can be done by let me see actually right here we had calculated on the me let me see。

 let me double check this is just doing the sum， I believe， yes。

 this is just doing the sum because they are all updated into the same central。

A lot of people want to nudge the same centrally， therefore we sum them up。

Somehow they can be partially canceled by a polyping with the learning rate。

 but really matters is how many numbers will go to the same bucket。

 the more number of want to go to the same bucket， the more you want to nu the weight so they're probably we are doing the sun right here。

You're very welcome to try the point to the mean the average。

That the beauty of deep learning is not a fixed science nor edge engineering。 So basically use it。

No matter that works the best。Not necessarily， this is the best approach because just what I did。

In the bank many0 years ago。So back to our question。

 should we do pruning first or should we do conization first？Right。嗯楚。对。研討。That very part。Right。

 that's a good point since you want to do quant prun first because you want to first eliminate a lot of。

Rundundant weights， okay， so you have fewer number of weights to quaine reducing your workload。

A the contest and potentially reducing the quantization error。 So first。

 get rid of those redundant weight before the contest。

So this is the way distribution after fine tuning a approved the model。



![](img/7709f67508e9b6473189b0f9a1be397e_275.png)

Why theres a big bump here because everything close to zero are approvedruned。



![](img/7709f67508e9b6473189b0f9a1be397e_277.png)

Using our magnitude based polling approach， okay？Everything close to zero。

 they are set to zero so these areas get flatter because after fine tuning they become flatter okay so what does it look like after quantization the values becomes discrete rather than continuous distribution they become discrete only a couple of cent this is cent this is one this is another one。



![](img/7709f67508e9b6473189b0f9a1be397e_279.png)

![](img/7709f67508e9b6473189b0f9a1be397e_280.png)

Is there101 is another essential way， and the right becomes discrete。Last。呃 repeat the question。

Any situation where quantization would be more preferable than flu。啱。

Depending on the pruning granularity， of course， growing the pruning。

Any hardware accelerated so it's best to combine them both I don't see any scenario where you don't want to combine pausesp pruning with with quantization unless your hardware doesn't have any low precision units you can only do pruning。

But I don't see a reason where you cannot do pruning but only do quant at this you can do qua grained structured pruning。

So the remaining weights are still death。Okayy， so after the fineuning。

 we can see a slight difference。Right here between these two slides。

 you can see the sroid shifted a little bit from here to here the sroid shifted a little bit that is due to when we are updating the weights remember right here just now have a question。

We are often the gradient some the mo since all these blue gradient are trying to update the blue centroid。

 we want to sum the map， apply the nudge， apply the change altogether together to change this centroid。



![](img/7709f67508e9b6473189b0f9a1be397e_282.png)

![](img/7709f67508e9b6473189b0f9a1be397e_283.png)

Wu Sanany will get changed after a couple of its iterations。And we indeed。

Observed that change between these two slides。This is the， this is after。

Before this after it has seen a slight changed about the position of a。And another question is。

And is the assignment able to get changed and that is so true if the nudge is so big one value might also might also become another bucket。

 so the assignment the color assignment might also change and we are going to implement that in left two which we are going to release next week。

 actually we already release it so feel free to try it out to implement this came means quantization by yourself。

And finally how many bits do we need in practice previously we are showing two bits for illustration purpose in practice we find for this is for an extended convol layer before after four bits。

 the accuracy is going to drop very sharper， but before that the accuracy can be very well maintained。



![](img/7709f67508e9b6473189b0f9a1be397e_285.png)

Butut a layers after two bits， two bits。

![](img/7709f67508e9b6473189b0f9a1be397e_287.png)

Before two bit， the accuracy is still well maintained for the top five and top five accuracy。

And in practice nowadays for large language models。We're going to see that in La four。

Forbitit is very enough， is quite good maintaining the accuracy of large language models is transforming our。

So another idea。Composing this deep compression paper is using halfmancoing to further compress it since the weight distribution is not uniform okay。

 so some of the weights appear very frequently， some of the weight doesn't appear very frequently so we can encode the weights using different number of bits。



![](img/7709f67508e9b6473189b0f9a1be397e_289.png)

![](img/7709f67508e9b6473189b0f9a1be397e_290.png)

For different weights。They can use different variable length en codingd。

 so we can use fewer bits for the more frequently appearing one and use more number of bits for those less frequently appearing rates。



![](img/7709f67508e9b6473189b0f9a1be397e_292.png)

![](img/7709f67508e9b6473189b0f9a1be397e_293.png)

So put them together， we have this three stage pipeline for deep compression first using pruning to reduce the number of weights by the train the model。

 pruning retrain it repeatedly。

![](img/7709f67508e9b6473189b0f9a1be397e_295.png)

And then by quant， when first cluster the weight using K means a passing， generate a code book。

 16 entries， four bits or four entries， two bits。Then we quantize the widths with a code book。

 retrievetrain the code book， and repeat this process。



![](img/7709f67508e9b6473189b0f9a1be397e_297.png)

AndFinally， we can encode the weight using different bits for different weights。



![](img/7709f67508e9b6473189b0f9a1be397e_299.png)

And as a result， we can achieve very high compression ratio across different neural networkss。

40 times for the math， 39 times for the net5，45 times a like that。

 even the good resonate can be compressrised by an order of magnitude。



![](img/7709f67508e9b6473189b0f9a1be397e_301.png)

And this is the model size before and after the contentation。

 this is original accuracy and the compressed accuracy， the accuracy can be very well maintained。



![](img/7709f67508e9b6473189b0f9a1be397e_303.png)

![](img/7709f67508e9b6473189b0f9a1be397e_304.png)

Even for very small and compact neural nets like squeeze nets。

 we're going to introduce in a neuroarch factor search session。



![](img/7709f67508e9b6473189b0f9a1be397e_306.png)

It's very small to begin with like 0。47 megabytes。begin with its 4。

8 megabytes to begin human compared with Alex that is already 50 times smaller and 50 times smaller compared with Alex that with exactly the same accuracy。

 but even that can be compressed by deep compression by a0 of magnitude so 10 times smaller。



![](img/7709f67508e9b6473189b0f9a1be397e_308.png)

Maintaining the accuracy of the model is only as 0。47 nanobyte and put it in the pocket okay。



![](img/7709f67508e9b6473189b0f9a1be397e_310.png)

Yes， that's the hyperparmeterton， how to find that hyperparameter we're going to find where the axis of the laser are。



![](img/7709f67508e9b6473189b0f9a1be397e_312.png)

Here we get the accuracy drop in four bit， so K equal to 16。Here accuracy job by two bits。

 so okay equal goes to four。

![](img/7709f67508e9b6473189b0f9a1be397e_314.png)

We are going to play with that in the homework。Good question。All right。

 so how do we compute on a K means based weight quantization。

 we have to decomprise it okay by mapping it from the index into the original weight。

 so here we have the codebook， we have the quantized weight we have the first decod it from unsigned in which is just the index into the floating point weight okay and all the remaining operations will be done in floating point so it save the storage。

 but it doesn't save the computation。

![](img/7709f67508e9b6473189b0f9a1be397e_316.png)

![](img/7709f67508e9b6473189b0f9a1be397e_317.png)

![](img/7709f67508e9b6473189b0f9a1be397e_318.png)

But it's still very helpful for in the modern transformers and large language models because for a single user for。

On a generation phase it' completely memory bonded， compute bonded。

 so using IP 16 is totally fine but reducing the memory footprint by four times compared with IP16 is super helpful。

Okay， let's take a short break before we jump into the next part， which is linear quantization。Yeah。

All right， welcome back so let's continue a discussion about linear quantization。

 so now we want to use integer weights integer weights to represent the values and also we want to use the integer arithmetic。



![](img/7709f67508e9b6473189b0f9a1be397e_320.png)

To do the computation so that we want to get acceleration and also get a storage saving so let's see what is linear quant This is very widely used if you're using a mobile phone running an application locally that's highly possible linear quantization is used here。



![](img/7709f67508e9b6473189b0f9a1be397e_322.png)

So what is linear quantization， So given。This is our familiar matrix4 by four weight matrix。

 so now we want to quantize them into only integer values okay right here is10 is minus2 by1 minus10000 y equal to1 so now this is the quant the version of the original matrix so 2。

09 becomes1 minus 0。98 becomes minus2。

![](img/7709f67508e9b6473189b0f9a1be397e_324.png)

![](img/7709f67508e9b6473189b0f9a1be397e_325.png)

![](img/7709f67508e9b6473189b0f9a1be397e_326.png)

So here we have two parameters where I'm going to learn how to determine these parameters。

 but let's just see how that works。We have to define zero points and a scalar and a scale factor。

So we or you subtract the matrix with the zero point， multiply the skating factor。

And we get the reconstructed weight matrix， so 2。09 becomes 2。14 minus 0。98 now becomes minus 1。

07 and this is the quantization error quite small so they are roughly very well correlates between and after quantization so the magic here is how do we find how do we calculate this zero point。



![](img/7709f67508e9b6473189b0f9a1be397e_328.png)

![](img/7709f67508e9b6473189b0f9a1be397e_329.png)

2 bit s integer versus the scale， which is a 32 bit floating point number。



![](img/7709f67508e9b6473189b0f9a1be397e_331.png)

So what is a zero point？And scaling factor， so were going to map this integer value Q integer value Q subtracted from the integer zero point。



![](img/7709f67508e9b6473189b0f9a1be397e_333.png)

And multily by the scaling factor， we get the floating point running， so basically Z。

 which is the zero point。

![](img/7709f67508e9b6473189b0f9a1be397e_335.png)

![](img/7709f67508e9b6473189b0f9a1be397e_336.png)

啊，那。It allow a real number r equal to zero， which r equal to zero to be exactly represented by a quantized integer Z。

 so z will be mapped to zero okay。

![](img/7709f67508e9b6473189b0f9a1be397e_338.png)

And then we have another scale factor to scale the dynamic bridge。



![](img/7709f67508e9b6473189b0f9a1be397e_340.png)

What that means is that we have a floating point dynamic range from R mean to R max。

 this is the range of the datata values。We also have a dynamic range for the each value from Q mean to Q max。

And the zero point maps z to zero from integer space to 1 floating point stage to 1 floating point。



![](img/7709f67508e9b6473189b0f9a1be397e_342.png)

Great。

![](img/7709f67508e9b6473189b0f9a1be397e_344.png)

So this is corresponding to a different number of bits， you have two bits。

 the QB equal minus2 Q max max equals to1， you have three bits or minus4 positive three。

 so the integer。

![](img/7709f67508e9b6473189b0f9a1be397e_346.png)

Q me and Q max are fixed。So how do we calculate the scaling factor okay so Q mean has to be mapped to R mean and Q max has to be mapped to R max using the equation where we map Q max minus z field by S。

 we get the R max Q mean minus z fieldd by s， we get the R mean。

 we can subtract them and then divided， we can get the scalingating factor equal go to R max minus Rine。

 which is here R max minus R mean， the dynamic range of the14 point range。



![](img/7709f67508e9b6473189b0f9a1be397e_348.png)

![](img/7709f67508e9b6473189b0f9a1be397e_349.png)

![](img/7709f67508e9b6473189b0f9a1be397e_350.png)

Divided by the Q max minusq me the dynamic range of theteger integer scaleal。



![](img/7709f67508e9b6473189b0f9a1be397e_352.png)

![](img/7709f67508e9b6473189b0f9a1be397e_353.png)

So s can be calculated in this way R max minus r mean divided by q max minus qb。



![](img/7709f67508e9b6473189b0f9a1be397e_355.png)

So given our matrix， this is our familiar matrix， the max value is 2。12 me value is minus 1。08。

 we use this equation to calculate the dynamic range of the floating point versus the dynamic range of the eachteger。

 and now we can get a sc factor to be 1。07。

![](img/7709f67508e9b6473189b0f9a1be397e_357.png)

![](img/7709f67508e9b6473189b0f9a1be397e_358.png)

That's how we calculate the skin factor。Now we can calculate the Z， okay， so since we already have s。

 we can plug in s to get the Z。And it has to be an integer。

 therefore we have surroundeded to the closest integer value。In our example， Q mean is minus 1。

08 in the right part we plug in the equation。

![](img/7709f67508e9b6473189b0f9a1be397e_360.png)

And then we can log in to。pl in the  Q being which is minus2， since we have only two bits。

 two minus2， army is minus 908， minus 108， as we already calculated is 1。

07 and we round it with Z zero points is minus1。

![](img/7709f67508e9b6473189b0f9a1be397e_362.png)

So now let's talk about linear quantized matrix multiplication。

 so how do we use integer unit only use integer unit to calculate the matrix modification。

So linear quantization is I find mapping from integers to real numbers using the equation we just talked about。

So consider the following matrix modelations y equal to Wx。

Originally there are1 floating point values now we want to convert them convert it into integer values we are going to implement in the lab。

 so I will pay ready attention to the derivation for the remaining 20 minutes。



![](img/7709f67508e9b6473189b0f9a1be397e_364.png)

So we plug in the equation where r equal to s times  Q minus z s times q minus z for the output for the weight for the input activation plugging in。

 and then we rearrange them by subtract by moving S Y to the right hand side。

 moving z y to the right hand side。

![](img/7709f67508e9b6473189b0f9a1be397e_366.png)

![](img/7709f67508e9b6473189b0f9a1be397e_367.png)

And then we can expand the equation from thisal to thisceral from all the way we get is four different terms。

 so far， a very simple derivation。

![](img/7709f67508e9b6473189b0f9a1be397e_369.png)

So we want to use Mbit。😡，For example，8 bit integer multiplication。I use 32 bit。Integer addition。

To prevent overflow。So first of all， the skating factor。

And then we have this integer addition and then this yellow part are all constant。

 the weight is constant。

![](img/7709f67508e9b6473189b0f9a1be397e_371.png)

At zero point is a constant。

![](img/7709f67508e9b6473189b0f9a1be397e_373.png)

Profille zero points is constant so all these can be pre computed， it's not in the runtime。

 no runtime overhead and now let's focus on the scaling factor。So empirically。

 the scalingating factor as w as x divided by Sy is between zero and1。



![](img/7709f67508e9b6473189b0f9a1be397e_375.png)

And from this paper here can be represented by22 power of minus n times in value。

 okay a fixed point value between 0。5 and one。And this modification can be done with a fixed point modification。



![](img/7709f67508e9b6473189b0f9a1be397e_377.png)

And the total power of minus n can be done by a simple bit shift。

 so we don't need floating point unit。To implement this blue part。



![](img/7709f67508e9b6473189b0f9a1be397e_379.png)

So for this part we scale them to end integer， this part can be pretty imputd。

 and the last part is the end integer addition。

![](img/7709f67508e9b6473189b0f9a1be397e_381.png)

And let's look at the middle part， the Zw times the qx， so the zero point of the weight。

What is distribution like？

![](img/7709f67508e9b6473189b0f9a1be397e_383.png)

So it's roughly following a normal distribution， okay？So roughly centered around zero。 Okay。

 so we can safely set Z W to be0 because it's very symmetric and。



![](img/7709f67508e9b6473189b0f9a1be397e_385.png)

Roughpha0 is map to zero and so we set zw to be0。And what I mean is that originally C maps to zero。

 now zero map to zero from the fixed point to the floating point range。



![](img/7709f67508e9b6473189b0f9a1be397e_387.png)

![](img/7709f67508e9b6473189b0f9a1be397e_388.png)

![](img/7709f67508e9b6473189b0f9a1be397e_389.png)

In that case we can simplify the equation where now z becomes zero。

 so the scalingating factor will be using the absolute value of the R divided by total power of n minus one much simpler calculation for the scaling factor previously we have to do this calculation to map it now we just do a much simpler calculation to map it。



![](img/7709f67508e9b6473189b0f9a1be397e_391.png)

![](img/7709f67508e9b6473189b0f9a1be397e_392.png)

![](img/7709f67508e9b6473189b0f9a1be397e_393.png)

![](img/7709f67508e9b6473189b0f9a1be397e_394.png)

So we can。

![](img/7709f67508e9b6473189b0f9a1be397e_396.png)

Safely get rid of for part since ZW is0， it'ssymmetric then we are left only with。These two terms。



![](img/7709f67508e9b6473189b0f9a1be397e_398.png)

The first term， which is can be done by a bit integer multiplication， the QX and mean QW。

 that's where the most of the weight lifting is happening in the computation。And we can since zw is0。

 we are only left with a single term is a constant because z is a constant QW to quantize the weight。

 the weight is also constant。

![](img/7709f67508e9b6473189b0f9a1be397e_400.png)

![](img/7709f67508e9b6473189b0f9a1be397e_401.png)

But we are only left with the ZY。And the blue part is the bulk of the computation where the bulk of the computation happens。

Now let's consider adding back。The bias okay so far we are economic bias now we consider following the fully connector layer with the bias okay so the bias can be also with plugging equation right here the bias can be also represented by subtracting the bias and then multiplied by the scalingating factor of that bias。



![](img/7709f67508e9b6473189b0f9a1be397e_403.png)

![](img/7709f67508e9b6473189b0f9a1be397e_404.png)

Since previously we mentioned ZW is0， it's following a normal distribution， we can set ZW to be 0。

 so integer 0 map to the 14。0。

![](img/7709f67508e9b6473189b0f9a1be397e_406.png)

I think'll eliminate everything associated with the ZW so we are left with the equation here。



![](img/7709f67508e9b6473189b0f9a1be397e_408.png)

We can force this SB。你哋咩。

![](img/7709f67508e9b6473189b0f9a1be397e_410.png)

The scaling factor for the bias versus the scaling factor of the weight and activation versus the Z。



![](img/7709f67508e9b6473189b0f9a1be397e_412.png)

Similar to the weight， the distribution of the bias is also following a normal distribution which is so we can set zb to be0 we can set zb to be0。

 and we force SB to be equal to Sw times s x so that the equation can be simplified in this way we absorb to B together with these two terms。



![](img/7709f67508e9b6473189b0f9a1be397e_414.png)

![](img/7709f67508e9b6473189b0f9a1be397e_415.png)

And so force has be equal to SW times S x。It says like this， continue with that renovation。



![](img/7709f67508e9b6473189b0f9a1be397e_417.png)

We are going to move SY to the right hand side and move Z Y to the right hand side。

 so we are left with this equation。

![](img/7709f67508e9b6473189b0f9a1be397e_419.png)

![](img/7709f67508e9b6473189b0f9a1be397e_420.png)

So QB Z XQW quant wave， the point of activation bias the biasers。

 they are all constant so we can pre computeute them。



![](img/7709f67508e9b6473189b0f9a1be397e_422.png)

And we define the QB minus the Q W to the Q bias since it's a constant。

 then we can simplify all the equation to something like this。



![](img/7709f67508e9b6473189b0f9a1be397e_424.png)

![](img/7709f67508e9b6473189b0f9a1be397e_425.png)

![](img/7709f67508e9b6473189b0f9a1be397e_426.png)

As look closer into this equation， the blue part is the bulkcott of the computation。

 most of the weight we is happening in the blue part， but low bit integer multiplication。



![](img/7709f67508e9b6473189b0f9a1be397e_428.png)

![](img/7709f67508e9b6473189b0f9a1be397e_429.png)

And we can rescale the scaling factor to nbit integer like8 bit integer followed by shift we just discuss about it。



![](img/7709f67508e9b6473189b0f9a1be397e_431.png)

![](img/7709f67508e9b6473189b0f9a1be397e_432.png)

And finally， we have MB integer ad。Okay， so now everything can be cast into a low precision integer operation。

我哋 we啊。Use convolution rather than a fully connected layer。



![](img/7709f67508e9b6473189b0f9a1be397e_434.png)

So compared with the fully connectedor layer now we run the convolution essentially the revision is pretty much the same you're going to visit in the lab。

 we just replace multi with convolution， we're all linear okay so blue part is where the green part is where most of the computationnot is happening。



![](img/7709f67508e9b6473189b0f9a1be397e_436.png)

So this is a computation diagram where we have previously the quantized weight。

 this is the quantized input calculation we do into the con。

 the convolution is added with the bias the sum in sum using a 32 bit register for the summation to prevent overflow so it in it be in 32 bit in for the summation register and all the sum is done in 32 bit and the bias scale by the scalingating factor and the add the zero point and finally we get the quantized output。

So what's the difference with the K means quantization previously we are using。

32 bit bullet point to do all the computation。 Now we are using integer to do all the computation。

So we are saving not only the storage， but also we are saving the compute。

So we are going to implement this in lab two， so make sure you understand the lecture here。

 I'll pause a little bit for you to in case you have any questions for the derivation。It。对。Yeah。

 for Reddo， you basically have nothing on the。Nothing on the on the left。

 so you are waitinging half of the dynamic range if you set the biasers the zero point of the bias to be0。

 which is this case。It raise the half of the dynamic range。If no more questions。

 let's see how does the accuracy compare with the floating point so the this figure is showing the floating point versus8 in figure so this is the latency versus the accuracy ideally we want something on the top and left corner and consistently the8。



![](img/7709f67508e9b6473189b0f9a1be397e_438.png)

![](img/7709f67508e9b6473189b0f9a1be397e_439.png)

Is having a better trade off on the plot compared with the IP。

The floating point counterpart higher accuracy， same latency or same accuracy lower levels。



![](img/7709f67508e9b6473189b0f9a1be397e_441.png)

On the left hand side is showing for Re 15 in Section3。

 the1 floating point conceal the integer accuracy。

![](img/7709f67508e9b6473189b0f9a1be397e_443.png)

And nowadays， this8 bit quantization becomes very mature。

 does the solution to accelerate and compress neural names。

And most of the hardware have 8 bit integer units， so that's very widely used if you're using running neural nets on the phone on a microcontroller on an edge device。

 this is a very critical solution。All right， so that concludes our second part。

 which is the linear quantization， so different from he quantization which only save storage but doesn't save computation。

 linear quantization can save both storage and the quantization。



![](img/7709f67508e9b6473189b0f9a1be397e_445.png)

![](img/7709f67508e9b6473189b0f9a1be397e_446.png)

So what is next， Can we go even lower precision， So we are going to talk about binary turnernary quantization in the next lecture。

 only use one bit or two bits to present each。Okay， so let's summarize today's lecture。

 we first review， introduce the data types， floating point， what is integer。

 what is a floating point representation。What is the exponent bit， what is the9a bit。

 what is sub normalormal origin， how do we represent very big numbers， what is the FP4， F8。

 different configurations， E2 M4， eta。E5M2， et cea。

 and also we visited the basic concept of neural naturalural quantization to turn convert weight and activations to discrete values。

And then we introduce two types of quantization， one is K meanss quantization。

 we're going to see them in the homework and also the linear quantization。

 we went through a long derivation， make sure you can translate them into the code in lab2。

And here are some references。And that's all for today's lecture。



![](img/7709f67508e9b6473189b0f9a1be397e_448.png)

Thank you。
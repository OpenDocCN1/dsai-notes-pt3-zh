# 【麻省理工】高效机器学习 MIT 6.5940 EfficientML 2024 年秋季 p10 P10 Lecture 6 - Quantization Part II -BV1o7jzzwEST_p10-

All right， good afternoon everyone， let's get started。

 so today we are going to learn about lecture six， the second part of the quantization lecture。😊。

So in the previous lecture， we introduced the basic techniques of quantization。

 which is a super important technique both in the E age and also in the large language model age。

Quantization is very widely used， no matter if you want to deploy the neural network on the phone or the edge device or in the cloud。

 this is a very useful technique。A very widely adopted in industry and actually a big shortage of engineers currently who can specialize in such techniques so in today's lecture。

 we'll first review the linear quantization and also will cover two important concepts。

 one is post training quantization， PTQ， the other is the Q A the quantization aware training。

 how do we fine tune the model so that we can recover the accuracy。

 remember like pruning without about pruning and how to fine tune p model to recover the accuracy and similar here quantization we quantize and then fine tuning。

QAT。And then we'll talk about binary internal tunnel quantization to further push。

The compensation bit to lower bit only one bit。And finally we'll introduce automatic mixed precision quantation。

 not every layer required same number of bits， just like improving。

 some of the layers are more sensitive， some of the layers are less sensitive。

 so we want to treat different layer differently to minimize the storage and maximize the efficiency in similar case for quantation。

Okay， so this is where we were left over since last on Thursday， we talk about K meanss。

 first we started with the floating point weights， B32 for the weights， B32 for the activations。

And then the second part we quantized the weight using the K means quantization okay so for example here。

 this is our peri matrix， we have a codebook and each entry with just store a2 bit or four bit low precision index looking into the weight。

So that's the code book。So the computation is still arithmetic since we have to de quantized the weight into floating point。

 it save storage but doesn't save the computation， which is still useful for large language model inference batch size of one where is memory bonded。

 not compute bonded and weight is the weight is the memory bottlene so very useful technique。

 we are going to implement that in the。 hopefully are you will all downloaded。

 we will have them available in our website for that too。Lastilt lecture。

 we also introduce linear quantization， so both the weights and activations can be quantized to interior values。

And the computation is also done in integer parristhmetic。So we have a bias。

 we have a skating factor， we derive the equation for that。So this is the k means quantization。

 we have a cluster impact， we have a centroid。And then we can fine tune aensroid。

We can see the accuracy is very well maintained， we can even combine p and quantization to further push the model size to be a smaller。

When we are talking about linear quantization， we introduced the zero points and the scaling factor。

So for two bits， we can represent four numbers in four colors。

And this is the quahe value minus zero point model by the steer factor。We can get them recovered。

P32 weeks。So remember how to calculate the scaling factor， so scaling factor basically maps。

The interior range to the floating point range。So this is the interior range。

 this is a floating point range。And this zero point maps z0 point in integer representation into zero in the 14 point representation。

And we went through all the math to calculate in a quantized matrix matrix modification。

 so theres single layer and LP， what is the breakdown about the computation so this is the majority of the computation done in low precision integer。

Cause the bias。This can be done by linear operation and also the shift operation。And finally。

 plus the integer ad。For convolution it' very similar with this replace matrix modification with convolution。

 majority of the job is done in the integer convolution。Okay。

 so how should we get optimal linear quantization parameters， S and Z。

 So we' will talk about quantization granularity， similar to pruning granularity where we can prune a single weight。

 We can pe a row of weight。 we can prune the whole channel or a whole filter or the entire channel to the different granularities for pruning and similarly。

 there are different granularities for quantization。

And then we are going to talk about dynamic range clipping。

 so we may have a pretty big dynamic range， how do we clip them？And finally， about rounding， like 1。

5， should we run it to one， should we run it to two。

 should we s passiveically round it to talk about rounding。

So let's start with I start with quantization random narrative。

So we will first talk about per tensor quantization。

 you use one scaling vector to scale the whole tensor。

 so this is tensor quantization followed by per channel quantization so for one channel。

 all the values in one channel share the same。Skating factor。AndW which has more skin factors？

P channel quantization we have if you have like seven channels。

 you will have seven scalingating factors but here per tensor quant。

 you have one scalingkating factor for the whole tensor。And finally， group quantization。

 this is very important for after blackwell architecture and India blackwell architecture。

 group quantation is very useful for four bit or below when introduce。

Pro vectoror composition and also the MX data type， the shared macro exponent data type。

Which is a very interesting data type。Lower precision。Okay， so let's start with persor quantization。

 which is very widely used。These days。So we have one skin factor for the whole answer。

Using a single scaling factor for the whole wake tensor。That works quite well for large models。

 but for small models。People observe this degradation of accuracy。And why is the reason。

 what is the reason？This potential quantization suffer from。Accuracy degradation。So you can plot。

The China index。Here is the range okay， we can see the range actually differ a lot。

 some of the layers have a pretty big range， some of them have a little range。

If you use the same scalingating factor for these diverse channels， of course。

 you can have very good feeling for them all。So the failure comes from the large difference in the ranges of the weight across different local channels。

 some of them have pretty big outliers， outliers are the weight values that has either very big value or super small value。

Have is a honor。So that calls the。You are wasting the dynamic range。

 you observe very different behavior compared with other channels。

 so if you use the same scanning factor across all different channels。

 you cannot very well represent them。So the solution is per channel quantization。

 we want to treat these different channels individually。

 okay so that we can have a specialized scaling factor for each。And how does that look like？

So this is our familiar4 by four matrix， input channel， output channel4 by four。

Well compare perentnal quantization versus the previous pertensor of quantization。

Using professor quantization， we want to calculate。First。

 the scaling factor in order to calculate the scalingating factor。

 we want to first have the power max， the power max， which is the max valuable。

The value which has the max absolute value in the tensor， which is 2。12 in this case。R is2。12。

And here we are using how many bits， two bits。2 bits， so Q max equal to1。

 so R max divided by Q max using the equation we derived in the last lecture。

 we can find the scalingating factor that map。あです。Interger range into that fo point range。

So the scalingating factor is 2。12。So we have the scalingating factor now we can quantize the matrix since we are usingsymmetric quantization。

 so 0。0。So for example， 2。09。Here， divided by。2。12， that's approximately 0。9。

 something is very close to  one， so quant that to one。minus 0。98 divided by。2。12。

 the absolute value is smallerer than 0。5 therefore both quant to 0。But oh， I was so long。

Repeat that and quant it each。So this is the quantized tensor。

And if you can compare with the reconstructed cancer， we multiply eachide with。The scanning factor。

 of course， the pi is in zero， so we can directly multily so this is the reconstructing。Matrix。

And we can calculate the difference， 2。28。And now let's see how does it look if we do the per channel quant rather than treating the whole tensor。

 now we treat each each row each channel individually。So let's first look at the first row。

 what is Rx。Ourmic said 2。09。Therefore， the scalingkating factor is 2。09。Second row， R max is 2。12。

 skating factory 2。12 and so on Okay so different channels now we have different。Scanating factor。

 which is the max value of the absolute value of that row。And now let's see how do we contact them。

Now we are using different scaling factors for different roles。

And so that we can quantize it in this way。For example， previous by 2。09。

 we are using pro se quantization， were divided by 2。12。 now we are divided that by 2。0。

It's very close， it's actually a why。And the second value divided by 2。09。

 the actual value is smaller than 0。5， therefore surrounded to 0。

And this is the reconstructed of cancer。Compared with the previous reconstructed ten using。

Pensor composition。Now the value is more diverse， you have 2。19， you have 2。1 tool， 1。9 tool。

 etc cetera。And the reason is that we're using a different scaling factor for a different time。

So actually， the reconstruction error， the quant error is smaller than the potential quant。

 So we just want to use this very simple example to show you the。

The intuition where the pernal quant can have a usually have a lower quant error compared with pertensor。

And， in particular。What do you see about which one is different？This is the quantized。

Tenssor using peranno， this is quant tensor using pertensor quantization。

 we observe this value is actually different。The rest of the value are all the same， 10，10， 10，10。

 over this value is here。そはゼ。What was the reason for that？The scaling factor， for example。

 you can look at this value， 1。03。Using the pertensor quant， it will be divided by this scale。

Divided by 2。12， the absolute value is smaller than half。

And therefore is quant to 0 because the value is smaller than 0。5。It'sRo to zero。But in this case。

 this minus 1。03 will be divided。By was getting factor 1。92。The absolute value is larger than 0。5。

This 1。03 is larger than half of 1。92。They're always quantized to minus as one。

So that's the subtle difference， you have a fine grain。

 more fine grain scalingating factor compared with a single scating factor。Therefore。

 the representation will be more accurate， smaller quantization error using the perernal quantization and potential quantization。

So， of course， there's trade。What's bad about cancer per channel quantization？

You need to store more values， more scaling factors。

One is scalingating factor now channel you need one， so there's no free lunch。

 always a tradeoff you need to store more scalingkating factors。O。

So let's continue if we want to go even lower precision。

We need more accurate representation and more flexibility。

So so we can actually shrink the group size rather than。

per channel can further reduce the group size。we call it group quantization。

Using group quantization will introduce。per vector quant and also the MX data data type。

 micro exponent data type。very you。So that's first moiv。G compensation。I mean， Is。

Blackwell generation GPU。Which is super powerful when you compare the performance。

So we're comparing the H100 right here。GB 200。Gce flagwell200。好。This is running。Another model。

It has a very big improvement compared with the H100。

 the Black hole architecture compared with a hopper architecture。Heres7X improvement。

And the right hand side， we see a new bit of。A new tensor core called FP4， Tensor core。

 so these are we already from risk FP 16， DF 16，4 and half。Pa our flos。In a times of core。

9ine pal pad ops。FP 8，6。N pet flops， I4， 18 petal flops，2 x。Two x。

 the peaks were put compared with IP8 and I intake times more。So blackwell GPU。

Introduce this microtensor scaling。So that we can maintain the accuracy。Of FP4。Models。

And in order to do that， that's basically what we are going to learn group quant。

 having an even smaller group size to have a fine brained scaling factor so that you can have more accurate representation using lower precision。

So let's jump into that。We will first introduce the Bx quant per vector a back per vector scaled quantization。

SoPrevious， we have a scaling factor for each tensor， the per tensor quantization。

And now we want to have a scaling factor for each sub factor。some better and there some vector。

so rather than R equal to scalingkating factor， R Q minus z。

 now we have two levels of scalingkating factor， one global and one local。

This global scaling factor is a14 point core grain scalingkating factor for the whole cancer。

We also have a integer per vector。fineine grain per vector for each vector， smaller granularity。

It's getting a factor。We are going to modify these two scalingating factors together。

To scale a Q minus C。So that's achieving a balance between accuracy and the hardware efficiency。

By the fact that we can have a more expensive floating point skin a factor。

But they are at a very co right。So let let us。I'll try to understand this again。

Which is a more expensive scaling back。For tenor one or the。For back。Which one is more expensive？やピ。

S this can be in before or if they。So this is more expensive。With IP660 minutes。

 very expensive getting effective。But we can have it as a very coarse granular。

 the whole tensor have only one such expensive FP16。High precision is getting factor。

Only having that is not enough， we compound that with the less expensive integer scale effect。

And fine breath。So we have a less expensive skating factor for only low precision。

 but on a final regular， just a couple of weights， we have one scalingating factor。

So that's a very smart way to have on both sides。So in order to calculate the memory overhead。

 let's see how thats work。 So we have a four bit content for the weight。

 we have four bit per vector scale， so this is four bit。Sting factor for every 16 amendment。

16een ada right here。And we also， what is the effective bandwidth width？

So each audio is represented in four bit。And then we also have a four bit scaling factor for every 16 adas。

 so the four bit skating factor is imized across 16 different adas。Plus the original four bits。

So it's altogether 4。25。4。25 bit。That's the way to calculate。The hour had a two levels dating。

So in that context， we can have multiple levels of skin factor。

We can have the third level0 level one。Continual。Different levels。

 So let's see what we have learned so far。 How does that fall into this。This big picture。

We introduce this per channel quantization， okay， we have a scalingkating factor level zero skating factor for the whole channel。

So the data type for the weight。But the weight in red is into four， and then group size， I0。

 level zero， group size is per channel， the whole channel share a P16 scaling factor。

The effect your with is four。Since we have four here Im assuming we have many channels， thousands。

 tens of thousands of channels in our。This F16 divided by 10，000 can be negligible。

 so youve back to a bit with Israel before。And in VS quant， in VS quant。

 the theta P is also in the four， so each value is four bit。And then the L0 book size is 16， ask me？

I 16 adats we have a skating factor。So the s factor is I sine into4。

OkayAnd the next level group size is per10， the whole channel also share a K16 scalingkating factor。

So what is effective be with？F bit and then another four bit is giving thank about share by 16 values。

And this actually  16 bit can be divided by tens of thousands that can be ignored。

 so we have two and four and a quarter， that's the effective bitway。So now all comes the famous。MX4。

 I6， and MX9 data type。So what I started with MX4。So data scientist S1 M2。

Remember in the last lecture？I have one sign bit， we have two mentiza bit， what is missing。

They experiment a bit。Where is the expon？Actually sure they are here。

So we have one equivalent that is shared by two values。I one bit share our two letters。

We also have an a bit scaling factor on this E8。Only exponents。Shared by 60matics。

So these are the two levels of。Skinating factor。And now we can quickly calculate what is the effective precision。

 bandwidth with。For。One bit for sine，2 bit for the Mata， three bits， right？

And then we had two bits shared， I told that is。sorry， we have one bit right here， E1。

 one bit for share by two values， so that half a bit。And finally。

 we have eight grade shared by 6 values， that's another half big。

So3 plus half plus a half does's altogether four bits， that's what we call it Mx4。We also have Mx6。

 which has Y sign beds。Four menza bit， that's four five bits altogether。

 one exponent share by two values。8 phone them to share by 16 matters。85 plus a half。

 plus a half of six。I'm seeing enough for the IX9。Next time we have one song bed，7 myisza bed。

A bit here， and then we have one。One bit of exponent shared by two values， group size of two。

 and then eight bit of exponent shared by one group size， which is 16。So that's eight plus half。

 plus half thats nine bit。So these are the are more fancy。Representations。Going lower position。

And group quantization， which is super helpful to maintain the accuracy for such fine grain quantization gradularity。

All right， so let's switch here and talk about next topic about dynamic range clipping。

So dynamic range matters a lot since our it can change across different input。

 some of them may be large， some of them may be small。

 but how do we determine the dynamic rich because that's very crucial since the skating factor is calculated by dividing the dynamic range between the quant value versus。

The啊 floating point。So given a bunch of images， they may have very different dynamic range for each。

So to determine the floating point reach， the activations。

 we need to gather the statistics before deep point in the model。And there are generally two methods。

 two ways。To calculate the dynamic range。So if the model is trained by yourself。

 so if you train the model by yourself， if you have access to the training recipe。During training。

 we can actually calculate。And it Greens by maintaining a exponential moving average。

And what is that， we maintain this arm and armmenian。Ourmics ourmen。Across different iterations。

 So I t -1。T this is T是 RT basically equal equal to阿尔法。T plus1 minus。

We are using this discounting factor to discount。The previous。Dnamic range。

With the current dynamic I bridge。可。So the larger the RFR， the more we are using the recents。

大 I make过。Okay， so we are smooth。The dynamic range by using alphapha。What is the extreme case？

阿尔法也不图吧。If alpha equals to one， we are not using any of the old dynamic range because this term becomes zero。

TheInvesting to region。But that is only possible if you have access to the training process。

 if you train the model by yourself。If the model is twined by somebody else。

 we don't have access to this whole twining process。Therefore， it's very hard。

 it's not possible to estimate the dynamic rich in that way。But that is the most common case。

 sometimes we just download a model from Hing phase we quantize them we deploy them。

Then in that case， how do we get a dynamic range？We want to maintain a collaborationlibration batch。

Claration data set， and just use that collaborationlibration set like a bunch of images or a bunch of texts。

To calculate to estimate the dynamic range。We can use a dynamic range for you in this collaboration set。

To represent， to assume that is representative for the。Iput images or text from other sources。Okay。

So by running the collaboration batch， we have two ways。Try to find the RmX。

We probably don't want to use the full R maxax， so actually there is a tradeout here。

Say this is a distribution。Of the activation。We can observe there is a very long tail。

Of distribution， some of the values are super big， but you have a very small small amount of big values。

 very small amount of reason。Very negative values。So if youll set the me and the max。

To be like here versus here， you have a big waste， youre wasing most of the representation。Because。

You have only a few， very few valuess in the extreme corners。

So assuming we want to push the me and max to be somewhere here where there are least some ways because if you squeeze in closer。

 the distance between each composition boundary will be smaller and the representation for these values in the middle。

 these values in the middle， will be more accurate。

If the quant distance between adjacent bucket will be closer。So theres a trade off the me and Max。

 you don't want it to be。Ex。Max。And me， Matthew， you don't want it to be very small。

 or then it might be a sweet spot。So if it is a Russian distribution。

 we have closed form solution to find the sweet spot。我土备。That is 4。83B if a3 bit of it's 8。89B。

so the opinions of fashion parameter can be estimated from the collaboration input distribution。

But this is a herra case。Where did the input follow this operation distribution？

So what should we do if we以。当时给当事 follow the那表示。So a very widely used technique is to use the KL divergence micro curve。

To collaborate。The rank。So we want to minimize the loss of information since the interest models encode the same information as the original floating point model。

So we want to find the dynamic range by minimizing。Minimizing the pay divergence。这是个。

Equation for these two distributions， P and Q。One is before quantization， One is after quantization。

And we find the media max value such that it can minimize this k of divergence。

Let's give some intuition。Say this is distribution， this is distribution of the activation item。

This is an absolute value ranges from zero， although a 400， some of them might be even 400。80。

But most of the value。Normalize the number of counts， so lots of value measured below at 40。

And then has this long tail。If we decide to set the max item to be here， what happens？

All the values above all the values in this long tail will be quick。To this大， roughly5。

In way fourth to 50 right all the value above 50 will be clear to 50。

And you can the count will be the sum of all these values count。 So will be a this is the count。

 Okay， so the this is before and after the。啊，范一定的。Max value minimizing the k divergence。

What happens if you have a larger max value？So you will have。Shorter tail on the left hand side。

And the value。Near the quantization near the max value will be more accurate， however。

The range will be larger。 Therefore， these values。These values。

We actually have a lot of them will be less accurate， because the。Dy range is now larger。

 and the quantization error is now larger。It cannot be too small， it can be not to be too large。

The best way to calculate that is by minimizing this k divergence。

And let's see of the modern examples。So Alex that。Presnt1 52， Google Ma， Google Ma。

So this is the clicking。The optimal curriculum range。Discover for these different models。

No of them is。The largest by， theyre not using the largest。这是什么。

But they are using somewhere smaller than the largest values。Cllip。

The largest value to be the quantization max。So this figure further illustrates the intuition。

Between why we need such kind of clipping rather than using the max ladder。

 okay so if we have such a distribution。在这据徐留审。Very long tail。On。

 you could choose the me and the max according to the real。啊面。Its negative 0。8。

As part of the top positive of 0。8， you can choose the max and meaning this way。

This will be your quantization range。And you can see the。

Quronization noise is pretty large because the adjacent quantization sun。

 the distance is pretty far from each other。And in particular， very low density data。

 just a few of them is in this big range。Whereas says we include it？This is a new man。

 this is a new new max。AndThis is a new dynamic range。

And distance between adjacent centroid becomes much。Smaller， right。

 much smaller compared with this one， so the quantization noise becomes much smaller。

And all these vi。Will be click to here。It's still okay， why， because we just have very little。

 very few of them in this range， very few of them in this range。

So it's trying to click down to the desired max we want。

And this is actually a quite helpful technique very widely used。

So on the right hand side is's showing animation。This work is calledocctal from Un media。

 it can also magically find the optimal cliping range。

Our left hand side is showing that the mean error is complexax。

can all be too个 cliping skate can be too small or too large。If you are too small。

 you waste lot of you feel too large， you waste a lot of the dynamic range。If are too small。

 then many values will be clipped to the boundary。So there comex， there's a sweet spot in the meo。

And you can use this technique to find the optimal clicking range。And after applying output。

See the accuracy can be well very well maintained compared with that P32 accuracy。

So finding the graularity very important and then cliping。Okay， any questions so far？Yeah。

The value is the determined if you have four bits， you have 16 values you just one type of。One type。

 Yes， correct。All right， no question， let's take a quick break and come back in five minutes to continue discussion about running。

Welcome back。Let me turn the mic。you hear me。 All right。So let's jump into the third part。

Conunensition about rounding。So this is our conventional wisdom， if you have a vector， 0。3， 0。5， 0。7。

 0。2， we want to round it to like 0，1，1， 0， so the round to nearest。But。

Contradictorory to our conventional wisdom drawn into Ne is actually not optimal。

So wingigs are correlated with each other， the best rounding for each weight to the nearest is not the rounding。

 the best rounding for the whole cancer。So sometimes we want to have some randomness。For example。

 the same pencil sometimes at 0。5。If you run into zero， if you run into1。

 not necessarily running into one might be the opt， sometimes we can even run into zero。

So such stochastic round neural helps during the quantization process。

So instead of running into the nearest， we want to choose running down and running up。あ。

So to get best reconstruction， we can also learn a delta between0 and1。

We added to the original weight and then we run it to the nearest。For example。

 rather than just finding the nearest。Ro you good numerous。You can add a variable。

 this value would be learned。When we pass it through a function。

 H is a function through map B to the range between 0 and 1 between 0 and1。

This is an ocial solution using in such rectrified smo。So the Hv is between0 and1， we added it to W。

 and then we run it to the nearest。So that we can learn a tensor with the same dimension。

So there's vehicle。Another variable of the same shape， same dimension。

Followed by a regularization term。Encouraging the H toV to be binary between either0 or one。

And so this is called I Ron， very popular paper， helping recover the accuracy。

So just intuition is that don't just run to nearest， usually you can apply some stochastic。

To add some randomness during the granting process it really helps。

So let's do a quick summary about linear quantization， what we have learned so far。

We learn about zero points。skating granity per ten， qua range per channel or group quant。

After below four bits， group quant is getting super popular， super important。I'mX4， I'mX6， IP Flor。

 Central。Range quaing， we can use different techniques to find the optimal range to clip it。

And then wrongby。不平台。So by applying that these techniques。For the waves。For the a。

 we can actually very well maintain the accuracy for a bunch of models， like Google N， ResNe。However。

 some of the smaller models like mobile app， they still suffer very heavy accuracy degradation even after applying all the techniques we have learned so far。

Like 10%， 2% degradation of accuracy， which is quite bad。So what should we do， So let's talk about。

Find tu techniques to recover the accuracy for these models。 So let's help on Q A。

 the quant aware training。A very simple technique was already introduced in the last lecture about using KV's quantization where we have a code book。

After we get the gradient， which is of the same size as the weights。

 so this is the weight of the gradient， the dimension are exactly the same。

We sum the gradients corresponding to the same color， the same centroid。

 sum the mo multiplied by the urin rate subtracted from the original centroid to get a fine field in the centuryroid。

So that's very simple for。The K means。N network where we are just updating the sroid。

 its updating the codebook。Actually， it's more。Geting more complicated you to linear content。

So in the linear quant， the weights and activations are all low precision in。In the fourth Y。

In that case， during the training process， we actually maintain a full precision weight in the back。

maintain a full precision， not4 bit， not 8 bit， but 32 bit or 16 or 16 bit。

 a full precision copy of the weight。In the back， throughout all the week。So that we can。

Accumulate very small gradients， very small changes。Accumulate that in a weight lose。

 without loss or precision。And once the model is fully true， this FP32。

 this full precision weight can be thrown away， we only keep the quant of weight。Deployment time。

So this is the layer。Mius1 they。Once one， these are the activations， these are the weight。

 the weights will be quantized， this is the full precision weight。In fact。

 Huang Hai is fitted to calculate the layer N。Com being value and then get the output for the next layer。

So。For the backward process， we update this hook precision weight so that we don't lose any precision。

And remember， during the activation here， we calculate the activation and we should quantize that activation so that the boundary of output。

 the value is quantized。So this whole process is called simulated quantization or fake quantization during the training process。

Because the weight is quant as to QW， but is still using a 32 bit floating point register to represent that value。

Although the value itself is context but we are still using a protein point number to。To for it。

So we take trained the model taking quantization into consideration by adding these。

Two quantization nodes， compute node， one is quantization quantizing the wave。

 the other is quantizing the activation to simulate this quantization process。So we have QW here。

QY here。So forward process is very simple QW F QY， what about the backward process。

 how does the grid flow to the weight？Because the quantization。

 this is basically quantization and activation， if you think about it as an activation function。

So below zero。0。5 is all0 between 0 and5 to 1。5 there 1， between 1。5 and 2。

5 there two so it's actually a sta function。So the quantization makes the input provider to be discrete。

Okay， thepoli he criticized。What's the problem here for the gradient？The gradient is all0。

B becomes zero， then we can learn nothing if you have a zero gradient。

So actually we are using a technique called straight through estimator， STE。

 straight through estimator。We simply pass the gradient through the quantization as if it has never been quantized if it is just an identity function。

So the gradient to the weight is the same as the gradient to the font weight。

You treat the gradienting of the quant wave versus gradienting of the weight to be exactly the same。

政据。Quantization， compute node， this is quant W， this is W。

So treat the gradient between this purple line， this purple line to be exactly the same as if it is just an identity function in this blue quantization node。

What happens。It becomes an identity function。makingking the gradientding calculation much easier。

So this is the full picture， so the purple line is the backward glass。During the backward house。啊。

 before。Upon the vision node， the G is exactly the gradient of the quant as Y。Here。

The GW is exactly the gradient of the quantized W and。

This blue composition node is an identity function。

So we can use its straight through estimation technique。To estimate the gradient for the。

Floating point wait。And floating point activation。By using a quantization， where training。

Here are the quantization of where training results here are without the quantization of where training。

 we can compare the accuracy is drastically improved a lot。

 so potential quantization improved from 0。1% almost  nothing to 70%。

For channel quant originally is better。59% now become 70%。

So this conversation where training really plays quite a helpful role in the accuracy of recovery。

 some of the models like NASA Mobile here， the original accuracy is already pretty good。

So the quant where training gives a marginal improvement。But for large language models。

 which is very costly to trim， the desired scenario will be like this。

 are just using post training quantization without any fine tuning the accuracy should be。

We'll cover that in the Lanch and language model section。In details。Okay。

 so that concludes the linear quantization part。Can we go even farther。Okay。

 so we'll introduce binary and quantsation， just use01， maybe minus-1。

To represent the weight and activations。 And let's see what kind of magic we're having here about binary and turnernary quantization to further push the quantization precision to only one bit。

So let's see an example。 So wait。Mo product with activation。8 times5 minus three。

 so this is the weight， physics activation。We assume the boundary is yx， computation is yx。

 each operation。I plus add and also and multiply and accumulate。

We can quantize the weight to be binary rather than 8 minus-3，5 minus-1， we have1 minus1，1 minus1。

 so we finalized the weight， if it is positive， then it's one， it is negative， there is minus-1。

So we no longer have any modifications， but everything is。Plus or minus。

So the memory 32 times smaller for the weight， previously you a 32 bit。

 now you get only one bit plus one minute。And the computation is roughly complex。

 nice flos because previously you have。Mplication， now we have no modification。 only I。说好都没堵的。

One way is to deterministically by analyzing that if the wave is positive， then it's plus1。

 its negative， then it's negative one。That's basically a sine function， very straightforward。

 but you can imagine this results in a big degradation of accuracy。

Just now we mentioned adding some randomness usually helps with quantization so we can do stochastic byization。

I in this equation here， if it's smaller the minus1 is deterministically to be0。

 if it is above1 is of first。One， but between minus1 and positive one sometimes minus1。

 sometimes it can be quantized to plus1 if it is0， you have half probability to be quantized to0 half of the probability to be quantized to positive。

And can have a linear interpolation between minus one and plus。But it's harder to implement things。

We need a hardware， hardware random number generator in hardware。老师候。So let's see what happens。

2 hour form in matrix is full by matrix we use many times。If we finalize them to one bit。

Just using the sign。Before and after the accuracy degraded by a big market， degraded by 21%。

And the quantization error is 9。28， pretty big quantization error。

And what happens if we do some trick？So we can have a skating factor。

 and we have a flute point skating factor， which is apha。To make sure the sum of all the values。

 the absolute value， the sum of the absolute values of all the elements stays the same。So here。

 the scaling factor will be calculated。The O norm， which is the sum of the absolute value。

Divided by n since every entry。The absolute divide is one， so we have1 elements。

 16 elements in this case。Then we can just calculate the a， actually will be 1。05。

which is equal to the one norm divided by 16 values。And if we multily， it's getting factor over。

The quantization error slightly decreased。And the accuracy delta actually improved a lot。

 actually becomes 0。2%。Positives0。 2%， which is very interesting。So just now。

 we quant only finalize only the weight。 Now we all we want to finalize not only the weight。

 but also the activation。So let's see what happens， you both go weight。Commission is。反。

have1 times1 is1，1 times minus1 minus1， minus1， minus minus1， so this is the choose table。

Let's see another operation which is XO operation， XO operation。で啊。Both values are the same， 1，1，00。

 then output is one。If the two inputs are different， 1001， then the output is0。

 so that's the external operation you might have learned in 6。191。

SoWhat's the relationship between finalized weight and activation versus the export operation？

I they are heavily correlated。So。You can calculate easily sum them up with external results。

Okay so this is one x orbit1， this is0， x orbit with 1，1， x with0，0 xn than 1。

We get1 plus 0 plus 0 plus 0 is one。So now even doing this actually doesn't help。

It's minus2 versus 1， they're not the same。So what's the relationship。

 how do we use external operation to implement？The by the rise of the wave to an activation。

Since I ignore， it's just so simple to implementing hardware。Let's see how do we match that？So。

I assumingum everything is minus1， so let since the smallest negative is minus1。

If you have everything is minus1， if everything with the mo， that's actually minus four。And。But here。

 if we modify the sum of the actual results with two。 so this is the sum of the actual result。

 which is one times2 or we。Times2 can be very efficiently implemented by shift to the left from one bit。

-4 across the。The count times2 plus minus2， that's exactly the value on the left。

So take another look， assume everything is zero， okay we just count' the number of ones。In this case。

Because only if both values are the same， then it otherwise it's0， maybe if it is zero。

 it's corresponding to everything on the left it's minus1。

 so that's why we assume if everything is minus1 and add the difference。

 the difference how we calculate the difference is the number of ones in this case times 2 it' in the difference between minus1 and plus one is 2。

So we have one more added two， you have two， you have two more added four， you three more added six。

So you just count how many variabless are one and then times two。And they can mash。啊明白。

Right outside side。So put it in math。It's equal to minus thin， and is the number of adas。

 in his head is four elementss。was 34 minus n times plus2 times。The sum of the ignore operation。

So minus4， since we have four entries here， we calculate with the x more sum the month。

 sum the month 21 times 2， and added minus4， so that's minus2。

So we can use this very simple x operation to calculate the scenario where both weight and activations are finalized。

And this countant operation has a name， it's called P countant， and return the number once。

In this array， okay the array is binary， either one or zero。

 the pop count operation is basically applying on this binaryry array and count the number of mark。

 just return the number one is called pop count。So using the pop count function。

The final result would be minus n plus pop counts shifted by one。

 so it's shifted by one is basically multiping by two。Okay， using that。

 we can easily calculate the dot product very easily。For example here。

 this is the original floating point unquantized weight and activation。

 this is the quantized weight and activation。We just was have snow operation。And then she is the why。

And then past four， So as the result。So the operation， rather than modification and add。

 now it becomes X and pop count， both are very cheap to implement hardwarer。

 the memory is 32 times smaller seems both the weight and activation becomes one bit。

And the computation is roughly 58 times the less， y is that。

 that's roughly the rhythm that's roughly the complexity between ignore popcorn operation versus Mac operation。

So in that way， we can use or a cheap popr。You no longer need to have modpliers or others。

 you just need to have ignore and pop count operations。And what is accuracy。

 so if we only quantize the weight meaning the activation to be 32 bit。

 you have a little job of accuracy， if you have both weight and activation to be by theized。

 actually a big job of accuracy。But if you use XO net and the XO operation， the accuracy is improved。

 but still a very noticeable degradation of accuracy。

And if you want to see a actually detailed implementation， I actually did one Ra。

 open source R on FPGA， only use these two operations， one is external operation。

 the other is the popcor operation with cityized that we wrote very long since that with open source that can be deployed。

 I stick have PGA very small FGA its open source on our GiHub， feel free to check it off。Okay。

 so since accuracy is too low here， can we do better by using give it one more central。

 give it a zero right， rather than minus1 and plus one， let's have a zero and make it turn。

So totally weight。The weights are quantized to plus 1， minus1 and also zero。

The threshold above the threshold is positive。Between that is zero， you know the threshold is minus。

And how do we calculate delta So there's empirical value。

 youll find the absolute distribution about the absolute value and then multiply by 0。

7 so it's purely empirical。And use that to determine this threshold。

So given this is our familiar weight matrix。We covered the threshold， 16 entries based sum the month。

Times this empirical 0。7， so delta is 0。73 to use that as the boundary。2。09 is above the boundary。

 so it's0 high to plus10 minus 0。98 is below the boundary， so it's0 to。办就说。and so on。 like this 0。

09 is between the minus and positive boundaries slave quant220。Okay。

 we can also find the scaling factor。Can you find the ceiling vector such that the sum of the absolute value。

Remain the same between the left and the right。So here the skin fracture factor is calculated as 1。5。

平成。Conly the number of non zero elements is divided by the number of non zero elements here which。

In that way， we find the accuracy can be improved from 60 to 65。

 but still there's a gap with the proof precision， 69。So how do we further improve that？

So rather than using the heuristic， we can also trim rather than using this fixed。

S factor we can use two trainable parameters。The positive weight analyses with an negative weight to represent the positive and negative scales in a quantization。

So this is original full precision weight。We normalize them to be between minus1 and positive one。

And then we find this threshold to be T， and we quantize them。

And then we seal them by two learnable theory factors， double positive and double negative。

So the final weight becomes minus double negative。F1 positive about the positive。

We can train this WM and WP to improve accuracy。And finally。

 the accuracy in T TQ further improved on top of the two bit T W N。

To further match the original full precision model。

So there's some tricks you can play for tunneling neural networks。So this is the big picture。

We started with floating point weights， floating point arithmetic。

 and then we talk about this K means quantation， now we have inte weights plus of floating point codebook。

 we' still using floating point arithmetic。And then this is probably the most popular。

 linear quantization， we have integer weights and also integer arithmetic。

 we talk about a lot of techniques to find granularity， to find a clipping etctera。And finally。

 if we have this binary and tary quant， we have binary and t waves using bigwise operations。

But here I want to point it out that。Not necessarily the lower the better there should be a sweet spot and roughly four bit is commonly upgrade sweet spot these days it might get lower in the future。

 but there is a tradeoff right so the rhythmic intensity matters a lot for hardware efficiency。

So we have more compute。You might be memory bounded， so if you when you're reducing the precision。

 the memory footprint decreases linearly， but the compute the actual model expressiveness， the flow。

Bitwise operations actually reduces quadraically。So the compute reduces faster than the memory。

The memory reduces four， and the memory is more expensive than the compute。

Therefore the expensive stuff is reducing slower， the cheap stuff is reducing faster。

 so there is in balance， you can diminish return after that。

 so that's something to pay attention when you're reducing the precision。

Usually you don't want to corner one design one design knob to the extreme。

 you want to utilize all the design knbs， for example， pruning quantization， distillation。

Acectctor research， all different techniques together。All right， lastly， just like we talk about。

The sensitivity analysis for pruning where different layers may have different sensitivity。

 some of them may have higher pruning ratio， some of them may have lower pruning ratio。

 that's actually a similar case for quantization so here we have three layers they are all quantized for the weight and activation all quantized the same number of bits。

All eight bits。We can also do mixed precision quantization so for some of the layer。

 which is more sensitive。Like this layer we use more precision， some of them is less sensitive。

 like here and here we use fewer precision。There are a lot of choices right from one bit to eight bit。

 you eight choices， so weight and activation you have 64 choices。

you have n layers that's  stick4 to the N。Number of the design space has so many choices in choices。

You can use different techniques to search in this large search space。Here in this paper called HQ。

 how we're aware， automatic quant with mixed precision。

 we use this actual critique model for our agent to search that。

We map it to the hardwareer and then we get direct feedback。

 including the latency and the energy so that we can feedback the reward to the actual critique model。

And took give of the next generation of action。I think that's overcomplic。

 but that's rule of thumb is that。You want to have different。

 sometimes you want to have different precision for each layer。

 some of them you can keep them in FP 32 or IPP 16 if it doesn't quite hurt for accuracy。

 like some of the very cheap layers。Or some of the。

Memory bonded layers right for some compute bonded layers。

 you definitely want to have a lower precision and make sure they they're less sensitive to the accuracy。

So this is a trade off between the latency versus accuracy。In the design space。

This linear uniform quant versus using the hardware aware quant。

 you can see the hardware aware quant given the same latency。Have have a higher accuracy。

And given the same accuracy has a lower latency。And using that technique。

 we can also optimize for different design targets。

 which we are going to cover in the neural architecture search section。

 okay we want a model to have smaller model science。To be faster， To be energy efficient。

So using such automated approach， hardware awareness without mice not only for the model size。

 but also for the latency。And also for the energy。All right， in summary。

 in this lecture we reviewed linear quantization and then we introduced post training quantization techniques。

 we introduced different granularity of quantization， the pertensor per channel。

 group quantization in particular， AQ4， and also MX4。被告 types。And also。

 we talked about how to determine the dynamic range， the clipping around。

Next we talk about this quantization of wire tuning techniques to use fine tuning to recover the accuracy。

In particular， its a straight through estimator to use STE technique to find human quantized model。

And then we introduce binary internal neural nets， just use one bit or two bit to represent the wave and activation。

 in particular， use pop count and external operation to deal with the binary quantize network。

And finally， we talk about automatic mixed precision of content。All right。

 so that's the end of this lecture in the next lecture we'll talk about neuroact research and lab two is released so we'll come to try it out thank you。


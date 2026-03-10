# 【卡耐基梅隆】概率图形模型 ｜ Probabilistic Graphical Models 2020 p15 P15_Lecture_15_深度生成模型案例研究-文本生成 -BV1ebpGzhEA9_p15-

Today's topic is about a case study of deepgen models。In。

 in the text domain about like tax generation。So this is a little bit。

 a little bit different from the from what are on the syllabus， because。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_1.png)

The unified view of deepj models actually has been covered in the。In this lecture。

 the first part ofgen models。

![](img/41c7ebd7e80a872bb64632dd1a9a13bd_3.png)

So，Today， we'll be like discussing a case study on tax generation。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_5.png)

So first of all， right， what， what is tax generation， So tax generation is a very broad concept。

 a broad set of tasks in natural language processing。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_7.png)

So the goal is to generate a natural language from import data or like。Machine representations。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_9.png)

And it spans a broad set of NLP tasks。I'll keep like I say。

We know like a chatboard or like a dialogueg system， right， the input is like the chatbo the。

 the dialogue history and the output is a response。 Like we once kind of like generates and。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_11.png)

Kind of sure to the to the human。And the machine translation right input is in say English sentence。

 and output is a Chinese sentence。

![](img/41c7ebd7e80a872bb64632dd1a9a13bd_13.png)

And there are other tasks like on text summarization， like giving a document。

 We want to generate a short paragraph that summarize the content in the document。

And like image captioning， like the input is an image or a video， and output is a short。

 short description of the activities in the image。Or like like speech armed recognition， like。

 which transforms the speech signals to like a transcripts。

So there are a lot of like different tasks in this earth。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_15.png)

Text generation problems。Under underlyinging this broad set of tasks。

 there are basically two central goals in。Forest problem。 The first is。generatingrating human。

 like grammatical and readable text。Or like basically， we want generate so called natural language。

 right， The language must be natural and the fluence and just like how human with the write the text。

And the second goal is that we want to generate the text。

That contains the desired information from are in inferd from the inputs。Say in machine translation。

 right， the generated sentence must be with the same meaning with the input sentence。 Like。

 so that's the， the target sentence is the translation of the of the input sentence。

And the data description， like the reports we generated must be like describing the input table。

 say right。And， and for other tasks， like， we want to control the attributes of the sentence。

Even a sentiment label like positive， We want to journey a sentence that is our positive sentiment。

 Like， I like this restaurant。So this output must be containing the desired information that is specified in the input。

And the same， like for conversational flow， like we。

 we want to like control the conversation strategy and the topic， right。

 given the specified in the input。

![](img/41c7ebd7e80a872bb64632dd1a9a13bd_17.png)

![](img/41c7ebd7e80a872bb64632dd1a9a13bd_18.png)

So there are basically two essential goals。let， let's first take a look at how we can achieve the first goal thats generating natural language。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_20.png)

Are the common model for the text generation。The most basic model。

 basically and the is the language model。

![](img/41c7ebd7e80a872bb64632dd1a9a13bd_22.png)

So in language model given a sentence， right on Y， which is which consists of a sequence of tokens。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_24.png)

A language model basically can calculates the probability of a sentence or a piece of text by decomposing the probability of the whole sentence across the time steps or across the tokens。

And each token the has a kind of like conditional distribution， right。

 It distribution is like conditioning on the all previous tokens。

So this is kind of like a a model of this text。And if we want to implement the list。

Sometime usually we can use like， say， a recur network， right。

 as we have seen last in the last lecture。Like， say， we use LTN。

And the model is kind of a sequence of tokens。

![](img/41c7ebd7e80a872bb64632dd1a9a13bd_26.png)

Yeah， this is the language model。And to like kind of like incorporate the input data， Right。

 say in machine translation， this X is a a source sentence， the input sentence。On this。

 this whole language model will be additionally conditioning on this additional context。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_28.png)

So we will have a conditional language model here。And the context is like。Yeah。

 so that context will be like a input into this language model and all the inference。

 like in the decoding process will be conditioning on this context。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_30.png)

![](img/41c7ebd7e80a872bb64632dd1a9a13bd_31.png)

Okay， so how do we train this our model， right？ the training algorithm。

 there are a lot of like training algorithms we can。

 we can use those kind of like the most kind of popular or like simplestistic methods is the maximum likelihood estimation is pretty straightforward。

So on。To train the model， right， we are given a set of data examples。

 and we just maximize the data log likelihood。

![](img/41c7ebd7e80a872bb64632dd1a9a13bd_33.png)

Lets given the choose state Y star。It we just like evaluate the maximize the log likelihood of the data。

 right。Yeah， and yeah， this is the training。 And then for evaluation。

 the evaluation a little bit different。 Like， we have different metrics specific to each of the tasks。

Like， say， in machine translation， we have the magic called like blue， right。

 So we can compute the blue score between the。Generation by the model。

 anglengular quantum choose data。 So this blue score basically evaluates the similarity of the output anglengular quantum truth。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_35.png)

And for summarization， we have a another difference like a magic。

 And there are other like metrics for different tasks。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_37.png)

So you can see there there's basically two issues of maximum likelihood estimation for tax generation。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_39.png)

The first issue is so called exposure biasers。So we can see like， at training time。Right。

 we maximize the data log likelihood。 So， and for each token， right， we predict the next token。

 given the previous grand truth tokens。 So this is the in the chain phase。Like we， we。

 we are given list one choose token tokens， and we input list。头根来个。Why1 star， right？

 And we predict the next token Y 2 heads。But in at evaluation。

 we don't have these ground truth tokens， right， So at at the evaluation time， we predict next token。

 given the previous。

![](img/41c7ebd7e80a872bb64632dd1a9a13bd_41.png)

Sequence that are generated by the model itself。

![](img/41c7ebd7e80a872bb64632dd1a9a13bd_43.png)

So you can see there is a discrepancy between training and evaluation。At the training time。

 the model will see the graous。For the previous tokens， but at evaluation time。

 we can only use the sequence generated by the model。So that means like in another world。

 at the training time。The model is not exposed to the sequences it， it will produce。

 And sometimes this previous sequence like produced by by the model will contain some mistakes or like errors。

Right， so like I say， if this Y one head is， is， is a mistake。 like is a kind of a wrong token， this。

 this particular token will affect the subsequent inferences and。Basically。

 these follow up tokens will also be like a mistakes。So this is what we call the exposure bias。On。

And the second issue is that we can see like at the training time， we。

 the metric is the data log likelihood， right， we， we maximize the likelihood。But at evaluation time。

 we use a different metric to to measure the performance of the model。

 like a blue scroll at on for machine translation。So you can see there is another discrepancy between training and the evaluation。

 right， we have， we， we kind of like use given the metrics。For training and evaluation。Yeah。

 so there are a lot of like follow up training algorithms that try that are trying to like fix these two fundamental issues。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_45.png)

Say a a possible solution is the reinforcement learning， which I think。

The the follow up lectures will cover some of the aspects of reinforcement learning。So， here。

Basically， the investment learning is to like maximize the expected reward under the model distribution。

So here are this is say， this is your language model。 Like you want to learn this model。

 and you have some like a reward function or like a evaluation metrics。

And the objective is like this。 We want to maximize the expected。Reward under this under your model。

 basically。So。Yeah， so basically， like say we can plug in plug like whatever evaluation magic you want to use。

 like like im translation we here， we can use the blue score as the reward。

 And so let basically fix the issue of like the discrepancy between like training magic and the evaluation magic。

 right， Because like here at training time， we are maximizing the blue score。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_47.png)

But， of course， like reverse learning is not the， the， the perfect solution。

 It it has its own issues。Like you can see， like generate basically here。

 we will ask first use the model to generate the whole sentence， right。

 and you evaluate the quality of the sentence using the evaluation magic。But we can see like least。

 there is here。 So you can be extremely large sequence space。 Like， if。

 say if the vocabulary size is like 50000。 and we want to generate sentence of containing like 50 tokens。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_49.png)

Then this space will be very， very large。And that means like the， the search space， right。

 will be too large and the chain will be very in ineffient。Because like most of the time。

 this model will generate to something that is not simply not meaningful。

 And this this scroll would be very kind of， very low。

 And you cannot really like change this model in an effective way。And also， the same reason， right。

 there will be a high variance and poor exploration efficiency during training because of this very large sequence space。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_51.png)

So there are a lot of works like kind of like trying to fix this。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_53.png)

I kind of like training training issues to make this training more practical。

One of algorithms is like a reward augmented maximum likelihoods。So basically。

 the the high level idea is like we can add the reward or where perturbation to the ME data examples like we given a。

 given a training a set of training data in M E， we can like add some noise to the training data。

 So that at the training time， the model we also see some of the kind of like mistakes in the training data instead of the kind of like perfect。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_55.png)

Pviect is a stay there。And the list noise will be like informed by the particular rewards。

 This rewards， like， say emerging translation again， this reward is the blue score， right。

 So we can like somehow like close the gap between the evaluation metrics between like at changing time and evaluation time。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_57.png)

And another algorithm is like a soft， soft， Yeah， soft max policy ras。

 it's kind of like a extension of these standard policy ras。

By using the reward distribution for effective sampling and estimating the policy gradient。

I want to go into more details of these algorithm。 But here we just need to know like there are different algorithm here to like fix the issues in maximum likelihood estimation and and emotional learning。

And the the the other algorithm， like data noiseing， again。

 similar to this remote algorithm is to like add random noise to the data so that the model will be exposed to like noises and mistakes at training time。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_59.png)

Okay， so there are different algorithms。 And actually。

 we can show that these algorithms are kind of like。Closely connected with each other。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_61.png)

Basically， we can ensure that there is a unifying formulation of these diverse linear algorithms。

InIn particular， we， we have seen this right MO E， like So Max policy gradient。

 Remo and data noiseising。

![](img/41c7ebd7e80a872bb64632dd1a9a13bd_63.png)

And we can ensure that there are kind of like a like， basically。

 there is a kind of unifying formulation。 And this formulation is governed by three hyperparmeter。

Say， R is the reward function。And Arva and Bta are too like。Balancing weights to like scales。And by。

Setting these hypo premises to different the failures we can recover these different algorithms。

Essentially， like， say，Remo and ME， right， The only difference is that they are using different reward functions。

We'll see more details later。And yeah， all these evidence are special instances of a generalized and P regularized policy of optimization framework。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_65.png)

And the only difference is the choice of the reward R， and the values of some hyperparmeter are in。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_67.png)

Basically， this unified view inspires new and improved algorithms。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_69.png)

Let see more details here。So this is generalized so called ERRPO framework。

So we consider a sequence generation model， like PC S Y， given X is a conditional language model。

And giving whatever reward function， right。Why is the generation by the model。

 And the white star is the ground truth， like the blue score， right in machine translation。

And we assume a version distribution。Q on Y given x， which is the approximation to this to， to。

 to your， to the model of interest。And the objective of this framework。Is written on in this way。So。

 basically， we are。Maximizing the rewards， right under， under the。Val distribution， so。And theres。

 there's a clear divergence between the version dis distribution and the and the model of interest。

And then theres the additional， like entropy regularizer on the。On the fraction distribution。

So we can see this objective is pretty close to what you have seen in in versional inference or versional E M。

 right？ is essentially least two terms， like the expectation and then the K divergence。

If we see like a P is the prior distribution and the Q is the。Kind of like a。

 the professional distribution。Yeah， and the the only thing is like here。

 we have additional entropy regularizerizer。 and there are two like hyper parametersmeter of the base to like kind of control the moderation of the two like entroies。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_71.png)

Yeah， so this is if， if you know this like reverse learning。

 youll see like this is objective with a generalization of like many popular I algorithms。

 like relative entropy policy gradient， policy search and like trust region policy optimization。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_73.png)

![](img/41c7ebd7e80a872bb64632dd1a9a13bd_74.png)

Yeah， I wont go on into this details。 but yeah， this is the。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_76.png)

Generalized objective。And let's see， like how this objective can really like recover the specialized everything we have seen like M L E and Rammo。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_78.png)

Yeah， so yeah， first of all， I like a little bit more about this remote。 given this objective。

 right we solve this objective with a kind of like an E M style procedure。Like at step， at it。

 at each iteration， right， each step is like this。 which first， with soft list are。This。

 this problem， right， with regard to the version distribution。

And there is a close form solution for this version distribution。

 which you can see is a combination of the。The model， right， and the reward function。

And our beta basically are kind of like balancing the， the weight of the two components。Yeah。

 and the M step。Given this Q distribution， we maximize the。

Kind of like the log likelihood of the model that with regard cut to the the samples like generated from the the Q distribution。

So you can see Lisa is very close to the version E M， right。

The step has basically produced a closed form solution for the version distribution。

 And then M step is like a。Optimizing with regard to the model parameters。Okay， so so here。

 here is some like intuitive interpretation of this。Objective and optimization。Like。

 say the rule of alpha， right？ Let's see like if alpha tend to infinite。

 then we can see that from this， this part， we will see。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_80.png)

Q will equal。Will equal to this model， right。

![](img/41c7ebd7e80a872bb64632dd1a9a13bd_82.png)

So from this solution。 And also this， this can also be seen here， right， whatever equals。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_84.png)

Infin， then。你别。But like to， to minimize these scale diveence， right Q will equal equal to the model。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_86.png)

And for beta， right， if beta tends to in， then we can see。

This cube basically is a uniform distribution， Right， Because like here。

 beta is very if beta is very large。L corresponds to list term， right， If base on is very large。

 then we will maximize this entropy。Let means Q must be a uniform distribution。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_88.png)

And here， M step is basically maximizing the log likelihood of samples from， from the Q distribution。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_90.png)

Yeah， so with list are objective and optimizationim procedure。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_92.png)

Let's see嗯。MLE is actually a special case of this framework。So in M LE。

 we are basically using this type of reward function。Here， I set to this particular。

比re that function。If the data， if the， if the sample Y equals the equal to this Q choose data。

Then the reward is one， otherwise， the reward is negative infinite。

And Rva and beta are are set to these particular values。 Rva is kind of like very。

 a very small positive value， like very close to 0，0。 and the beta is set 1。

And we can see like basically， if we plug this configuration into this each step， right。

We can show that basically， the Q distribution will be like this。 if x， if y equals equals the gras。

 then you get one， and otherwise is 0。 So this is in。

 this is essentially empirical data distribution， right。And then like， as we said。

 the M step is basically maximizing the log likelihoods of samples from the Q distribution。

 And now we show like Q is the data distribution。 that means M step is basically maximizing the data log likelihood。

So will you cover this MLE algorithm。Like by setting R and alpha beta to these particular values。

Yeah， so Li is IMLE。And。Yeah， so if we kind of like visualize this the training procedure。

 we can see basically assume this is the whole exploration space， right， the。

 the whole space of the sequence。And we are， we are given a set of data examples。

 right in this whole sequence in the in this whole space。

And M LE is can be seen as a policy optimization， right with the deta function as reward。

 theelta function as the reward。So that means like the exploration can only is the exploration of the model at the training time is restricted on this set of。

Points in the whole space。And any exploration beyond the training data。

 beyond the particular beyond the set of points。Will kind of like get negative in rewards。

 So this exploration will be get kind of like a made void。RightAnd this。

 this basically explained the exposure bias， right。

 The model at the training time is only exposed to this a small set of samples here。And the whole。

 the model is not exposed to the whole sequence space at the training time。

But the cool thing is that given this geota function。

 because Q will basically reduce the reduce to the empirical data distribution。

 So sampling from here is pretty straightforward。 That makes the in computation of this model very very efficient。

😊，And also， all these data symbols are of high quality， because these are going to choose data。

You will always get for high quality samples from， from the Q distribution。

 So this chain of the model will be very efficient。Yeah， so this is the MLE。

 like an intuitive explanation of the。Advantage and disadvantage of the particular algorithm from the perspective of the more general framework。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_94.png)

So under the other algorithm， the remote like reward augmented on maximum likelihood likelihood estimation。

The only difference。On between M， L E and Rammo is that。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_96.png)

Now， we replace this data reward function。With a kind of like a common reward。

 such as the blue scroll。

![](img/41c7ebd7e80a872bb64632dd1a9a13bd_98.png)

Right， so the effective， the， the effect is like this are now with these particular words。

 the E step， right， we get this Q distribution。It's kind of an exp reward distribution。

And at the M step， we are like a maximizing reward augmented， maximum like likelihoodli。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_100.png)

Log likelihood。So you can see on the difference here， right。

 We are not no longer using the deta function as a reward。But instead using a。

 A like a tasks of speaker rewards。But at at the each step。 So this basically fix the issue in M L E。

 like the discrepancy between like training time and the evaluation time in terms of the evaluation matrix。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_102.png)

![](img/41c7ebd7e80a872bb64632dd1a9a13bd_103.png)

And yeah， basically， list words has list。This shape， like I say， we have given the grand truth data。

 right， this reward will give， will give kind of a score like kind of like in this shape。

 like we'll get the kind of highest the score if y equals y star。

But even if white does not like really fully matchly。Wantna choose。

 you will still get some like a kind of like a score， right， instead of like in in as in in M O E。

 right， we are， if we are using a digital reward， then only this point will get a score one and all other point will get an negative infinity reward。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_105.png)

Yeah， so if we visualize this on optimization。Compared to M L E， right。 now。

 Remo uses a task dependence reward。 And this， basically。

 this reward is more smooth than the theta function。

And this effectively permits a larger exploration space surrounding the training data， right。

 Because here， right， we can we have scores like surrounding this ground data。

 So in the sequence space， we basically allow the model to like explore the whole space。

 like kind of like close to the training data points。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_107.png)

![](img/41c7ebd7e80a872bb64632dd1a9a13bd_108.png)

![](img/41c7ebd7e80a872bb64632dd1a9a13bd_109.png)

And here， like because alpha equals1。Iy is very small。

 Let's basically ignore the model distribution of exploration， because like here， this。

 list terms are ignored because I is very small。 So all the sampling。

 all the samples from here will be determined by the reward function。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_111.png)

![](img/41c7ebd7e80a872bb64632dd1a9a13bd_112.png)

Yeah， this is the the ramo on。

![](img/41c7ebd7e80a872bb64632dd1a9a13bd_114.png)

As a special case of the general framework。So the the next algorithm， the soft max policy gradients。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_116.png)

Again on compared to Rammo， you can see the only difference。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_118.png)

Here is like in Re， we have R and bases like this。And then in soft max policy gradients。

 we kind of like change alpha beta values to like alpha equals 1 and beta equals 0。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_120.png)

![](img/41c7ebd7e80a872bb64632dd1a9a13bd_121.png)

So what does this mean like on。At each step， now we have this solution for Q distribution。

Like a is a， is' a kind of like a multiplication of the model and the reward。And again。

 at the M for M step is still like a maximizing the。

Likelihoods of the samples from from acute distribution。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_123.png)

And here。If we visualize this。We can see like a soft max policy gradient use both the model distribution and the reward for exploration。

So this basically permits the largest exploration space。 right you basically， the model can generate。

Whatever sequence， whatever sequence， right from in， in the whole like sequence space。嗯。Yeah。

 so but the， the difficulty here is that， as we said， like in in reinforcement learning， Right。

 at especially at the early stage of training。This model is still like not well trained， right。

 And so that it can easily create samples that are of low quality。

So that means like in sometimes this， the samples from this Q distribution will be of local quality and the training of the model will be not that efficient。

So this is the kind of， you can see a clear trade of here， right on。Let let let me see。 like Yeah。

 So like from M O E to level to soft max policy gradient。

 we are kind of increase in increasingly expanding exploration space。It's at the training time。

But you can see， like on。Another way of seeing this expansion is that we are kind of like allowing more and more noise at changing time。

 right， from the from the samples in in among the samples from the Q distribution。

 So given this noisy samples this， this optimization for the model distribution。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_125.png)

![](img/41c7ebd7e80a872bb64632dd1a9a13bd_126.png)

![](img/41c7ebd7e80a872bb64632dd1a9a13bd_127.png)

Its kind of like getting like harder and harder， and。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_129.png)

And for this case， if you even need more like training tricks to allow the practical training。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_131.png)

Yeah， and the the last algorithm， data noiseing right again， is a special case and。Here。

 the same is less。 we， we still have these R and beta values， but we are using a locally。

 just using a locally relaxed variant of the data data rewards in M O E。Here。

 we don't really once on。Like it restricts that on the。

 the sample must be kind of like exactly matching the， the quantum tools。But instead。

 we can allow some like a discrepancy between the sample and the the the ground truth。 like， say。

 we can allow is。A difference。On a particular token， a single token， right between the two sequences。

So this basically like allow this this noise is kind of like we randomly select token in the sequence in the Grand sequence and like replace that token with another uniformly picked to token。

So this is one kind of noise we can add to the training data。

Which is like kind of like described it in this reward function。

And there are many ways of injecting the data， in injecting noise to the in in the training data。

 So you can like just use different the type of conditions here So to like recover given the data noiseing strategies。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_133.png)

![](img/41c7ebd7e80a872bb64632dd1a9a13bd_134.png)

Yeah， and this is pretty close to the Rammo， right， because we can we add noise to the training data。

 which essentially allow the model to like explore beyond the， the set of samples。

 kind of like the space is the space like surrounding the training data。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_136.png)

And the difference between data noiseing and the Remo is that Remo will add reward aware noise。

 Right， Because here in Re， we are using a like a blue score as the as a reward， which in effect。

 is like injecting the noise informed by the reward function。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_138.png)

And the data noise is like adding the noise kind of like in a more random way。

 that we kind of like randomly swap a token in in the gra sequence。So this on the growth。

 the advantage here， like the noise is easy to implement because like this swapping a token is pretty straightforward。

But the Ram， like， if we want to incorporate the tasks of rewards to inject the noise is usually in practice is much harder to implement。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_140.png)

Okay， so for a quick summary， like for this set of given the algorithms for sequence generation。

For training the sequence model。Right， we， we see like every everything corresponds to a points in the。

 in a hyperparmeter space。And from left to right， we are in increasingly like gradually like increasing the explosion space at changing time。

And in theory， because like at the training time， the model kind of like is exposed to the larger space。

 right， the larger sequence space。 So in theory， this the model should be like perform。

 performing better and better， right。But the， the practical issue here is like the training will be。

 will also be like more and more difficult。So you can see Pis， there's a tradeoff。

And a natural idea here is that。We can like interpret among the algorithms， right， because on the。

 the at the leftmost points， right M O E is very easy to train， right。

But the approach space is very small， and the。On the right， this is very hard。

 very difficult for training， but the exploration is like but we allow a larger like exploration space。

 So a natural idea is like， can we like inter between from left to right， right。

 we kind of like train this train the model。 at on at the early stage。

 we change the model with M L E。And kind of like a great。 then at a later space。 at a later stage。

 we replace this Gi reward function with the the task specific rewards。

 right to allow like a larger exploration space。

![](img/41c7ebd7e80a872bb64632dd1a9a13bd_142.png)

And then we also like a new alpha and a bit from like a least configuration to list configuration。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_144.png)

So， in fact， we allow the model to gradually increase the exposure space at training time and increasingly increase。

 kind of like increase the difficulty of the training。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_146.png)

Right， so like this is kind of like by aning these hyperpargmeters。

 we can like interlate between these algorithms。

![](img/41c7ebd7e80a872bb64632dd1a9a13bd_148.png)

Yes， so with this interpretation with this high level idea。 Here are some like results。

ImSo in machine translation， right with this on a new link。Or like interlation。

 we get like a better like blue score for machine translation。 And also like for text summarization。

 we see like a improvement。And this is the， basically the， the the training curve， like。

I know like as we train this model， like the blue score kind of gradually like increase。

 And if we compare with the ME and Rammo， basically。Yes。We kind of like like。

 as we like a Chinese model， like with like an increasingly larger explosion space on the model will get like a better performance。

Yeah， but， this is kind of like a pretty quick。Introduction of this interpretationlation everything。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_150.png)

Okay， so this is the first part。How we can， like， generate。Our natural language。

 like we basically visit two like common fundamental issues for sequence generation。

 The first is the exposure biasers， and the second is the criteria mismatch。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_152.png)

And there are， many algorithms are proposed to like fix these two issues like ME， Remo。

 So max policy gradient， data noiseing and the standard poly gradient。

And all these algorithms can be like subsumed in a unified framework for the sequence generation。

Like which in this under this framework， list evidence corresponds to like particular configurations of a couple of hypocrs like reward function and R and the ba。

 the two balancing weight。Yeah， so yeah this is the first part。Yeah。

 the second part is like how we can like。Ensure that our model will generate the text that contains the desired information in from the input。

So we see that for list different tasks， like machine translation and data description and other tasks。

We have， we basically have different amount of training training data superfuion data。Like。

 as we know， like emerging translation， we have kind of like a very large amount of data。

 like tens of millions of chain examples。 So you can like directly use the supervis learning to change the model。

And the data description on again， we， we， we have a certain amount of data。

 like tens of thousands of data examples。 is's kind of like。Its。

 it still feasible to like directly use like supervised learning to change your model。

And the same like for sentiment sentiment control。But for other settings， like say。

 we want to many mod a sentence， like from sentiment positive to negative。Well still like a。

 like a preserving other aspect， like a content of the sentence。Basically， we。

 we don't have any like super data。And for a more complex settings。

 like we want to learn to control the conversation strategy and the topic。 again。

 we don't have any supervisicion data。So， in these particular cases。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_154.png)

We need some methods to like learn this control generation or conditional generation in an unsupervised setting。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_156.png)

Yeah， so this part will particularly focus on this unsupervised setting。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_158.png)

Yeah， so here are some like a particular examples in in this setting。

 like text H transfer or like a text content manipulation。And for conversation。

 we have like a target guided open domain conversation。 Yeah， let。

 let's take a look at these different settings。First， on text attribute transfer。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_160.png)

So the task is like this given a sentence。We want to modify this sentence to have a desired attribute value while keeping all other aspects unchanged。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_162.png)

![](img/41c7ebd7e80a872bb64632dd1a9a13bd_163.png)

Say we want to we want to say we want to transfer like attributes like sentiment， tanks。

 voice and gender and other different attributes of text。Like， say， on to transfer sentiment， right。

 from negative to positive。But this is the input sentence。

 like it was super dry and had a weird taste。We want to modify this sentence to a kind of like。

 to have a positive sentiment， right， It was super fresh and a delicious， kind of like taste。😊。

And the logo here is like we， we want like a changeless sentiments， but still like。

 keep all other aspects unchanged， like armed。

![](img/41c7ebd7e80a872bb64632dd1a9a13bd_165.png)

The， the， the content， right， the entire slice and the taste and like the super or。

 all these different aspects are keep unchanged。So the application of this time， this kind of task。

Can be like personalized ethical writing， right， I know like a personalized conversation systems and other different applications。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_167.png)

Right， so for a formal formulation， like giving a input X and the original attributes， A X。

 for which we want to control。And。The task is basically that we were given this X and the target attributes。

 A Y。 we want to generate a target sentence Y。Why has the desired attributes。

And what keeps all attribute independent properties of x。So the training settings like this。

 we only have players like X and A X。But we don't have this direct superficion data， like A X， A。

 A X and Y， A Y。 We don't have this parallel data。嗯。Yeah。

 so the next is like how we can use this be right available to train this particular conditional generation model。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_169.png)

So here's， here's a possible solution。 Like， we have this model， like given。

 given this X and A Y as a kind of。X and A Y are two inputs。 And the goal is to generate y。

And basically， we have list。This encoder， right， we first like encode the input sentence as a。

 as a hidden hidden vector Z， like the feature vector。

 and we concatenate this feature vector with the the the attribute value like like for positive sentiments。

 This these A Y equals one like for negative sentiments， equals 0。

And conditioning only two like looking canation of the two features。

 We use a decoder to generate the wine， right， conditioning only two。Yeah。

 and the the key intuition for。Are training this model。

We decompose the task into competitive subject objects。

And use direct supervisions for each of the sub objects。Like， say the first objective right on。

 we want Y， we want y to keep all attributes independent the properties of x。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_171.png)

So that means like Y must be like very close to the input X， right， You。

 you can only change some of the tokens in the whole sequence。

So a very straightforward and very simple objective way to like enforce the similarity between X and Y is that we just use all the encoding laws。

 right， we once。

![](img/41c7ebd7e80a872bb64632dd1a9a13bd_173.png)

Basically， we want Y to be exactly to be exactly the same with x。

 So this is a very simplified and straightforward way to like， encourage this。那个呃。

The property preservation， basically。

![](img/41c7ebd7e80a872bb64632dd1a9a13bd_175.png)

And the second objective， like， we want why has the we want y to have less desired attribute Y A Y。

 right say we want， if this A Y is like positive sentiment。

 then we want why to have to really have the sentiment positive sentiment。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_177.png)

So how can we encourage this？We use the classification loss given the way sample right from。

 from the model。We feed this sample to a sentiment classifier， a pre sentiment classifier。

And we once list the， the prediction of the sentiments。To be the same with the input sentiments。

 right， so you can see there's， there can be a loop on like given re the y。

 and we feed this y into a sentiment class fire and this sentiment class fire。

We want less sending cacheifier to like recover list input sentiments。Yeah。

 so we can see there are basically two loss functions。

 and we will optimize these two loss functions jointly。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_179.png)

So， look first。Intuitively right at least these two lots functions we have like we drive kind of a drive for the model towards two two directions。

 Like， this is the why we completely recover this input sentence X。

And the the classification laws basically will encourage the Y to really like implement these desired attributes。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_181.png)

And if we optimizeize these two losses jointly， well kind of like drive the model towards the direction we expected。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_183.png)

So， and because like basically， these two laws are competitive and minimizing this joint。

 The two loss is jointly will avoid the model to like collapse。In terms of this competitive laws。

 right here。Right， basically。啊 you。We can see like this classification laws will prevent the model to to generate exactly the same x。

 right， because like X does not really fit this， this criteria， right。

 So I'm also like here for classification laws， the auto including laws will。in a sense。

 like be competitive with this cl classification laws， because like， say， given whatever sentence。

 right， if we only have this classification laws， then like given a positive sentiments， this。

 this decoder can generate whatever sentence， right， that is of positive sentiments。

 regardless of the input sentence。So you can see these。

 these two loss functions are basically competitive with each other。

 but they can be optimized jointly to like have like a joint objective to like push the model to whether towards what we we desire。

 basically。

![](img/41c7ebd7e80a872bb64632dd1a9a13bd_185.png)

![](img/41c7ebd7e80a872bb64632dd1a9a13bd_186.png)

So， on the performance on。一二数。If we jointly optimizeize these two loss functions。

 we can basically get a like sentiment accuracy towards like above like 80 90%。😊。

And the blue score against the in percentage around the 55 is kind of like a pretty decent result。

Basically， the blue score evaluates the similarity between the output and the inputs。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_188.png)

Right， and here are some like examples， right， given the inputs。

And say we want to change this to a positive sentiment。 right on here are the inputs like on。

I could give them a zero star。 and the outputboard is like give them a sweetar star view。

So you're gonna to see like a。This， this model basically learns to like correctly， like a。

To like change the sentiment from negative to positive， right。

And you can see this output is pretty close to the， to the input。 right。

 we kind of like preserve all other tokens that is， that are independent with the sentiment。

But theres a particular problem here Like the language more。

 the language quality is not not very good， right， because a sweet heart start view is not a correct language。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_190.png)

![](img/41c7ebd7e80a872bb64632dd1a9a13bd_191.png)

And this is also reflected in the。Pplexity， if we use use a language model to evaluate the perplexity of outputs。

 we get a very high perplexity， which means the language quality is not very good。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_193.png)

So we， we can certainly like， we can improve this model。 like by using another type of objective。

 another type of loss function。 We use a language model as the direct supervision。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_195.png)

On the solar additional loss functions like given the with sample we。

 we get the output right from the model。And the objectives， like。

 we want to maximize the likelihoods of this sample under a language model。 So basically。

 we want like change the generation model so that the samples will have will have like low language language model complexity。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_197.png)

And the which list additional loss function， right。

 which basically like a train three loss functions jointly。And then we。

 we kind of like get like high accuracy and kind of like preservable input centers pretty well and get a low like language language model complexityplexity。

 And here's the。

![](img/41c7ebd7e80a872bb64632dd1a9a13bd_199.png)

![](img/41c7ebd7e80a872bb64632dd1a9a13bd_200.png)

![](img/41c7ebd7e80a872bb64632dd1a9a13bd_201.png)

Some of the samples， but if I can give them a great star review， I would。 right。 So basically。

 this language model corrects this， this sentence into this。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_203.png)

![](img/41c7ebd7e80a872bb64632dd1a9a13bd_204.png)

Re sentenced light。

![](img/41c7ebd7e80a872bb64632dd1a9a13bd_206.png)

Okay， so this is the the first example on app task， like the key ideas。

 like we decompose the task into competitive competitive sub objectives。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_208.png)

And the useless direct superfion for each algorithm on sub objectivess， like a force。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_210.png)

To like preservable sentiment， to like a change the sentiment that we use a sentiment classifier as the dialogueg coefficient。

 like to like a preservly input contents。Or other aspects。

 we just use the order encoding laws to like to， to like provide supervision and to in improve the language quality with the language model to provide supervision。

Yeah， so this is the first application setting。 and the second setting thats pretty close to the first one。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_212.png)

Is that we can generate the centers to describe contents in a given data records。And again， here。

 we want to control the， like， the， the writing style of the sentence。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_214.png)

giving by giving a reference sentence。Like here， like， this is a content records， a table。 Basically。

 we want to generate a sentence。That describe this content。And， but there are a lot of ways to like。

 describe the content， right， We can have different writing styles。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_216.png)

To control this writing， the writing style， be we then like provide an additional sentence。

 a reference sentence， right， which is， which was written like by human and。

 and to describe a different content。

![](img/41c7ebd7e80a872bb64632dd1a9a13bd_218.png)

So the task is like， how can we rewrite this relevant sentence to describe the new content。

Right so the， the desired output here is like the brown James that way with that we with the exactly the same wording。

And。32 points， right from this content and 7 assist and other are。and other content， other content。

Yeah， so basically， the goal is like we want to control the writing style using the writing style of the reference centers。

The， the method is pretty similar to the， the method in the first task。 because again。

 like we wantna basically we want to preserve the the the early aspects of the relevant sentence。

 We are only changing the content， right？ So again。

 we can kind of decompose this task into different sub task。

 sub sub objectives and use direct sufficient to encourage to ensure the model can accomplish the each of the sub sub objectives。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_220.png)

![](img/41c7ebd7e80a872bb64632dd1a9a13bd_221.png)

Yeah， I won to go into more details。 but here are some like results。

 like with this input with this reference sentence。

 we our model our approach basically produce this results as， as expected。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_223.png)

![](img/41c7ebd7e80a872bb64632dd1a9a13bd_224.png)

And there are different ways of like， as a baseline， like a low based methods and like other。

 like other particular methods。

![](img/41c7ebd7e80a872bb64632dd1a9a13bd_226.png)

Okay， so here's some like quantitative evaluation。 I was skip。 I was skiless。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_228.png)

Okay， so this is the first part， like sentence level control。 Like， how can we like。

 change the attribute of a sentence like sentiment or like。

 how can we rewrite the content of a sentence to express kind of a new set of content。

The next part on。At the conversation level， right， how can we like control the the conversation。

 or especially say the。The conversation strategy or the topic in。

 in a open domain conversation system。So a very quick overview of the of conversation system research。

 there are basically two set of。Converation systems。 the first is the task oriented dialogue。

So in this type of conversation system， we use this dialogue system to like adjust a specific task。

 like booking of flight like like a reserving a a restaurant。

So this type of dialo is usually close domain。 Right we have a chatbot for a particular like airline company。

 right， Like this， this chatbot will help you to like book a flight。 But this。

 this chatbot cannot do any， anything else。So this is a close domain conversation。

And we have like a chat chat for open domain conversation。

 The goal is to like improve the user engagement。 The metric is like， how long this。

 this chatboardt can like keep。Conversing with， with a， with a human。

And this conversation is usually just a random conversation。

 And without any like control on the topic or whatever aspect。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_230.png)

So。The， the third， the third kind of like a type of composition， which is a new research direction。

Is how we can basically combine this to。Tybal compositions。First。

 is still open domain make conversation。 You basically can converse with human or about whatever topic。

But at the same time， we want to control the conversation strategy to reach a desired topic at the end of the conversation。

Like， so so we basically， we want the chatbot， like studying from whatever topic， right。

 we want the chatbot to pour and sometimes implicitly guide the conversation flow to a particular target topic。

So say， this， this type of application， this type of conversation system can be used in like a conversational recommend system。

 like or like in education or in like psychotherapy。 So imagine like in psychotherapy， right。

 a doctor will chat kind of like a chat with the the patient， right。

 kind of and the this conversation is very relaxed。 is is the open domain conversation。😊，But the。

 the doctor has some like implicit goal。 I think it he wants to let basically guide the topic towards a particular。

 particular。Topic， right， so that's it will like inspire the patient to like speak up。

 to speak up like whatever this patient is thinking。And the relevant tool are。There are whatever。

 like a disease or other issues。

![](img/41c7ebd7e80a872bb64632dd1a9a13bd_232.png)

Yeah， so。Basically， again， we can like decompose the task into two sub objectives。The first。

 the first objective is like studying from any topic。

 We wanted the conversation system to reach a desired topic at the end of conversation。

This is the so called target的概念。And at the same time， we want this conversation to be natural。

 right we want this topic transition to be first smooth。

 so that the conversation is like very is kind of engaging with the， with， with the human。So。

 so this is， this is one example， right， studying from whatever topic like this general greeting。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_234.png)

The desired topic is like， say ebooks， say in a in a recommended system。

 we want to recommend the the， the customers to like。Basically， to buy ebook， right。

So on this is the conversation between the agent and human。And we can see like in this conversation。

 right， on the topic of the conversation， basically。Is like。

Basically transit like gradually from whatever like a tired sorry work work work program。

 coding book and then ebooks， right。

![](img/41c7ebd7e80a872bb64632dd1a9a13bd_236.png)

And we can also see this， this conversation is pretty natural。

 like on this topic transition is pretty smooth。So this is the goal we want to achieve in this particular task。

SoAnd the， the challenge here is again， like we don't have direct super data。So on the solution。

 like with these competitive sub on sub objectives。And these partial supervisions， right， first。

 to enable this natural conversation。We can use reach chip chat data to learn smooth single turn transition。

 because in we have a lot of data for like on this chi chat conversation。And this。

 this should track conversation basically provide the information about what do we mean by like smooth transition like。

So here， like I say， from whatever。Sents from whatever like sentences。

 like or like a composition history， how we can generate a smooth response to this history。

We can learn use this natural convert this tree data。And the second goal。

 let to reach a desired targets。 we could use like low based monitoring planning。 Like。

 we want the keywords of each of the。

![](img/41c7ebd7e80a872bb64632dd1a9a13bd_238.png)

![](img/41c7ebd7e80a872bb64632dd1a9a13bd_239.png)

Responses to like a。Kind of like getting to like a get closer to this to the， to the， to the。

 the target conversation， to the target topic at each step。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_241.png)

So okay， so a。High level illustration of the model the modern architecture。

Given an utter like by a human right， I'm writing a chat about his program。

We first extract the keywords。From the arts。Which is the program。

We can see these keyword as a topic of this particular utterance。Right。

 so this is the keyword extractionion。And then we have like a。

We can have like keywords like conditional response retrieval。 Like。

 this is a retrieval based conversion system。 But， of course。

 we can use like a generation based response on。

![](img/41c7ebd7e80a872bb64632dd1a9a13bd_243.png)

Model， basically like given this given this new like topic， keywords。

 we want to generate a response to this utter。

![](img/41c7ebd7e80a872bb64632dd1a9a13bd_245.png)

And here， like given this coding a book right， we generate like interesting。 I read about。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_247.png)

Cding from a book。 So this is a implementation realization of this topic。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_249.png)

And the key thing is the， is this part， like how we can do this topic transition， right。

 from programming to coding and book。We， we could somehow use a kind of like a particular model。

 a kernel based model， like to like to like capture this topic transition。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_251.png)

And the plaza targeted the rule guided the rule。So， first on。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_253.png)

We want this transition， right， We want given whatever keywords， we want to transit this topic。

From this keywords to another keyword， let。Is like a closer。

 that is closer to the to the target keywords， right。

 this is the target topic we want to achieve at the end of a conversation。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_255.png)

So from program， we basically translate to like coding book because book is closer to ebook， right。

So we use the what， we， we kind of like evaluate the distance between the keywords。

On in the word embedding space。Yeah， so yeah least is the next。

 the next keywords must must get closer to the target keywords。

And also we want to achieve this smooth transition， right， So we want to constrain here， right。

 the two keywords， the next keywords will be close to the original keywords。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_257.png)

In the word embedding space， So this basically makes ensure that the。

 the next topic is semantically close to the current topic。 So this ensures this smooth transition。

And we can tune the weight of one and2 to control the aggressiveness of the chatbot。

 like how aggressive this chatbot will guide the conversation from this original topic to the to the target topic。

😊。

![](img/41c7ebd7e80a872bb64632dd1a9a13bd_259.png)

Yeah， so basically， there are two， these are two like competitive kind of like。

Losses or like objectives， right？ And we combine this two to。

 to basically like achieve the so called target guide open domain conversation。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_261.png)

![](img/41c7ebd7e80a872bb64632dd1a9a13bd_262.png)

So okay， heres some results like。The target is dancing， right， and from whatever topic。

We see like the conversation， like playing sports。 The topic is sports。 and then basketball。

 And I like basketball， which is the topic about interest。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_264.png)

![](img/41c7ebd7e80a872bb64632dd1a9a13bd_265.png)

And then like rap music， right， So can see like from sports interest music。Music and song。

 and then and then singing， right， And then from singing to like， to， to dancing， right。

 So you can see there is a clear like topic transition like basically throughout the。

 the course of conversation。

![](img/41c7ebd7e80a872bb64632dd1a9a13bd_267.png)

But， of course， there are these， these kind of like a pretty， like。Simple and preliminary solution。

 And there are different。 of course， this this system can like a fail， like in， in different cases。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_269.png)

Yeah， so overall， like this is the how we can do like a unsupervised controlled。

 controllable on tax generation。

![](img/41c7ebd7e80a872bb64632dd1a9a13bd_271.png)

Like at both like sentence level or composition level。 The key idea is the is the same。

 Like we come decompose the complex task into competitive sub objectives。

And the issue of the objectives can have like a direct supervision for， like， for learning。

 And which kind of like a train list on。Our sub objectives jointly。

 we basically can like drive from model in towards the direction we want。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_273.png)

Okay， so this is pretty much about this this parts。

For generating text that contains desired information from input， in， from input。And yeah。

 least on the two central g， right for tech generation， how we can generate natural language。

And how we can generate the outputs that。Is like containing on relevant information。Okay。

 so this is pretty much of this lecture。are any questions。



![](img/41c7ebd7e80a872bb64632dd1a9a13bd_275.png)

Yeah， cool I'm happy to negative questions offline。


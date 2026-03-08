# 【Hhu Dusseldorf】表征学习 ｜ Representation Learning Msc Course Ss2023 p03 P03_W03_BERT-自然语言表示学习 -BV1RPZwB6EJZ_p3-

All right。Hello， everyone。And welcome to week for today's topic is。Language models。

Or more specifically only bird basically。嗯。So I will go over some of the natural language processing basics。

 so how do we handle language at all？Then。The architecture that going to use。

So a short recap of transformers。So I assume most of you kind of know how transformers work because you auto deep learning。

 yes。发开。T it to you again anyway， because I think it's important。嗯欢迎你。Yeah， language feature excs。

 everything together then will be this model B， which was like the first I'd say。

 proper representation learning model for our text。可。But。First， some questions for you。

 how and so far you only basically have to work with images in this course anyway。

So regarding deep learning or representation learning。诶。How do images differ from text？So。

They scared。So may scale in two dimension the images to me， yeah， yeah， yeah。Yeah。

 images are too dimension。你时间。です。はちは？That's a like variable link。

Okay they can of course have also different shapes， but you can resize images。

 you can't really do this with text。3 size be right like this， Probably not。就关于。突击。嗯。What的。This is a。

Very exciting time the Texas forward。Yes。系嗯。再来一次。就是道人。Inhaly， numerical continues。

 so the different pixels have。Different intensities， which can be easily described with a。

Real number of float number。And she。系全我都出得。诶。That's， basically。Property of the data themselves， but。

Then what can we do with the data， For example， the things that you。Things had learned last week。

Those pretext tasks they talked about could you do this with language。So yes。

 I mean you you come to test。I mean， kind of a lower question。

 but generally all the transformations that you can do with images are not easy with text images。

 you can scale and rotate and blur and colora jitter， and you can do transformations with text。

You can。Well， I other what is used like handcrafted。Sentences that have like the same meaning。

 but like generate transformations are。Very hard。Rets。Basically no transformations。Okay， and well。

 finally， I think。The downstream tasks。 So what are like the typical downstream task for images。

他安全对啊。The classification is like the。Probably the most popular one。

 segmentation is already like a little bit difficult but representationally because like quote pixelix。

嗯。But。Most things that you want to do with。Images， you want to learn some。

Can you basically describe the staation and I don't know if you have some NLT experience。

 but I was like some typical NLT tasks。The next one。Yes， for example。走。T。另个算 for一个。

More difficult and guess。喂，怎么听。佢 happy everything。And here are some of the task translations。

 so there we have the input at the sequence and the output is a sequence in a different language of potential different length。

And。Text the speech。Text is usually more multimodal with than images， so it's connected with。

More different domains than images。 So we have data sets that combine text and images。

 You have data sets that combine text and video data sets that combine text and speech。

 So text is like the。Common core domain， basically。If you want to learn something more youot。

The sentimententmental analysis， so what's like the mood of a sentence， which is again。

 justification。Summarization and。That may be interesting named entity recognition。

 so they asked to task what is like the subject。There's a sentence it's talking about and where is it reference to？

So。If I say the tree is。嗯。I don't know， an oak， it is very tall。Then the subject would be tree。

 but also like the it in the next sentence， which refers to the tree。Okay， but before we can。

Go further about all that stuff we have to talk about。Toop first。

So I won't go into detail there because that's not the focus of this lecture。But， basically。

We assign。Each words twin token。And some or less common words are split into multiple tokens。

So here we have the sentence， does tragic understand language and the words does understand language are all very common so they each get there。

On token。Yeah， but check which is not。A con word and becoming more con maybe。

 So this gets split like in two tokens， G T and speech token checked GT and T and these hashtags here mean that。

That is like a subwar token。So when there are lots of different ways to do this。

This one is from the word piece tokenizer， which basically takes a whole very large corpus the data set of words。

And looks at which words are very common in the science that they each to their own tokens and then。

Which words a little bit less， common and then splits them into two tokens， basically。

Spititz the birds。And tokens in such away so that you can。

The short left least number of tokens for a typical text。

So it basically does the kind of compression。On the test。And then， each。Zg gets the site number。

And the work tokenizer has around 30，000，000 tokens， I think。

 so each text gets turned into a sequence of numbers from zero to 30，000 roughly。

And because it splits uncommon words into smaller words， it can handle all kind of new words and。

Ws the different languages and other things that he that hasn't seen in the。嗯。In the training data。

So， but you don't need to know any details about that just that。

Text get turned into a sequence of number。Okay。So then how do we deal with our。

What input output should our representation model to take？So， for images。U have something like this。

 so we have our presentation function G。An image has like the shape。Three times。H times E， the W。

 so three car channels tied with for each you can a representation for each pixel。

 and then you compress this into some representation。啊。In some t dimensional representation。

 each image gets represented as a singular vector of some dimension。

Now here we must take a variable length of vectors。Now we order vectors。

 somehow we turned our list of numbers into vectors， how we do this a jobboard makeup。

But our function needs to take a variable length of vectors。 So that's what this star represents。

 So R star is basically。The set of。Of all vector is a different length。

So this is basically like A StarP。It's like the union of。阿逼。Timeines L for L from0 to infinity。

That's what our input is， sequence of vectors of arbitrary length。

 so what then should output what would be a good representation shape？For an。こ昨年度。Any ideas。

So for images they have just the same vector， would this be a good idea？For text。I mean。

 the way I ask this probably guess that the answer is no， it's not a good idea。

 but why do you think such a representing a text？As a single vector might not be a good idea。です。

The get strong maybe。性がな。Yes， so basically that's one point。

 so basically like the information density you text can vary much more than in an English。

And the other thing is you have to。Think about the tasks。So things like named entity recognition。

I like token level tasks， so you want to predict which tokens exactly refer to which entity。

And if we have only。One vector as a representation， this is very difficult。Baこ。So嗯。

That's where basically we want the output also to be a sequence of vectors。

So we want for each token and representation output here that matcheses the error。

Which used for like talkingken level tasks， like name entity， name entity， recognition。

 But you also don' like an extra output that。0ero， poier。

 which is like a summarization for the whole。Text。Which we then use for not token level tasks for tasks that use the whole input like。

Sentdiment classification。So tos that take。The input and take like a finite number of outputs。

All right，How。Can we deal with variable thing？Inputs in general， so what kind of neural networks。

 architectures。主管。也死了。です。On anciary current neural networks。So， if you don't know they， basically。

Work like this。So， you have your。Neer here， basically do you have your tos X1。读exel。

You this network has two input。And two outputs。So the input at the first step is basically。

 let's say zero， it gets zero here。And the jokeking here is some kind of network。

And it outputs the representation of Z1。And a hidden state。

Which then goes into the same network with the same parameters again。But with the second talking。

W and outputs。你出。And hidden representation， which see was in the next。Ands one and then啲。Last output。

It's like the hidden state of oil of everything。Z0。So they are。Some problems with this。

 maybe some of you already know if you talk about this in deep learning。

What are some problems with our hands。With the information only flows from next。X。三千。没。Yes。Yes。

 it's one thing。不そ。Yeah， for tokens that are far away in the sentence。It's hard to。S provisionYes。

So that are like the two most important months。Like the long term interactions between words isn't really given。

 but of course， in like sentences， the first word in the last word can be very。回理。

And the other things like。The vanish grave a problem。

Because it has to go to the same network every time that gets gets。

Very the gradient basically at the end。 And there are ways that solve this， like LSCM， long term。

 shopping memories and。What are called gr cells， but they don't solve like a problem of long term interactions。

And also。The information about the whole text， the Z zero， only basically comes up at the end。

 and therefore there tends to be very little information about the beginning in this last。😊。

Hidden state， so it forgets a lot。😡，And other things that you can do are one dimensional convolutional networks。

So。Basically， the same as with images， you kind of like。可呢。Which takes。Some fixed number of tokens。

And combines them somehow and the output。And you can do this on multiple layers if you want。

But this has the same problem with long term interactions。

So the way to solve this basically is to learn the interaction， to learn which。

Words are related to which other words， and this is done by attention。

And you can combine attention mechanism with on ends。Or you can just。

Only use attention and then you come to transform us。Okay， so I'll explain the attention mechanism。

你辉。So。I mean， you say you're all kind of familiar， so I don't won to take too much time。wa。Basically。

It works like this。 So you have your。Inpoint sequence。一万。To his。And theyre all de dimensionsal。Then。

 you compute。Values。The called V12 V L。 let's say they are D。Q TV dimension this sensor for。

Qury key value。And。They can compute it in any manner from the input。

 but usually this is just a simple linear layer。So V I is equal to W V times。X I。

Where this is just a matrix。And you apply the same matrix for all。That doesn in the input sequence。

Then you want to compute the output。Though， so。Z Y has eed some of the values of the other tro。

And that's called the weight alpha。白追。And the weights。Short some up。主管。

So the idea is that for words that are very related。To this word。

 this value should be high and for other words。This should not be high。So again。

 there are lots of ways to compute this。Basically， this is a function that takes the X todays input and spits out some number。

 the attention score。But again， thiss usually just done。With linear transformation。So。We computer。

Very。To I， which is linear transformation Wq times。X i。And the value。Which is not the value， the key。

T这我 just able to。W K times X J to be F。Three mattress Cs in our attention mechanisms need WD， WQ。

 and WK。And then we compute the attention。佢注 x one。XA and this isnt just the dot product。

 I hope is' still on camera。And usually skate this by the。Dimension， I mean。

 there are different ways to do this。And then we apply it。Soft marks to this to scan it。

We basically make probabilities of this， and then we get。这么意思。And that's also basically what'。Yeah。

Yeah， the basically the vectorized form。Of course you can put all the input into one matrix by just stacking them and then applying the matrix to this。

 and then they call this Q and K。Can you do this operations？And to then get some more express。

A more expressive layer， we do this basically multiple times。This name calledmoy hat tension。

For each。You have some number of heads， say 16。And for each of the heads， basically。

 we have a different。没得。So we had some subscribescript everywhere。And the。的明星。第一。

AV is then usually the。Tal dimension。 so the input dimension divided by。Number of pets。

So if the input dimension， if each of these input tokens has like size 512。And we have。16 hits。我HX。

Then嗯。Here， the output dimensions of these layers will be like 64 each， and then we concatenate them。

 get back back to。派发了2。And another linear layer to。And。

We have turned our sequence of vectors of size 512 into another sequence of vectors of quarter size 500。

Then呃。We act another。Shorts。Andl key on top shows a two two layer network。

 three layer network with one given dimension。And this is then a transformer block。

 and we just stack them however often they want， and we get them transformer。

And also important just that works and neuronss are like the head norm。

 so has like the residual connection and the layer norm。

And because of the residual connection it's important that the dimension basically always stays the stay the same。

 I mean you could do this differently， but usually。For every block， the dimension space is the same。

谁。And。Yes， how do we train without？The way that it was done first was autore。

 so by just predicting the next word。So if you want to do this。With attention。Just in here。

Right he need some kind of mask。Because transformers are inherently bidirectional。

Predicting the next word is trivial because it basically already sees an expert。So to overcome this。

They basically artificially technical the weights to zero， so they said。AIJ tove。

If J is larger than I。So that no information from the right can flow to the left。

And if you want to train the gen model that is necessary。

All the GPT models are basically trained this way， so check GPT you assume everyone knows。

Thiss basically drain this way， but always predicting the next words and also like1 building al tricks。

😊，But if we just want to own representation， this is not very good。

Because if you want to answer some questions， then。About。

The first word in the sentence that might relate to like later words in sentence。

 so you want to always have the bidirectional context。So we cannot learn auto request。

So we will use pretext tasks。Basically like with images。

 but we had used other creatures pretext tasks。And the first one is。ます。Language， small。

We basically just remove some input tokens。And then try to predict them。

So the idea is if we can do this accurately， then we somehow understand the language。Originally。

 this was called the closed test。Which was something of。

A concept from like psychology from I don't know， 70s to test that someone was somewhat frequentent in a language。

So， I assume。Everyone here speaks English， I hope。So can you tell me which words they are probably missing here？

上。所以。30多。我做人。系我咧。阿少。啊。I know我 this。あれないですアン。And what than AI， Okay， you failed the human AI test。

Of course， I like。Diffor it could be a store， it could be a shop， that could be market。

There's usually not。The perfect answer。But。If you can get it right。

 you probably have understood something about。第一。The language。So how do we prove this practice？

We introduced the mo token。We and we just remove some words。

Then we take a representation of the smart token。Because remember。

 each token gets its own representation at the end。And just put a linear layout of that。

And then try to predict this。They only have a finite number of tokens。From the example， from above。

The road is organized it with like20 tokens。So this would be linear layout from， I don't know。

If P is like 1024， control 24，2 per of00。whichhich we would have to learn just normal with cross antropy。

And there are。And the usual hack around us that are chosen。

 and they usual they're basically always chosen。We select 15% of the words that we want to mask。

But then we don't mask every one of them。Why might it be important that you don't actually mask？

Every of these words， in one of these words。Can think about how then the training input would differ up from the。

Test input， basically from the actual downstream task。If。The use。ま。家中。The buy is always going for。

This spoken is something。こケ事。Yesス。I to towards guess。If you put。で。对呀。

So in the basic although like the masked to never appears in the actual text。😊，So。

To better represent the downstream class then we just。Leave some of the words unchanged， and。

We're based on with men tokens。嗯。Yesす。And then we only predict。

The chokings that were selected that again， so is different basically it sounds a little bit like a de noise and auto encoder。

 you put noise on there masked and then we reconstruct basically important。😊，把是公。嗯。

Actually predict only 50% of the selected totals。And we only predict using。

The embedding for this particular show， So it's a little bit more like like a mask I was on Korea which you will learn about later in the course。

Yes， I don't get the last。喂。1230。We can just increase our。马嘅总经理。していいす。No。

 because only the selected filters are。Given to the to this prediction that idea。

That means that sometimes this way， the prediction layer will get the input that is already correct。

So， this is。Actuallyly different in this way。It's also prevented to adjust。好易俾食业。

predictdict common words because if you leave this out and basically if this is。Too large。

 And a good strategy is to just predict common words and your。Rights kind of often。Okay。

 and the other pretext pretext task that is used is next send inspiration。

So it's a little bit more long term， so we need to understand multiple sentences and their concept at once。

The question is， does the second sentence photo？After the first attendance， so poor went shopping。

 he bought new shirt。Makes sense。Buying a shirt and shopping is connected。

Second sentence is Ramona make coffee， vanillail ice cream comes for sale。Okay。

 both texts have something to do with food。But otherwise cannot connect to non signature。

This this not。A perfect guess I no。Question there's not a perfect， there's no answer usually。

 of course， sometimes real texts that are non secrets where it's not clear how why the next sentence followss on the first。

But Georgia is also quite good。So how do we do this in practice？We add more special tokens。

 so we have the Mar soken before， now we have the glass token CS and the separator token SAP。

The glass toping is added at the beginning。And the separator talkingken is added at the end of。せ日す。

And then they also get some number。And because there's not a token level task。

 we only want to predict yes or no， it's a binary rec classifier basically。

 we predict it on the embedding of the classstone， so the emdding of the classt is basically that z0。

 that zero that I talked about before。The betting of the classroom should contain basically everything about the task。

And we'll use this in if we want to do non toking paste。Ts at the edge。嗯。Yes。

 so the separator at the。In the middle of course important。

 so the modern is Richard the first sentence and the Richard the second。

But even if we don't use next sentence prediction， the separation took at the end is。Very important。

For like a more technical training reason。Anyone that maybe me some idea？What do you think we do？

You knowYou know we usually want to batch short inputs， right。

 we don't want to just have one example。This is inefficient。But our texts have different things。

We need to somehow make them the same length， so it works。广洲。Yes， you， basically。

Then the separator talking at the end tense the network here starts preparing your don need to'll pay attention for the rest。

In practice usually also of the model some padding masks。

 so we don't compute attention between a patting token and。

In non getting talking but is' always's important for this。Okay。

 and that are basically the two protest tasks that。But users。And。Especially。This one。

 the mouse flangch model with these particular hyper power dust is used。A lot。

And I know maybe some people should investigate if other Hybar does might be better， but。

No one has bought out so far。They seem to work。ok嗯。Now what me saying how we turn tokens。

 so integer numbers between0 and let's say 30，000 came to vector。And the answer answer， we just。亮。

So basically， we learn。For each token。A vector。In some dimensions。And we train this with。

Greatraating descent like before， so you can basically imagine this slide feature you have your tokens from  zero to 30。

000 you enco them one hot， and then you put linear layout top that。And。Why do you think。

Learning such an embetting vector。Is better than just using the one Hs encoding。So。We have our。

When what total encoding is saying。And then we learn the linear layer。So yes the idea it's one lot。

 so the vector is only in 1。0 else and it indicatess which to it is。😊，And then we。

Compress it basically， with a linear layer in。上次说啦。Of course， the one advantage is。It's smaller。

 it's computational more efficient because that's a dimension that we are carrying through our own network。

But what's another reason why you don't want one hot。Inports。可以。公司。Exquisite。Different uses for。

The same one yes。等咩。比说他。关这些。就跟说他。Somehow express。发出去有し。No similarity in this attention， but one。方Yes。

I mean， okay， I guess the attention would still work because before you compute the attention。

 you apply another matrix anyway， but yeah， the point is you learn。Similarity between words。

 hopefully， at the end， words that have similar meanings。

Or somehow semanically connected should have similar ems。So that's why weve known this this way。

But that's， of course， not enough。诶。Transformers have no inherent concept of order。And of course。

 the order and attendance is very important。嗯。You can't just scramble the sentence and it expected to have the same meaning。

 so that's why we have this position and。俾识啲。We from each起。嗯 position and sentence via a number。

And then we em this as well。Yes， for which reason we。咩啲。年你啊。Because more is just not necessary。

I mean you can basically。At any point， your。The matrices were some more complicated layer。

 but it turned out。Uing this simple and everything add simple and just making network deep at the end more efficient。

😊，です。What does this like say like me。Yeah， I get there in a minute。

First about the position em bedding。If we do it this way like we。

 that means we have inherently a fixed number of positions that we。😊，Ha and be。

So let's say you choose the number。Like ten ten thousand。And then。

We only can inbed positions from zero to 10，000， and if we have some sequence input sequence that's lower。

 then this just doesn't work anymore。So there are different ways of doing position beddings。

That don't learn stuff like sinenooidal embeddings， which you use like sine and cosine stuff。

To give a unique embedding to each position， but this way you're limited to a certain number of positions。

Okay， and finally the segment embedding。嗯。But。This is the next sentence prediction， pretex tasks。

And this mask basically tails the network。维持。A path belongs to the first sentence and which belongs to the second sentence。

So there you only learn two embedding vectors， basically。Right。And you might say。

This is not necessary because you already have the separation token， the network should already know。

 which is the post， which is the second sentence。发0。Again。

 it just turned out it learns this way faster， nicer。Okay， now we have three different beddings。

Basically， most important on the text bedding and yoga bedding。One bedding for each token。

 the position bedding， one position， one vector for each possible。Position and the segment embedding。

One lecture for each possible segment。And then they can already see it， we add them all up。

Why do we do with this， do we add them and whys has not abrupt them？😡。

You could also just concatenate them。Yesす。was so high much。什司。

Because that's because white's not a problem， if you have two random vectors in high dimensions that're basically almost guaranteed to be orthogonal。

So if you add them here， there's not much risk of collision。Then of course。

 if we just concatenate them， we would have a huge factor at the end， we don't want this。

This is slow。Oh whatsoever's so。Just as we want to have。

Just as you want to learn correlations between similar words。

 you might also want to learn correlations between。Words and positions。

 maybe some words if they appear at the first position like the。

Should have some special correlation there。If we。Learn them independently and just stack them。

 the learned position vectors and to vectors would always be。

Agons so there would be no information flow between them。So that's why you just add them up。

And then usually also like some form of norm afterward typically lay and norm。切嗯。By the way。

 this week's exercise。Will be bird， So we we will implement some small version of bird。

And then theres again explain somehow a little bit and to implement this year。Okay。

 then if we put this all together， we get good， which then for bidirectional encoder representations from Poas。

Again， like all the popular machine learning methods they somehow much work together and actually some nice acronym。

But the important part is bial because even though it's not like the first time transformers have been use language。

It's the first time that I said， why do we actually read this from left to right when we can read both directions together？

刚。GPT， like the precur of chairGPT。Was trained with transformers before birds。

 but only like one direction。Of course， GPT is inherently like a generative model。

 so it needs to be learned this way， but。管理委。So。Bt was trained using these two pretext tasks。

Next1 inspiration and mathed language modeling。Its。As the transformer architecture。

 the large curve has 24 layers。It 1034，6 heads， so total parameters us 340 million。

 which is not very big in today's standards。嗯。Does anyone know what CheckGPT for is about a number of parameters？

I think it's already the trillth。So this is not much。And it's not even so old， but。It was strange on。

The books corus， which is。Books。T the8 million words and the whole of English behaviors。

 which is like 2。5。Pillion words and because you use this next tense version， it's important。

 then actually uses some large。Contiginuous text。From which we control。嗯。Next sentence。其嗯。

How do we evaluate？How do we evaluate on或 done some tasks。It's basically again linear probing。

 we put a linear layer on the top and do whatever we want with it。But what's important with word。

 they fine tune the whole network， they don't just train last layer。

 they fine tune the whole network with a small learning rate。The tail takes a long time。

 but is needs a little bit better beside。 You can also just。嗯，把就。You can just go do that。

 you can just do it， which is faster。And the waves of good and the other variants that will tell you about in a minute。

啊。Freely available for like power face and whatever。So if you want to some language stuff。

 you can just use this。Put a small electric control into your good go。And it's。

Evaluated on the clue benchmark sets， which。I forgot what sensor so on the video that I will upload a there a link there。

 I think it has like 17 tasks in total。My， is Kooc tasks。We have sentences and the task is to say。

 which of these sentences make sense？Okay， who thinks the second sentence makes sense？那么如。嗯。

Some of the tends are very obviously nonsensical for humans， at least。

 some of them are a little bit more tricky。They're all also available in P place。

 so if you want to take a look and investigate what these data sets look like， we can do this。

Another one is the RTE。Task， this stands for something， something entertainment。

Which is the question does。The second sentence is intended upon the first。

So does the second sentence for you from the person？In this case， here are tough， though。

Something about pot dying， and then。The new installation of the Poe and the 16。

And the second sentence is Pro Benex 16 is the new leader of the Roman Catholic Church。

Wch is already kind of complicated to understand the disentment the first because it kind of have to understand if the pope is the leader of the Roman Catholic Church。

And。Comping like installation and such。But like there are lots of ata。And B did quite well。

 So this is just the the。Ter directly。Copyied from the paper。Do read the paper if feel interested。

Important is mostly just here the last line， GT。Which is a transform motor with like the same number of parameters as bird base。

But it outperforms。Put outcomesform between basically all tasks。So like especially the COD tasks。

 empty RTE tasks。That's like pretty big。Okay。Whats this。

Then there are lots of birth variants that have also worked in the name。Like Robertberta。

 for example， which is basically the same as Bch， it has different training parameters。

It does not use the next sentence prediction task。Only the last language morning task。

So it turns out we don't need next sentence prediction anyway。We need your leaders。

 but you will need to implement an an this for this week's exercise。

The most important changes are just bigger， batch size， longer training， more data。

And I got better advice？And then Albert and distber。Which don't perform quite as well。

 but are much smaller and faster。And。Basically， everything I said so far can be applied to any other any other kind of sequences。

 so G A， for example， for G A theres。In a for RNA， theres RNA and there are other sequences。

 I assume。In which is it' use as well。嗯。Of course， especially for RNA and DNA。

 this makes much more sense than some autoreive way because。In language。

 at least there is an canonically direction from left to right。

 even though it's like the last word can be important for the worst。

 but like an DNA direction just like or complicated， I guess。

 doesn't have like a real left or right direction。And these DNA and RNA models also use like the same hyperparamas for mass language modeling。

 so 50% selection learned。80%80% masking。Because it just works。So so far。

 no one has like figured out a better way to select those type of parameters。嗯。Yes， and again， I'm。

Poss，反 needs。You can get more。Next week。So， yes some further reading， if you want。

And especially recommend us transformer blog post， which is actually written from Nicholas。

With by Nilas。Yes， do you are any more questions regarding this lecture？So what's this fair to start？

2。Basically， for everything。Lguish related。You want to have some sentiment analysis on tweets for example。

 you want to scrap like all tweets that have like the hashtag 22 election or something。

 and you want to know which have like a positive sentiment。

 which are like positive and which are negative。You could train all the data and train it on this whole big network on this。

 or you could just take your bird embeddings， you could use a pretinent bird network and then just train a small linear layer on the embedding。

No，It does not generate， so it's only for representations basically。Where sunny for。So sorry。就这一下我。没。

对啊。Books and also like why there。你次偈。The traininging is more fun best。I thought about some polish。

So they was such a Po project and they found that the data also carry together and they for example。

 also use like。Sometimes it's for movies because they want the sts。对啊。Yeah。

 if it's only trained on English， then it's only going to。Learn English。

 of course in books and like novels， there's already a lot of dialogue， so I kind of learned that。

But。Of course， learning multiple language at once is complicated because。咁。Theres lots of。

You need like a lot more data。Because呃。Actually， you want to learn that maybe one word。

In Polish or English means the same in non language， so it should have learned。

It's similar embedding， but it's very difficult way to learn if your texts have only English and texts have only Polish。

 so we want to have texts have like multiple stuff。

So you need a lot more data and like some of the follow up things of birds use different languages。

 I think Robert， Roberta used multiple languages I not short。诶嗯。

Like get a lot more variants of but you you can。Look at them。 Yeah this link。

And some of them use different languages， but yes， the training data and languages。

Very important animals。But it's possible to learn which languages once。

I assume most of you are played around like with Che here， right？

And this is pretty good at multiple languages and even translation， not perfect。

 and of course it's trained differently。Justica Gold has access to such a huge amount data。Right。

It is。Anything not forgot in this lecture， last lecture， anything anything。Okay， then。I think。

They don't have problem thats at lecture now， and still do the。Exercise in。11 minutes and。

Quarter past4。All right。
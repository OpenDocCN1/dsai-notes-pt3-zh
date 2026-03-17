# Stanford CS221 ｜ Autumn 2025 p17 Stanford CS221 ｜ Autumn 2025 ｜ Lecture 17： Language Models [3orP3u2-jcg] [BV1XuPrzwEes_p17]

![](img/149d190c2ff6f22ac426057c1ba8d500_0.png)

![](img/149d190c2ff6f22ac426057c1ba8d500_1.png)

So today， well talk about language models。 This is one of the very few lectures that don't have executable format。

 So you don't have to trace through code。 We're not gonna test you on it。

 you're just gonna and enjoy。 Okay So we do know now that language models are everywhere。

 I'm sure all of you have used it chatT。 And then it's on your phone when you write type anything on your keyboard。

 you see the autocomplete。 That's a tiny language model there。 And some of you may have used cursor。

 maybe as part of your homework。 You can see code completions。

 That's also a language model running in the background。

 But you may not have known is that these days， language models are really everywhere。

 And when I say that， I mean that they can be found in robotics。

 they can be found in other all sorts of interesting applications。

 maybe even voice videos that you don't even think about。😊，Okay케。And these things are very powerful。

 That also means that they are also like getting industrialized。

 They lot big companies trying to build these giant artifacts and ship it out to you because they can do a lot of stuff。

 So I'm gonna show two examples here。 You have the Lama。

 three models from At and Qui3 models from Alibaba from China。😊。

And so we'll run through some examples just to show you the scale of these language models we're dealing with today。

So first of all， you know， to train a typical large language models today。

 we have 03 is trained on 36 trillion tokens。 What does that mean roughly that is like 27 trillion words and if you just know write down assuming like maybe4 byte per word or something like that you get about 144 terabytes of data just raw text and to think about that to say that on your laptop as a lot of data you have let's say you assuming maybe  few hundred0 word per page then you can get about 90 billion sheets of paper and you stack them high。

 That's about 9000 kilometers above the surface and just for contrast the space station is only 400 kilometers above earth and the Earth only has about 6000 something kilometers of radius so there's a lot of data and if you were to type this data out at 50 words per minute。

 you're gonna have to type a million years So I think it's really important to kind of just grasp the scale of the。

Wguch models are we working with today。And let's say you with Lama 3， instead of 36 trillion tokens。

 you have 16 trillion tokens in your training， let's say a 400 something billion parameter model okay so there's a nice rule that can estimate the amount of flops that you need for training such a model that gives you around 3。

9 times 10 to 25 flops and which is really close to what has been reported by meta and if you just take one of these GPs。

 let's say8100s off the shelf， these are very expensive and you divide it up you get something like about 8808100 days where if you have your one of your laptops。

 you're going train for maybe 65650000 years on your single MacBook and so that works out to be about 42 million of course if you assume$2 per hour per age 100 GPU for single。

So pretraining run of one of these giant language models。Okay， so so did makes sense to see。

 you know， MVD stock price that high up and and is very happy about all this development。😊。

And this is not the end。 and people are still building out these data centers。 They're。

 they're trying to send at this point， GPS to stay to space。

 We have Google exploring space based infrastructure for training launch models。

 same thing within Nvidia。 And so like。You don't know where this is going。

 things are like expanding really quickly， like it doesn't seem to make sense。And， you know。

 given the current trend， we might just have the GPS in space before know， Stanford wins in the big。

 which is next week。Okay， and then you have giant teams working on these language models。 You have。

 for example， for Qin 3， more than 150 contributors and for Lama 3 and G4。

 you have three pages of authors。 So that's probably more than a couple hundred people。And。

All of this money， time， compute people just to create these giant matrices of numbers。

 which I've learned about from， I believe， homework2 and。First couple lectures。

So how this all make sense， right， spend all this effort， all these millions of dollars just to get。

 you know， numbers。So to summarize， this is kind of the state of language models。

 we have a a huge chunk of internet。 you' train for many many days for many many dollars and you get like this just file of numbers。

 And so for this。This lecture， I just want to give you like a gentle introduction of like what this kind of like means。

 like how do we make sense of this right So first of all。

 we're gonna to talk about what exactly our language models So what they are fundamentally as objects And second。

 why is a good idea to model language， like there are many things you can model。

 why why is it specifically language and third things is that what makes language models work。

 Like what are some key ideas that people discovered over the years that makes it a good idea to just train these things and scale them up。

And finally， I'm going to talk a little bit about where we are today。 you know。

 like as you as a student taking this class， you know， what does this all mean to you？Okay。

 so what exactly your language model？So language models you know by definition or models of language。

 but you're like can this is not helpful like what does that mean Well for our purposes。

 we say language is just a structure sequence of characters Well that's a very very vague description but I assure you that many people who work on language models today。

 don't really know you know language more than that really so language can be in many forms obviously you know English。

 here's Tamo， here's a Python Python is language that you work with day to day。

 you know even sign language is a language that you have characters you have grammar okay。😊。

And vertically speaking， the structure from a language comes from two things。

There's the vocabulary which means what are the things that you can put into this language and second there's the grammar which is like the rules or conventions of how these characters can follow each other okay so they roughly define what you could you know work within a language and what you cannot work with within the language and to learn a model of the language that means learning the structure of this language you know understanding the vocabulary or understanding the grammar and try like best predict it or produce it like if I have a language model you should be able to like tell me you know how likely or how possible or this sequence under this particular language。

Okay， so here's the example， we start some examples。With basic language modeling。

 you're basically dealing with how can I best， to some extent。

 complete a sentence or fill in a sentence。Now have this sentence here。

 the stock market crashed and investors something。 Okay， so you have prior。

 So you've grown up you speak language， you speak English and you have a particular belief of what the blank space should be。

And we can run through some examples。 So the first example is that if you just put in drawers。

 which means like desk in Chinese， it doesn't make any sense because it's not a particular useful It's not a valid。

 actually word in English。's， it's a wrong vocab in this case。And second， you can say， well。

 the market crash and the investors started going or going。 It's not the correct semantics。

 It's also not the correct grammar， but it's starting to get within the realms language。

 the English language。You might say the stock market crash and the investors panicked。

 which is a very plausible completion。But then there are many other plausible completions。

 and one of them could be that you celebrate that the stock market crashed because you really want to buy stocks at a very cheaper price。

And in particular， you want to know that。Depending on like how you kind of see the world。

 if you imagine yourself to be a language model， what words that come next really kind of reflect。

 you know the kinds of words and beliefs that you kind of have seen before。

 know to prefer the word celebrated， you know the model or maybe you would know something about the world to know that。

 okay， it's actually better to celebrate than to to panic， for example。

 because panic is more common if you look at the English language。Okay。So。

A language model then is just some object that you kind of like， you know。

 obtain un quotrain to really model language or predict a language。 So if I have a language model。

 it's just an object that takes in supposedly a prefix or any other forms of text and then complete text。

 There are many ways we can do language modeling。 But for now。

 we'll stick with kind of like completing sequentially。Okay。

So now we'll talk a little bit about the tensor view of the language。Sking。Okay， so let's。

 to kind of conreetize this whole thing a little bit more。

 supposeose that we represent each word as a vector。

 have you have these word vectors that you play with theres embiddings that you understand that you can represent a particular discrete word as a continuous vector。

And suppose we have a vocabulary， which is basically a string to index dictionary with only 10 words that looks something like this。

 Okay， so for the first word I only know these 10 words and then for the first word I assign an index of  zero。

 the second word I assign an index of1 and so on So is a simple Python dictionary。And。

If we go back to the previous case。The stock market crash and investors something。

 then a language model basically say we take in these word Is or like input Is。

 so they we use the index to represent the words so you have a again。

 you have a vocabulary that kind of give you this indice。And it has a shape。 Okay， the shape。

 maybe is a length to the sequence。And then you would have these embedding。

 which is like one individual vectors to represent each of these words。

 and they will have a particular shape， so if you remember you're going to have， let's say。

 define D dimension， let's say in this case4， then I have a 6 by4 matrix。

 okay to represent the input sequence。And then what happens is that you are just asking the language model to do a classification task。

 essentially right I'm classifying what would be a good word to come next， So in this case。

 if I have a vocabulary size of 10， I would say that I would like to you know make the probability of the word panicked or celebrate it to happen to be higher。

 but for words like investors investors like this word to be very low probability。Okay。

 so essentially you're just dealing with kind of like multiclass classification。

 but for you know protecting what the network next word is。Okay。In general。

 obviously you can make the sequence arbitrary long as long as you can train it so you can have a T shape vector and then you can make your embedding dimension arbitrary。

 you can make it D so you have a T by a T by D matrix and then you can have a vocab size of V that means you can just define as many vocabs as you want。

 and then you make it a V class classification task essentially right so this is kind of the simple picture of language modeling。

Now， instead of saying we want to predict a word at the last position。

 which is to you know complete the sentence， you can also just make the language model predict at every position。

 So because you already have the input， you might as well like try to make it do more stuff。

 So in this case， you can say， well， instead of predicting only here， I'm gonna predict also。

At every position before。 So I'm gonna have T by V output tensorship。 So in previously I have V。

 because I have like these probabilities for the vocab for the last word。 But now I。

 I'm gonna have the probabilities for the vocab over the vocab。 But for many words before it。 Okay。

 so for the first vector。😊，You're basically predicting what the probability is for the word after the。

 okay。 And then second， this is the probability of the word。After the stock， okay。

 so you're going to have like a bunch of these probabilities。Okay。

And suppose you look at the last position and let's say you get a bunch of probabilities。

 So some of them are more likely than others。 you can then what we call do what we call sampling。

 say take the most likely that will be greedy decoding。

 but you can also like sample from the distribution。

 you randomly pick according to the probabilities。 Let's say in this case。

 I pick the word panic because the language tells me that， okay。

 it's more likely that this sentence finishes with panic。Then what I can do is then take this word。

Put it back to the sequence。Again， I have this shape T tensor， shape T by D tensor。

 and then I'm going to do the prediction again like from there。 Okay。

 so I can again do the same thing where I take the prediction word。

 put it back to input for a pass and get another another vector so you can continue doing this Okay。

 so this is what we call auto regression or auto aggressive language modeling where you just predict this words one by one after each other。

Okay。You could also batch everything together。 Okay， so there's there's no。

 there's something saying because at the end， the language models is dealing with matrices and tensors。

 So as long as you figure out your dimensions， you can just do many sequences at once。 Okay。

 so instead of saying I'm gonna have a T shape tensor for the one sentence。

 I'm gonna have like batch of B I have two sentences instead。

 And then I'm gonna to have like two two sets of like embedding vectors。

 So they'm gonna have to shape B by T by D。 Okay， so B is a batch T is a sequence length and D is the embedding dimension。

 and then you can do the same kind of like four pass to produce。The shape here， which is B by T by V。

ok。So this is a send batch you've learned that from to。O。

So now let's look at like how we can interpret a language model from a probabilistic point of view。

So essentially what you're learning， this thing language model is just a distribution over the sequences。

😊，Okay so ideally， if you have a very good language model。

 it tells you how likely a particular sequence is， I say maybe the stock market crash and the investors's panic it has to probability have2%。

 by the way， this' 2% is over all the possible sequences。

 not just like this particular you know completion of the word panic but over things like I ate lunch today where I didn't。

Go to gym yesterday or something like that。And you can imagine that you can have different kinds of sequences that have different probabilities。

 So maybe you wouldn't like to see the investors to go golfing。

 so you want to have a lower probability effect that。Okay。And with a joint probability like this。

 what you can do then is to unpack it with the chain rule。

 which you have learned from your abbvationation lectures。

So if I take the sequence of the probability probability of the sequence the stock market crash and investors celebrated。

 I I can just unpack them kind of like word by word， right， I can say it's。

 it's the same as the probability of the word there and then followed by the probability of the stock。

 given the the and then followed by the probability of the market given the stock and so on right。😊。

So this is like you kind of basically repeatedly apply the Bayes rule Bayes rule to like know break up this first part and then condition on this part and then break up this part and then condition on this part and so on。

And so you have a expression that looks like this。Which basically says at every position。

 you can predict will you have a。I'm all of the probability of the word。

 given all the words that come before it okay。Inan。

What that says is that you only need a model that given past context， predict one word at a time。

 And again， this is like what we call auto regression in many cases。

There there are many objectives of language modeling you don't have to just do next word or next token prediction。

 but what I've been showing you is basically next word slash token prediction。

 basically you run em multiclass classification problem over the vocabulary and you do that sequentially word by word okay so you have input which is batched sequences and then you have output of batch sequences with probabilities over the vocabulary and it learns basically this distribution and it turns out that this is the distribution that people sorry the objective that people use in practice for all of these language models that you see at least for pretraining so it's very rare to have seeing other people people doing other kinds of stuff and we'll talk about why this kind of makes sense intuitively。

Another objective would be mask language modeling where instead of you predicting the next word you can predict some missing word in the middle okay so here's an example。

 if I want it to fill in this gap of import something as Ny， you can you fill in a lot of words。

 but you may not want to fill in another language again this is the wrong vocabulary。

 you may not want to fill in import which is the wrong grammar。

 you could fill in Ny if given your past experiences working with Ny and Python。

But you could also say， well， it's a valid thing to fill in jackta Numpy， which is like。

 you JaX's implementation of the same interface for doing some kind of similar tens of operations。

 but in JX。Okay， and this objective， I would say， isn't used as much anymore。

 It was very popular or like popularized by Bt back in 2018。

 so back then people like train these language models。

 just using this objective and they found that you can pretrain Q like just train on them a lot of text and they somehow just become very useful。

 but these days we don't use this objective as often I would say。

So we've talked about what language models are precisely。

 Theyre just like a model over over the distribution of sequences。 Okay， but there are many ways。

 we I talk about how we implement it。 and there are many ways you can implement such a language model。

The very， very naive approach is that you just count the sequences。 So imagine that。

You have like a bunch of internet documents， you just go through like a news website。

 you go through Redit。com， you go to like tour。com and then you just grab these text and then you compile all these text into like a giant repository。

And then you're like， I'm gonna go through all the text。 I'm just gonna count， let's say。

 every sequence。 And then I'm gonna like assign an empirical kind of like probability to it。

 That means like if if I see the sentence of the phrase the stock market had been showing signs of exhaustion。

 and I'm going like okay， increase account of that by one。

 And then you can define over the the entire data set of your preaching or training data set。

 and like you get like an empirical probability。 if something never happened then the probability is0。

 if it happened， then you will be nonzero。嗯。But obviously the problem is that some strings will never show up。

 you don't know you can vary this string that you show and you may， for example。

 play with this word and instead of an， you put it to or and you realize of the documents that you search。

 you just didn't appear at all。So this is not a very good approach。

A slightly better approach would be that you you still count， But by n grams。 So when we say n grams。

 which just mean n consecutive words or n consecutive like chunks at the time。

So these are called Ngram language models in the literature。

And and this kind of involves some approximation to the probabilities that we just shown Okay。

 so for the same sequence， we have the stock market crash and investors panic。

Then this is the original expansion of the probability。 instead of that， we will say。

Were approximated as the word panic only depend on the previous two words。So I'm saying like。

 I'm not gonna care about the sequence， you know。All the words before and investors。 I'm gonna say。

 if I see an investors， I'm just gonna count what kind of words that appear after。

 So this is obviously like a。Simplification by assuming that each word only depends on the previous n by one words and minus one words。

 and this is similar to the mark of assumption that you work with with the Bay lectures except that now we don't say it's one before n words okay。

So back to the counter example， then you can， you can now see if I only care about ngrams。

 Then I find that the stock market， this phrase do appear many of times。 and I can start counting。

 Suppose I have， I want to like， figure out the。Probability of the word crashed。 I can say， well。

 crashed given stock in market， I can say， well， crashed， given stock market appeared onces here。

 but then stock market show up here， but then it is not ending with crashed。

 So there are two occurrences。 now just say okay， I'm gonna assign probably one over two。 Okay。

 and then there's no more stock market here， no， no here。

 so they don't they don't count towards my probability。

So you'll be able basically this essentially like a giant lookup table。Of probabilities。Alright。

 lastly， obviously， we're not here to count text。 We're here to train cool AI models。 And these days。

 when you want to train AI model， you use new networks。 and there are plenty of resources。 but just。

 you know， this is a slide from Android Ka that you just have language model that sorry。

 a new network that takes in a sequence， but predict the next word and you can train it using gradient descent you've learned from。

How many lectures go。Okay， and the view here is that you're going to have these sequences， let's say。

 the stock market crash any investor or something， something。Same as before。

 you have these tensors of this shape， you have embeddings of the shape。

 and then you just predict the output probabilities and。

Because it's it's basically a giant multiclass classification problem。

 You will have the ground truth precisely using your own input text。

 You can just ship them by one position。 So to predict the next word of the， you know， previously。

 it is stock。 So you gonna just put stock as the label for the prediction。 samee thing。

 If you want to predict network next word after stock。 then by by your very own sequence。

 you know that the correct output is market。 So you can just take a sequence。

 shift it by one and use that as your own label。And so that's how you get the loss and you can like grab percate and get your gradients to training your model。

Okay。Cool， okay， any questions so far before we kind of like， you know。

Go into the next stage like so far we just talked about what language models really are。

 there are some objects， they're not moing distribution over sequences， they they seem fine。

 seem okay， but why is a big deal right。So。Why is it a good idea to model language。

 Why not other things， Why is it that we are so obsessed with sequences。Well。

You realize that many tasks in the real world are just language modeling。

 So many things that you do day to day， if you observe。

 like pay attention to very quick very closely， is's really just a sequence completion problem。

 So you might like run email to the G teaching team and ask for extension。

 So you say high teaching team， may I please get an extension for homework 9。 I was something。

 something， something。 Okay， if you have a very good。😊，Let's say expert distribution。

 which is that means like you， you say the right words。 This may get you like an extension。

 But if you say something like， oh， I was， I was like very bored。

 then I won't give give you extension， for example。 So it is a language modeling problem。

And you may think that you may also see that like writing code is a language modeling problem。

 you have an array， you want to like finish know the chunks of code that you haven't wrote。

 haven't written， then you know that's a language model to predict the next token or word depending on what you have shown before。

Okay， here's another example from a friend of mine working on research project。

 You can be like your advisor send you some messages and you like to like to respond to them。

 And based on what they have said and what you kind of like know about yourself。

 you can like start putting the next token prediction。 like next token。

 like next word distributions from there， you can just like keep completing。 And that essentially。

 is like language modeling problem。 So you see like there's a lot of like。

Tasks that are essentially solved if you can model your next word distribution really well。Okay。

A second reason for why language modeling is a good idea is that it enables what we call multitask learning。

So that means that if you train a language model on many， many data with the same objective。

 which is the next token prediction or next word prediction。

 lot you teach the model a lot about a lot of the tasks that you care about。

So here's the Wikipedia article。You know， you can you can read it。

 you can like try and understand it， but if you get a language model to fit on this article。

 you realize that， you know， to do really well on this particular article。

 you have to force the model to memorize a lot of things。 For example。

 if you see Alan mathison Turing you know， the birthday and then。You ask to complete this next token。

 then you have to kind of like force language model okay to say overall all the possible you know tokens and dates and you know numbers and so on。

 I need to pick the right date， So you have to force it to memorize certain things you're trying to like encode this knowledge into this let's say neural network that you're train for language model and same thing about other tokens you might have to have to learn about what Alan Tring is doing where he was born and in what year he did what things So these are all general like facts you kind of like have to induce like instilling into the model。

Okay， and if you apply the same objective and the same model on different kinds of text。

 let's say math， then you learn about other things， not just like facts about the world。

 So for example， in this case， if you' are given a sequence that's are with an an irreducible fraction is a fraction。

 something something， So for example， in a complex plane this expression equals something。

 Then you would know that youre telling the language model to kind of learn about math a little bit。

 You have to be able to predict the correct expression for this。😊。

For this expression that comes before。And similarly。

 you have to get the language model to produce a counter example while something。

 something is not a irreducible fraction。Right。ok。And similarly， if you give it a logic puzzle。

 you can get a language model to see。 Okay， here's a complete problem setup up。 You know。

 given the below， there are three statements about three conclusions， followed by three conclusions。

 And then， you know， who， you know， who is a dancer， who will be an actor and then， you know。

 kind of like logical entailment of all these facts。

 And you ask the language model to predict next token。 And you're basically enforcing。

It to kind of like reason based on what you see in the context。

 So to be able to correctly produce this answer C， the language model has like perhaps you know。

 think， this is disputable。 Some people say maybe you can get language models to memorize the question。

 but there's like you know， many ongoing effort and debates about like， okay。

 what is truly reasoning， what is truly like intelligent。

 if language models can answer all this questions correctly over a thousand of them a million of them are they smartware。

 they just like seeing patterns， you know， somewhere。Okay。

 but what's important here is that you're using the same objective next word prediction andre using the same kind of like language modeling formulation。

And so we solved similar problems like this from your logic homework。 You know。

 you can encode these statements into your first you know， first order logic clauses and statements。

 and then you can like apply you know， all this the system that you've learned to produce a conclusion。

 This is a case where you realize that you can maybe get at the answer with a completely different approach here。

 we're not saying we want to encode symbols。 Were we're gonna to encode rules。

 All we're saying is just here's a giant pile of text。Predickt the next token。

A good language model would simply have like a high probability of predict predicting the correct answer as the next word as opposed to saying like。

 okay， I can explain what the you know the symbols are and the logic are and there's a graph you can draw。

 No， it's just like next word prediction。And so this phenomenon has well was really like popularized by this GB2 paper from Open AI 2019。

 so they say that language models are supervised multi taskask learner and what they kind of say is just like we would like to move towards more general systems。

 we can perform many tasks eventually without the need to manually and label a training data set for each one So that kind of like touches on this idea if you just train on a lot of these documents。

 a lot of these different kinds of data， simply by an next word prediction。

You can like teach the system， many， many tasks at once。ok。

The third the reason why it's good idea to model language is that language models apparently scale really well。

 right， So the idea is that if you have a lot of data and a lot of and the big model。

 what you can do is you can fit all the task at once without any special models Okay so you might think I need a model specifically for Python。

 I need a language model specifically for English。 It turns out that if you have a loss of data and the giant model。

 you don't need to do that。And then the second point is that if you just keep increasing the data set size and then the model size and the number of amount of compute that you throw at it。

 the losses just keep going down。 like there's no sign of like stopping。 Maybe， you know。

 some people would say we're starting to hit sign but for practical purposes of。Of say。

 like we don't really like hit a barrier。 Like every time you double the compute。

 double the mono size， you just。Expect this loss dropping。And so back in the day。

 you would have a separate language model for newer machine translation。

 You would have a separate model for coding。 So this is from open AI。

 This is a model they called Da Vinci Codex。 This is a special model that they have for coding and they train it on a lot of coding data。

😊，Today you have a single model it's called GPT 5。1 and it does everything。

 you know you can ask it to write jokes， you can ask it to summarize text。

 use tools and then do translation and using text summarization and all that stuff like people are already starting to replace old translation systems with these like single unified language models that does everything and it's faster too。

嗯。So back in the day you have these models that are like you know。

 maybe 30080 million parameters are which were considered big， you know。

 these are still a lot of like gigabytes of memory。But today you have these models that。

 you know are really big。 We don't know how exactly how big。

 but we do know that they are probably 100 times bigger and this hundred times bigger model outperforms another model that's a thousand times bigger。

 okay so these are really just scaling up the language models on lots of lots of text。

 and then lots of those task at onces。 and you train them if you train them correctly。

 they just do everything for you。And so this idea of kind of like scaling was touched on by this paper called scaling loss for newer language models。

 And so in there， what they said is that。If you just keep adding compute。

 keep adding data set size and keep adding a number of parameters， you get this like smooth。

 keep decreasing ever decreasing testlon and you know it just seems to work really， really well。Okay。

 which is very interesting， so this is from five years ago， six years ago。And similarly。

 the mind two years later， you know， Ro did more study on this phenomenon like how do you scale these models and they find out that if you。

 let's say， fix a compute budget of this many training flops and then you like vary number of parameters。

 you get this different different points on the testing loss and then if you get this for every you know compute budget。

 you can like just draw a line through them and you realize wow they just don't stop。

 they just keep going， they keep going down and this is kind of the plot that you kind of you produce just by scaling the flops and then。

It going token and they can predict what's the optimal model size， for example。

 for this fl budget and then what's the loss it's going to achieve。

And then it seems to support what people have found before about the scaling。Okay。

 so to summarize why it's a good idea， I give three reasons。

 there are many more other reasons why modeling language is a good idea first is that many tasks are just language modeling。

 everything that you do or most of the things that you do if you think about it。

 including writing your exam on Wednesday is a language modeling problem right if you train a giant language models on this simple objective of next word prediction next to prediction。

 you kind of force the language models to learn about a lot of task at once。😊。

And the third reason is that they kind of scale really well。 Is it a simple recipe， and then。

It just works。 You don't have to think about all the fancy stuff or other kinds of like techniques。

 Just one thing and do it really well。 And then you get good results at the end。And the didn't。Okay。

So。What makes language models work？ So we talked about what they are。

 what they are is a neural network or like even a giant counting table of sequences。

 We talked about why theyre。It's a good idea to do language modeling。

 but language modeling is not exactly a new idea。 It came like decades ago。 people thought about。

 why don why don't we just like model language， But why is it now like this decade or this last couple of years that people realize。

 okay， it's it's a really good thing to do。We already touch on part of the reasons， so for example。

 people realize that if you do scale， they scale really well unlike other things that people have done before。

Language models， you they can do a lot of things when you scale them up and then they realize that if you do next token prediction。

 it's a very nice， convenient multitask learning objective as opposed to you let's say pick multiple data sets and then you kind of deal with the losses's you know that people used to do the idea of a meta learning for multitask learning。

 the idea that you collect multiple task and then you collect train on each task and then you observe the performance and then you update the model kind of like meta gradient where you just update the using the performance of each task to update your model in a particular way。

Here， there' there's none of that。 You're just a simple single objective。

 You train on lots of text and it just works。There are many more ideas that make language models work。

 We'll touch on a a few of them。 This list won't be exhaustive because there are many things that go into kind of the innovations of language models in the last couple years。

 and here we just want to touch on like the key kind of like intuitions on what you make them work。

 what are the key essential things。But， you know， some I argue there are things like missed here。

 You can talk about isolation。 You can talk about data quality and many other things。 But， you know。

 we， we'll go through them if we have time。Okay， let's start with model architecture。

So you probably have heard of this paper， attention is all you need。

It basically introduces architecture called transformformer， and it looks somewhat scary。

 You have a lot of blocks in it， you have lots of arrows in it。

 and then it has gotten so much attention。Yeah pun not intended that Google put up this。

A statement at the top of the paper。 they， they don't usually do that。 If you have a paper。

 you put it out at's it。 But right now they decide to edit the paper at this statement on top。

 you know， like， wow， okay， you， you can use this architecture the diagrams if you want to。

 So it's a very， very popular architecture。 It's a transformer。We won't talk about transformer。

 unfortunately， because I think that there are many， many online resources you will learn about。

 like in engineering classes 2 the4 n36，2，31 n and so on。

 And I just want to talk to you you mostly about like why architectures would matter。

 Like if you have a bad architecture， what kind of happens and why， what。

 what would a good architecture do to fix it， right。

 So they matter in the sense that they shouldn't be a bottleneck to your language modeling problem。

 Okay， if I have a giant。Dala set and a single simple objective。

To just pick the architecture that's the most scalable that doesn't create problems。Okay。

 so we'll gain some intuitions by looking at what could fail if you just use your multilayered perceptron NLP from homework2 to the language modeling problem。

 and then you should go and maybe look up transformer and try to read about how it has a different architecture and that makes it a little bit better and quiz yourself like how it fixes the problems that we're going to show you。

Okay， so if we were to， let's say， do a simple MLP for this problem。Remember again。

 we have this shaped T tensor， which is the input Is。 We're gonna have the。NowT by D tensor。

 which is the embeddings of the vectors of the earth wordss。 You can just， why don't you just put it。

 put MP in the middle， right， You can， you can， you can， you can。

 you can imagine that I can just transform you know， all this as a giant， flat vector， a vector。

 and then into this giant， flat vector of T by V。ANumb of elements。Well。

 the first problem you're gonna see is that your parameter count kind of depends very strongly on the sequence length and the vocabulary size。

 right， So suppose I want to make this model a little bit bigger to handle2 T tensors。 Okay。

 so that means like 2 T words in the inco sequenceequence。

 Then you intuitively have to like increase more and more like neurons in this NLP。

 And then that just directly adds the number of weights that you have to。Add to the model。 Okay。

 so even with just with imagine you you're doing like simple one layer classification problem。

 Then if you take the vectors as like a fact flat vector， then you have T times D times T times V。

 which is on the order of O D V T squared parameters， okay。In practice。

 we want really large sequence length。 So we， like imagine when you use HgBT。

 you fill in a lot of stuff in it。 You don't just want like T equals like 10 or something。

 you give you a whole， you know， homework and ask and solve it for you。

 So that takes like 1 thousand words。And in practice， you also want large vocabulary， right。

 so you want you want a model to know about a lot of tasks， lot of languages， not just English。

 you want to know know about like coding languages， Chinese， you know， Hindi and all that。

So it doesn't scale really well with a long， long sequence of big v cap in transformers。

 what happens is that。You they design architecture such that the parameters don't replicate across the dimensions。

 like it doesn't mostly replicate。 So you have the same set of parameters that kind of like work for every position。

So these are the projections the Q KV that you're gonna see。 They work for every sequence position。

 And then there's only a weak dependence on the vab size。

 So you would only like change the embedding initial embedding matrix and the output kind of like multi multiclass classification layer。

 but everything in between doesn't really like depend on the vocab size。

 It just like a vector of the word， and then you kind of do something to it using tension mechanism and so on。

The second problem is that this network is fixed and there's no dynamic weights。

 So what the NLP is is essentially encoding like like a fixed giant lookup table。

 that means for this particular prefix， this is the next word or this is the distribution of next word。

And with a frozen model， like I train Zopia and don't touch it anymore。

The weights don't have preference for any for different like positions。 What that mean， I mean like。

 suppose you go through， let's say you pick a sequence length and you go through your many。

 many documents。 And then， you know， for different documents， know， for this particular sequence。

 the first position might be the most important for that sequence。

 the last position might the most important。 and so on and so over over。

 like let's say uniformly random about find， you don't really get the NP to learn about， okay。

 what are different positions depending depending on the input。 So you just like for any input。

 I just have this set of weights。 It's fixed。In transformers。

 even a frozen model can create these like quote unquote dynamic weights with an attention mechanism。

For deciding which position in the input sequence is more important。 And that's kind of like a very。

 very essential and crucial idea that makes them work。 right。

 So we're saying if you have something like a rare word in your sequence。

The model can learn to attend to that word more so than the other like fielder words。

 like an and the and but like that kind of words， but NLP does not do that for you natively。

And the third problem is that if you just do an anMP， there's no computation reuse。 So at best。

 we can just like， you know， remember all the sequences that we've seen and then cache the output of it for a particular sequence of a particular length right。

 let's say I've seen the sequence in stock markets crash in investors， something。 Then， you know。

 okay， I can remember it。But if I change， let's say this word and to or。 well， you know。

 you have to redo the entire for pass because you cannot like remember just these， you know。

 activations because these activations， if this' change， this also affects this one。

 So it doesn't help for you to like remember particular position。

 So they all like mingle together with this like giant。A linear layer。In contrast。

 transformers have set up such that they are nice techniques that you can bake into to like reuse a lot of computation。

 So， for example， if you changes word to and to or。

 there are ways for you to like just remember what you compute it so far from this sequence。 Okay。

 so it can reuse a lot of computation。 It's basically it's design in a way that it doesn't。

 it allows you to reuse computation more so than N L。Okay。Cool， again。

 I have not I' told you what the transform is， I'm just throwing out keywords。

 hopefully I can look and look into the architecture a bit more and understand how they work。😊，O。

The next kind of like key idea that makes language models work is this idea of pretrain versus post training。

So previously we let's say in your homework， you dealt with this case of training。

 there's no pre opposedposedse， yous just trainings a data set you train it。

 that's it okay but when you scale it up to like really really big models。

 what you kind of like you have like natural separation of the two stages so in pre training。

The idea is that you want to train like a giant model on a giant amount of text with a simple objective。

 which we talk about as a next token prediction。 here is， here。

 the idea is that you want to make the model generally knowledgeable about many， many things at once。

 So this is the multitask learning stuff we talked about。Right， in this， in this phase。

 you don't care about what the language model is gonna do。

 You just wanted to model whatever scene it sees very， very nicely。 And if you do that really well。

 you do get like somewhat of an intelligent model at the end。

Because you can like complete the tokens across menuing tasks。 And here's， here's a table from a。

openpen source language model called Omo。 It tells you what the training data is。

And what they used So here， if you look at the first like like the category。

 it it' something called DCLM baseline， which is our data set of like web pages and people can kind of like improve them over many techniques we'll talk about in a moment。

 but intuitively it's mostly web pages that you found on internet Okay here they have about 3 trillion tokens of it and 3 billion documents and a lot of words。

And。Here's an example of what you can find in such a， you know， giant data set。

 Here' here here is as Mattta discuss the workings and policies of the site about us。

 Learn more stock overflow， the company。 So as you read more， you realize， okay。

 this is just some text that you crawl from stock overflow。

 And in in particular it is it's a templated text。 It's the things that you will see， you know。

Pretty often， if you just go through different pages of， of stack overflow， you know。

 you could like train a language models on this， but you may not be like that useful。

 But this is one of the pretraining documents that you might see。And here's another， you know。

 random document that you could find。 It's a， what is you saying， it's， it's probably some form of a。

newss article website， you know it says New York Times here it says you know navigation like what's next and homepage and these are like the categories。

 So again this is like an a document you might just craft on internet。And here's another one。

 you know， you you see。I don't know what this is， but like some， some。

 some stuff that text that you see like you can see that it's maybe produced by humans。

 It's somewhat legible。 It's you know， you could， you could like learn and fit the language model on it。

Here's another one， but this one is more useful。 this is like someone writing a question about how they could set up。

Time machine question mark。 And then here are the command that they run。 So this is like， you know。

 to some extent， high quality。 Okay， it tells you， you know what are the words that you might want to come come up with after saying I want to or whatever words you might say after saying。

Googling， you know。Here's an example。There are， so in the the other in more advanced class on language models and CS 36。

 you know， here's a link to that to show you more even more examples。

 is is like randomly sample text from the Internet。

 And you realize they really like are very diverse。

 you'll be surprised how many stuff is on the Internet because we， you know。

 and students we typically spend time on this sites and this side， that side。

 but there's so many things out there that doesn't。You know， intuitively feel like， oh。

 it's on internet。So。What I've shown you is kind of already quote unquote high quality data among all the things that you could find on the Internet。

 So what I'm showing you is this data set called DCLM baseline。 And it， it's like 1。4% of。You know。

 this pool of data from the Common C and Common Crow is just this project that writes a crawler that。

 you know， go to the web pages， go to the links， follow them save every page that you sees into like a giant。

 giant data set and only we say maybe 1% of them is is is is good to produce a baseline data and to cut that down from。

 you know， that many documents to 1。4%。 You do many things like， well， we want to filter out the URL。

 We want to keep only the English we want to like。You know， deuplicate and then we want to， you know。

 even apply another language model let to like look at whether it's high quality text or not。 Okay。

 so it's hard to imagine personally for me how much， how much like bad data is in this like stuff。

So there's a lot of data curation that happens for pre training。

And the nice thing about pre training， and this is a key paper that we will talk about。

 it's called language models or Fu short learners or GP3。

It basically says that if you do have a good data set and you do train a very large model and you do train on a lot of data。

They have this capability called fuel shot In contextex learning。

And this is from also 2020 many years ago。 it basically says， suppose you just， you， you do nothing。

 you do absolutely nothing to make the models， you know， specialize in any tasks。

 You just say here's the internet here here， we're gonna filter it let's train it and see what happens。

 if you throw them on benchmark problems， such as like multiple choice questions。

 summarization questions and see what happens there。 And what they observe is that。

As you increase the parameters in the language model。

 the average performance across 42 benchmarks just keeps going up。 Like。

 you didn't do anything to it。 You just make the little models larger。 You just train on more data。

 There's no task specific training。 There's， there's no like， okay， here's a chemistry problem。

 Please learn about chemistry。 No， just Internet data， okay。

This is you know come out firm preing and then there's another capability called fu learning。

 which is that if you train such a model to a very big size and a very big data set。

 you can just like write a input sequence， write a perfect sequence。

The sequence looks like some form of instruction。 Okay。

 let's say you don to translate from English to French。 and then give it some examples。

 such as like sea order。 you know， I can see French。 but that's， I hopefully that means sea order。

 And then you just kind of like provide examples and then you provide this blank for it to fill in。

 So you have remember a language model is just predicting the mixing token right。

 So this is a perfectly valid input sequence。 And what it and what happens is that if you do this and you you put examples in the input sequence you just knows how to do it by looking at the examples because you have to learn how to。

 you know， maybe examples of English and French text in the training data and you kind of like pattern match。

What you have seen and pattern match that you're trying to formulate a task。

 and then you just like like does it。 It finishes for you。

 So people call it in context learning or with field shot prompting I mean。

 simply showing the examples of the task as part of the input string makes the completions better。

 And that's。Very surprising。 Like if you， if you like think like， think， think about it。 like， why。

 why would it work at all that you just train language model。 It just does the task。

 And it's not just like this translation task。 There's many tasks that。You can do。

 but I'm showing only showing one。Okay， so that's pre training。Yeah， again。

 here we're just like producing like a giant model on a single objective。With a giant text。O。

Post training。Post training is where you want to like start making a model more useful like chatGBT。

 so you now have a big base like this base model that does a lot of things you those a lot of things from the next token prediction objective。

But it's a basically still an autocomplete on steroids， right。

It just follows the patterns that it sees from the text， but it isn't useful because。

If you have autocomp， it doesn't know that whatever you want to give it to it。

 it's it's a task or is it like like a problem， I a coding problem。 It doesn't know any of that。

 You just knows that I want to complete the next token to the best of my knowledge or to the best pattern that matches the between data。

 So's， here's an example。 If you throw the prompt or the input string。

 explainplain the moon landing to a six year old in a few sentences。

What happens is that TPT3 would create more questions like that as opposed to answering the input sentence。

And。If you examine this and you think about， okay， what might happen in the preaching dataset set。

 you can imagine that there could be these websites that just lists a lot of questions that you want to like quiz a student or you can。

 they can be like a lot of like these questions that are collected in an exam or something， right。

 That's the distribution of natural language or you find in know， training set。

 The answer to this question like。Answering why like how the moon landingning works。

May not be as common as like just listing more questions in in in the you know in the data set。

 right， So imagine if we go online， how how often is it that you just find nicely formatted question and answers as opposed to like a bunch of questions cluster together。

 more like the latter， right。Okay， so post traininging is the process of making language models more useful。

 such as following instructions。So instruction following， as I was saying， this is one of the。

Key capabilities you want to induce to a model。 So here we just want to make the completions treat the input string as a question on instruction。

 And this is another key paper we can talk about。 This is from 2022， Also open open A eye。

 So in this paper， they kind of introduced this idea of an R O HF。

The idea there is that you can just collect bunch of the data sets that are like question and answers。

 You can first。Make the model train on that directly。

 So instead of like next token prediction on general Internet documents， you can make it you predict。

 you make the next tokens to be the answers as opposed to more questions。 So you do that directly。

 And then what you can also do is that train get a bunch of humans coming in to label。You know。

 what are good completions for this particular question。 So let's say you get a model to。

 to generate two responses， Both are really bad。 But some of them look more like an answer to the question。

 So they will say， okay， this is a better， This is a better， better answer， better completion。

 And so you can have a bunch of these like。Preference labels。 Do I have slides for this Probably not。

 Okay， okay。You just have a bunch of like preferences from， from the model。 So for example。

 if the model generates four answers， you get， you know， some laborers to come in and say。

 which is better。 And once you get that kind of data。 So question answers and preferences。

 you can string a separate model to like， predict which answers are better。

 So we call that a reward model。 this reward model basically just approximates the human preference。

 Okay， and lastly， you just。Treat the。Language model as。

A policy like like a agent in an R which you have learned in a couple couple weeks back。

 So here we're saying you're gonna have this language model that produces generations。

 And every generation it's just like an action that it does， right，s think of it as that。

 And then for every action， you have a corresponding reward。

 And the reward is that if you produce something that humans prefer more， you know， you get。

 you get reward。 And if it produce something that we don't like as a completion， you get less reward。

And because if you train this reward model from the human preferences。

 you can just make your language model reinforcement learning against that reward model。

 So they have this like three stage training。 So you first fit on instruction following data using next token prediction。

 and then you train a reward model。 and then you kind of fit like a preference learning so。嗯。

The training algorithms。And the generations and the reward things。

 these are all the things that you've learned about。 There's no really like fancy like algorithms。

 like in practice， people， I think they just use the simple things that you have learned about policy gradient methods and then maybe like modifications like there's a baseline to to kind of reduce the variance to the policy gradient。

 But it is what it is。 It is like a simple objective that you kind of learn in the couple of lectures back。

ok。And so once you've done that， you make the language model basically follow instructions。

 so in this case this is the same example from a couple slides back that if you prompt GP3 to produce completions to the first prompt。

 it now gives something that looks like an answer to the question than more so than more questions。

And then same thing there， you know， give write a guide on how I can break into neighbor's house。

 if you just asked the base model to complete it， you might get like。

More description of the problems， more so than answers to the question。 So in this case。

 he says I would like to do it without touching anything。 blah， b， blah， bh， bla， So this。

 this could be like a， like a standard thing like a paragraph that you see on Reddit or something。

 And in this， the response like from instructionivity is more like。An answer to the question that。

The prompt is asking。 So it's treating it as an instruction。

So you might guess that this may not be a good idea to have models answer any kind of question for you。

 and so a different goal， a separate goal in post training is this idea of safety tuning you don't want it to tell you how to break into a house right there are many things you could do in post training so in followinging is one safety tuning is another。

 there are many many other things like reducing memorization you can do make it like more concise。

 more warm， less sycophic like all these things is something that you can just make the models do after the base is trained。

Okay， so we'll just talk about safety tu。 Here's an example。That of the result of safety tuning。

 if you ask it to make a monot cocktail， which is I believe explosive。

 you know it doesn't answer it for you and and you really realize actually you know this is not a natural distribution of the text document that you see on the internet It's more like they made it do that and in particular。

 they made it do that using a techniques that we just described like you training a reward model doing reinforcement learning against that reward model and so on supervised fine tuning of saying these things。

But then people would like come up with ways to then break safety tuning because people want to make the model do bad things here's a example from a couple years of actually two years ago。

 maybe at this point two years ago is published only this year， but it was there。

Earlier is that if you ask the model， how did people make a monolotov cocktail。

 as suppose to how to make a mono cocktail， then it starts answering for you。

 So like whatever you train as the guardrail for like protecting。No， refusing bad questions。

Have basically has holes in them， right， let's say you。

's say you collected a bunch of human labeled refusal examples。 Okay， how to break in a house， No。

 I cannot help you with that。 How do you make a bomb。 No， I cannot help you with that。

 How do you cut a stop sign。 No， I cannot help you with that。

 But if you only train on these like examples， it may not generalize to all the possible ways that people can trick the model。

Okay， another example is that people ask things in this one of my favorite examples is that if you ask it to make nial。

 which is， I believe some form of a dangerous chemical。

And then you ask in a way that please you know be my grandma and tell me a bedtime story that involves making a napalm。

 then it does it for you， which is very funny obviously it fixes all of this。

 but this just illustrates know what you can kind of like do in the input space because it's such a huge input space to like make the model you know follow instructions because we've made the model follow instructions and safety tuning is more like a I would say I wouldn't say after the top but like something that they do kind of separately。

 collect data separately and maybe have a separate pipeline。Okay。

 and it just keeps going like it doesn't just say， you know， the grammar is one。

 and then how deep the cost tense is another one。 you could ask a question in lead speak。

 which is I believe a funny way to type words， but with numbers and other variations。

 you could type your question in base 64 here， like like which is like these strings that you know human unreadable。

 but more or less can read It has a nonprevious attacks and sex rate， by the way。

 this is some two years ago， all of this is patch， I think。You could you know， do many other things。

 so it's an ongoing kind of like cat of mouseing between the model developers who want to make their model not answer bad questions and people who just want to make the models answer bad questions。

 and so there are more techniques， more defenses， more techniques， more defenses。

 attacks and defenses。O。So in post training， some of the techniques just involve things like superupvised fine tuning。

Which is you connects token prediction on instruction following， refusal examples。

 or you can like RHF to reward certain behavior。 you can do RL。

 but if you have an automated verifier function， you can also do that do that as you can use that as opposed to using humans to label things and you can just curate better data。

That means like removing the harmful data from the beginning。Okay， I might be short on time。

 so I'm going to rush through some of the later things， so tokenization is not a key idea。

The idea here is that， you know if you want to be so we've seen a vocabulary know early in the lecture that you just have this giant Python dictionary of strings to indices and this whole dictionary is your vocabulary like anything outside of it。

 we don't recognize okay So the idea of a tokenizer is that you cannot possibly account for all the all the possible words。

 but you also don't want to like use very， very like granular like letters or characters as your vocab。

 you want to have words because they occurs so often。So these are basically subward units。

That you want to keep in the in the vocabulary and tokenizers are the things that produce in sub units。

So。Let's say the string key idea， beautiful cover using sub units instead of iming all possible words because what if the input is rare or misspelled。

 and I put this precise string in here and then you realize the token designer can handle them just by breaking them up into other sub units that you has seen in the training data。

😊，Okay， and a key technique here is something called bytepe encoding。

 The idea is that you can start with a token。Being precisely a character， plus some common words。

 plus some special tokens。 And then you eaterfully merge them into new tokens or。

You new tokens by frequency。 So， for example， if you see that in and put occurs so often together。

 then you just put them into the same same token。 And then you just keep doing that。

 And every time you do emerge， you add one new word to your vocabulary。 And so you keep keep adding。

 keep adding and you just stop until you like， let's say， reach a certain size of your vocabulary。

I can't do justice of tokenization because it's a huge problem it's both like solves a lot of problems it also creates a lot of problems and I encourage you to take a look at this lecture which goes into much more detail for example a lot of the problems that we see with Lamo today is because of tokenization but then we cannot train them without them at this point at least so it's like a very you know you're boring you're also like boring。

Borrowing us like like one piece of a wall to another piece of wall， you fix the problem later on。ok。

Systems， briefly talk about that。So here's an example just illustrate why systems matter。

 So because for most people， for a lot of when I was like learning language models and machine learning。

 system is really an afterthought。 I don't think about， oh， there's GPU， there's memory。 there's。

 you know， like like flops。 I have to think about this sharding。To give you kind of like intuition。

 suppose I have this 70 billion parameter model。 The weights alone already takes 100。

 like with the say 2 Bs per parameter that already takes 140 gigys of memory。

 like I don't believe my laptop or and if your laptop have that much memory， maybe some of you do。

That's like a huge， huge model。 and we haven't even started training it。 it's just like， you know。

s just the weights when you train it， there's activations， there's gradients。

 there's the optimizer states。 the atom first and second movement and this like creates maybe like8 times more memory So that's like1。

12 terabytes of memory and this is only a 7 billion prim model you do have trillions of parameters models these days and a single H 100 GPU only has 80 gigb of memory like how does that make sense Like how do I even it doesn't add up right。

嗯。So I just want to touch on the few key ideas that people do。

The first idea is that you can quantize your models because the models are again。

 at the end of it just giant matrices of numbers， you can just say。

 why don't I represent these floating point numbers using lower position。

 I'm saying let's say if I have four bit quantization or two decoization。

 I'm saying there's only two to the two， which means four possible values with the weights。

 So I have this like spectrum of possible values，I'm just gonna fit them into the bins like with two bits。

 and I'm gonna have like four bins。 And then I'm gonna fill them into the bins。

 let's say using some nearest low loss metric。 And then I'm gonna just like run these weights to the nearest bin so that can reduce the amount of like bits you need for per parameter。

So you know， that's roughly how it works。And I believe today you can go as low as2 bit for inference and4 bit for training。

 but this is really active research， people don't really know。

 I don't think people have really figured out how to do four bit training like large scale pre training and for two bit inference。

 you already really get bad performance like you lose a lot but there is something you can do。

Second idea is that you can just cut things you know shortard things and parallelism and sharding。

 So suppose if you have a model that can fit on one GPU。

 then you can just like split the data into multiple GPUs。

 have them process the data separately and merge results Okay。

 so that's the basic kind of like data parallelism。Like just startingarding a data。

But if your model cannot fit in a single GPU， then you might do， you might cut the model instead。

 there are many， many different ways to cut the models。 And here。

 I'm just gonna show you some quick examples。 You can be like。

 I will cut the layers of the model into different GPUus。

 And then I will have the first GP produce the input and the output for a pass。

 send that to the next GPU。 and it doesn't。 It's very slow， as you can imagine。

 because when the second GPU is doing the computation。 The first GPU might be just waiting。 you know。

 doing nothing。You can also cut the matrices because you know。

 if you think about like how much multiplication work。

 you can cut them and then splitit them into separate motion multiplication of smaller matrices and then combine results off the band right so this is an illustration of how you could cut them maybe columnizers rowwise to get the same result and then you can just put the matrices on different GPUs。

And then next idea is just to be more hardware aware and bright better code。

 like there's what is being what is the bottleneck。 usually is the memory bandwidth。

 So you don't want to like move things between the memory and the actual GPU very often。

 So you should ship all the stuff you need to GP at once。 It does everything at once。 S it back。

 Okay， so kernelron fugen is this idea of combining many small operations that go between memory and compute into one big operation。

Flash attention is an example of that。Okay， I'll skip that。

 So the main things I didn't talk about that make language models work。

Things like test some scaling like if you make a language model say many。

 many things before it produces answer， somehow it does better， you know。

 it's a very interesting behavior。 it's like how humans think if I ask you to predict the token right away。

 the next word right away， you don't get a good answer。

 but if you can just get a scratch pad to write your thoughts down。

 you know you can do better on your exam。There's distillation。

 which is like if you train a big model， there's a small model。

 you can make the small model behave like the big model just by mimicking the big model。

You can use tools， get language models use tools， you can there's a lot of training infrastructure tricks that make work in practice。

 there are many algorithmic innovations like optimizers， architectures， RL， algorithms。

 and you have to think very hard about how to evaluate your language models and then there's also multimodality which I didn't touch on vision。

 audio videos and so on。Okay， finally， I have spent the last two minutes to talk about where we are today。

 So if you learn about all this language model stuff。

 you know what they are roughly on conceptually on a high level。

 you know why it's a good idea to model language just because you can learn many tasks once and it scales really well and you know know you're not heard of some key ideas that it can work right like scaling post training。

 pretraining。Data and RL and all that。And so like， that leads us to today。So this is a slide from。

From from earlier this lecture and in this case， I didn't tell you what how a language model would fit into robotics。

 but a robot would now， for example， take images and language and robot actions all as just individual tokens or words that you can predict in a language model and you see a language model now fits on many。

 many things， not just natural language and that seems to work。And right now， today。

 if you go outside and talk about language models， people kind of assume that you're talking about large language models because these are the things that are。

 you know， like taking the news and like people are these are things that are having a real impact on society。

 We don't really talk about the small language models that you， you know。

 train in this class or the neurotranslation models that you know， you use five years ago。

And because of the industrial realization， these language models are now primarily developed by organizations。

 each with their incentives， like it's very rare to see that like a university like Stanford to just come up with a language model because we just don't have that much compute and money to do it so many developed LLM and sell it as software。

 So you've used TB in Kude and many integrate these language models into products。

 you know you've used cursor， there's something called Lovevo。

 which allowsGB websites and many release them freely like Quin Lama。

 Kimi Deepse for strategic reasons like we don't really know why。

For many I think are we might know why， but like you know people can try and think of why why do you release such a know millions of millions dollars you train them and you kind of just put them in the world。

Like there must be reasons and others release the models just to advance open research。

 there's the Omo models， and then Percy is leading a project called Marinein。

 which is like building these open open open source models。Okay。

 so when you think about these closed models that like open eye or Anthrop ops。

 they are sometimes we also call them frontier models because they are kind of the best they are。

 They are put behind a paid API。 You can access them。 But they are identity trace。 So you know。

 everyone can use them。 But like you have to like show yourself like who are to use them。

 And supposedly， they have some secret songs， right， they， they have special algorithms。

 They have special data systems or inference tricks that makes them better， faster and stronger。

 We just don't know。 like this is what makes it。😊，Interesting， which is that they。

 they produce these objects。 They have papers that。You know， from 2019，2020，2092。

 that roughly tells you how it works， but the precise details we don't know Okay。

 but somehow they just you know， beat humans at coding， which is II competitions at math。

 they have this benchmark for frontier math， which you know I don't even understand the questions that are alone solving them and then they just know a lot of knowledge about the world as well。

 which is the HOE questions， benchmark。 And these are the things that a couple years back， you know。

 really like have changed the scenes of language modeling and。

Like how AI as a feel is moving forward and they have caused international or governmental response andote or maybe panic。

 And this is kind of the situation and people love these models nonetheless。

 like despite their clothes， despite we don't know anything about them。You know， we use them daily。

On the other hand， you have these openweight models。

 these are models that are trained also by companies mostly。

 but they just put up the weights so you can see them， you can like play around with them。

 you know their architecture， you know how much they cost roughly with math。

 and then you can do anything to them。 you can fine tune them using this library called and soft you can run inference on them using this library called the LM you can run RL on them with something called Ver and you can use it for your own startup most time depends on the license。

You can also like try to play with it to remove the safety training。

 You can try to extract training data from these language models and you can like study the architecture。

So these are up there on the on the Hawk face。 They're just on the Internet。Um。

Sometimes you wonder like why they're free， like these take so much to train。And then you realize。

 okay， running these models actually not free because you have to have the GPUus to run them and they could just sell the infrastructure to run these models。

 And these openway models are trying to catch up to the closed frontier models。

 and they are really catching up。 So for example， where recent model called Kmi K2。

 it's supposedly beat open A and Anthrop closed models on certain benchmarks。And for these。

 while the weights of the models are open， you don't really know anything about the data or the compute or the algorithms that really goes behind the scenes。

 they are just you know hidden and then， but you're fine with it because the models are available that because that means you can like put it on like a workstation on your laptop or something and random them play with with them。

Okay， lastly， open social model， you have everything's open， you have training data algorithms。

 weights and code， and they're mostly academics so far。 So these are relatively small models toyish。

 though they're getting comparative to the older generation frontier models。

 but these are the models that really allow you to do a lot more things。

 because you can now know how they're trained， what data they're used and so on。😊，Okay。

 yeah there are two more slides， but yeah can I can end it here。

 but yeah it's starting to create a concern about AI safety these models are getting so good。

 they know how hot computers they can create bioweapons they can do coding they can do forecasting and then people to the point where people would write books that says if anyone builds even more powerful models everyone would die know that kind of situation So that's kind of where we are today and there are a lot of problems that you could we didn't even get to talk about with these language models。

😊。

![](img/149d190c2ff6f22ac426057c1ba8d500_3.png)

But yeah， that's for the lecture。

![](img/149d190c2ff6f22ac426057c1ba8d500_5.png)
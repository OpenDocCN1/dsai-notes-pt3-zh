# CMU《高级自然语言处理｜CMU CS 11-711 Advanced NLP Spring 2025》中英字幕（claude-3.7-s - P9：-09-(9)_ Fine-tuning.zh_en - GPT中英字幕课程资源 - BV1nYVHz7Eoa

Ver。And today we're going to be talking about fine tuning。And there's several interesting。

Things to go over with fine tuning。So first I wanted to just recap。

 so in lecture six we talked about pre training。And the basic idea with pre training was to take some data。

Run the pre training。Minimize the pre traininging objective。 and then you get this。Base model。No。😔。

We talked about different ways of。That you could adapt these base models to tasks in different ways。

So one way is through prompting and this was in lecture 8。

And so here the paradigm is you take a base model。 you want it to perform a particular task。

 So you describe the task in the prompt and also provide it with some task example。

You could then get the model to perform different tasks by writing different prompts。

Today we're going to talk about the other paradigm for adapting a model to tasks。

 which is fine tuning。So here and we'll go through the details。

 here you have some task relevant data。So let's say we want to make a translation model。

 Then we would collect。For example， these paired sentences of one language and another。

And then we'll apply this fine tuning procedure where we again minimize some loss and we'll see it in a bit。

And then that gives you a model which is specialized for the task。

We'll also talk about this kind of trick you can do。

 which is you can train a model to just perform multiple tasks。

 so that'll be called instruction tuning and you'll get what's called an instruction following model which can you can instruct it to do many different tasks so kind of clever。

Clever trick that we'll see。And so today we'll go over four different things。

As with many of these lectures， it is my first time giving them。

 but I think we should be able to get through all of them in today's lecture。Again。

 we're just going over the kind of basics of them so that you've seen them and all of these ideas are very relevant to。

You know。NLP today as well as potentially your projects。

 so hopefully you learn a lot of useful things today。So in particular。

 I'll go over the basics to find tuning， I'll go over instruction tuning。I'll briefly introduce。

Ideas for what's called knowledge distillation and talk about how it relates to things like instruction tuning。

And then briefly at the end， I'll talk about one of the main methods for doing efficient fun tuning。

You'll actually see this in a lot of different fine tuning code bases nowadays。

 and you might even use it a lot in practice if you don't have a lot of computational resources like multiple GPUs。

Okay， so first， I'm going to go through standard language model fine tuning and talk about some of the effects of fine tuning。

 why you would want to do it。So in standard language model fine tuning。

 the idea is we start with this pretrain model， we'll denote it as P theta of y given x。

And now we collect a data set。And suppose our data has both inputs and outputs。

 so the inputs will be X and the outputs will be y。And now we。

Optimize the following loss and you probably recognize it。

It's essentially the same loss that we use for pre training， we now use it for fine tuning。

So here it's saying that you go over your data。And for each different example， you minimize this。

Objective here， or you could have this as a loss function。

And the objective says that the model should learn to predict the next token in the output sequence。

So can anyone tell me what this objective is called？Or what this optimization。Is called。啊。Yeah。

 exactly so it's called maximum likelihood estimation and then the loss function that you minimize。

Ends up being this cross entropy loss。And so this is the same idea that we've seen now in several lectures。

In lecture three， I talked about this maximum likelihood estimation and cross centropi loss。

In the context of these very simple bygram models。We also saw it come up when I was talking about the recurrent neural networks。

And we talked about it in pre training， it's the same kind of next token prediction objective they use for pre training。

Now we're just going over our data set that we've collected and applying the next token prediction loss to the output sequences。

So。In summary， and we'll look at a few examples and then I'll show a code example as well to make this very concrete。

But first， I want to just stay abstract for a second。And so again。

 fine tuning is some procedure that takes in your pretrain model， takes in some data。

 and then takes in some loss function。And in the case of language modeling。

 we have a pre trained language model。We have this paired data and we use this crosscenttrouls。

So although I'll talk about language models a lot because that is the technique that's used widely in natural language processing today。

The idea of fine tuning isn't anything specific to language models。For example。

 you can fine tune a BRT model， which is a mask language model。

You can also use different loss functions， you don't necessarily have to use this cross entropy loss。

And you'll see fine tuning come up in other contexts。

 like you could fine tune image classification models and things like that。But aside from the slide。

 we'll mostly focus on language models。Because currently that is what's used a lot for advanced NLP。

Okay， so any questions about this， and then we'll see some concrete examples。

 So if the question is about like concrete examples， we'll see this。O。So。😊。

Just to give a sense of some different tasks and some actual training data。One example is。

 let's say you want to do summarization， then your input X might be some paper。

And your output might be an abstract。Pretty useful if you can do this。And you can actually go on。

 you know online and find data sets for this， here's one where they collected 300。

000 different examples。And then here again， you have the string of the entire paper。

And then you would have the abstract and you fine tune the model to generate。

The abstract given the article。

![](img/67431f0f3726bc2694d1bd200dbf1b83_1.png)

Okay， and then again， in case you haven't seen this。嗯。



![](img/67431f0f3726bc2694d1bd200dbf1b83_3.png)

Cite before or just let's just take a look at what's here。

 you could again look for various data sets for the tasks that you're interested in and there's a chance that maybe someone has a data set here。

And this is actually where I took the screenshot from。So。Yeah， that's an example。



![](img/67431f0f3726bc2694d1bd200dbf1b83_5.png)

Another example is， let's say you want to do problem solving， like solve math problems。Then again。

 you could put it into this form where now your input X will be some string which is the problem。

And your output Y will be the solution。Okay， so there's also data sets for this。

 a really famous one is called。Unfortunately， it's called the math data set， MAH。

 all capital letters。And they have a training set of。7，500 examples。

So one thing you could do is you could take a language model and then fine tune it on this training data set。

And then hopefully it's a bit better。Solving these kinds of math problems。



![](img/67431f0f3726bc2694d1bd200dbf1b83_7.png)

This is an interesting example， so this one is a bit more general in some sense。

You could imagine your input X just being some type of prompt。And then the output is a response。

 so imagine you have a chat bot。So you could see this data set here has 2900，000 examples。

And you could see that the inputs here。Are kind of different。

 They're not necessarily like math problems or summarization。This one says。

 how does the sentence end， whereas this one says， write a sentence。Not in English。

And then you have a response here。So we'll actually talk about this later。

 this is kind of getting at this instruction tuning idea。But again。

 you can find these data sets on this website and if you haven't seen them before。

 look through them to yeah get a sense of different kinds of data that。



![](img/67431f0f3726bc2694d1bd200dbf1b83_9.png)

People fine tune their models on。嗯。So then， yeah， there's a really simple code example I put together in the。

In the course code repository。

![](img/67431f0f3726bc2694d1bd200dbf1b83_11.png)

And so basically what it does is it solves the usual task in this class， which is generate names。



![](img/67431f0f3726bc2694d1bd200dbf1b83_13.png)

So。

![](img/67431f0f3726bc2694d1bd200dbf1b83_15.png)

Here we again start with this name data set。And then here it's starting with this really small language model。



![](img/67431f0f3726bc2694d1bd200dbf1b83_17.png)

So I actually ran this on my MacBook and did the training， did the fine tuning on my MacBook。

But the idea is， yeah， now we're starting from a free train model。

 whereas in the previous code examples， you know， we are starting with like a transformer or R&N just from scratch。



![](img/67431f0f3726bc2694d1bd200dbf1b83_19.png)

And then there's two things that I had to do here， one is you have to add in。These special tokens。

 the vocabulary。So this one will be to。UDo padding so I've talked about that before。

 if you have variable length sequences in the batch。

 then you have to kind of pad the extra positions。And then this is maybe not strictly necessary。

 but I just added in this。Start of a sequence token。



![](img/67431f0f3726bc2694d1bd200dbf1b83_21.png)

Okay， and then since we're working with a pretrain model。

 we have to actually resize the model's embedding layer so that it adds these to additional tokens。

Now， here， I maybe won't go through the， the details here， but I mean， there's not much code here。

 I'm just implementing these like pi torch。Data sets and data loaders。

So it's taking in the names data set。Here it's adding in the BOS token and end of sequence token。

And then this is forming a batch。 And you can see here， it's like。

Using the built in functionality from hugging face to take care of the。Padding。



![](img/67431f0f3726bc2694d1bd200dbf1b83_23.png)

So now we have different data sets and you can see what a batch looks like。



![](img/67431f0f3726bc2694d1bd200dbf1b83_25.png)

So one interesting thing here is。You can see some of these names are。



![](img/67431f0f3726bc2694d1bd200dbf1b83_27.png)

You know， like four characters long。

![](img/67431f0f3726bc2694d1bd200dbf1b83_29.png)

And so when we were using the character level model。Sorry， eight characters long。

 so when we're using the character level model， the sequences would be longer。

But now we're using a model that has been trained with the by pair encoding。

So you could see that the names are typically like two or three。

Tokens long because now you have these subboards。

![](img/67431f0f3726bc2694d1bd200dbf1b83_31.png)

And then here's just like how the exactly how the data is formatted。



![](img/67431f0f3726bc2694d1bd200dbf1b83_33.png)

So。So， there you go。And then the training loop is。Pretty similar to the ones we've been looking at。

 and this is all it comes down to， you loop over your training set。You get the。Inputs。

 and you have to set the attention mask。嗯。And then you also give the labels。

And then this is using hugging face。 So it'll actually take care of， like。

At least I believe it does of shifting the labels。And then you。Yeah， compute the loss again。

 hugging face has this loss computation kind of built in。And then do the optimization。



![](img/67431f0f3726bc2694d1bd200dbf1b83_35.png)

Okay， so it did take like a little bit of time to run a full epoch on the laptop。



![](img/67431f0f3726bc2694d1bd200dbf1b83_37.png)

But you can get a model here and then you can generate some names with it。

So that's like a very simple fine tuning loop。

![](img/67431f0f3726bc2694d1bd200dbf1b83_39.png)

And I also put in here， oh， and yeah， you can run it yourself。



![](img/67431f0f3726bc2694d1bd200dbf1b83_41.png)

I also put in here an example from the Huging F Transformers library。

So some people actually still use the script， you know。

 for like research purposes or fine tuning purposes。



![](img/67431f0f3726bc2694d1bd200dbf1b83_43.png)

And if you look at this one， the code is a lot longer。



![](img/67431f0f3726bc2694d1bd200dbf1b83_45.png)

So they have a ton of different options。嗯。你。Yeah， they have options for also like parallelizing the model and things like that。

And dealing with data sets。 So there's a ton of setup code。But then ultimately。

 these fine tuning scripts always have this same kind of main loop that we saw in the very simple example。

So here's where it's saying， okay， I'm going to iterate over each batch in the data letter。

I'm going to do the forward pass， compute the loss。And then do the back propagation。Okay。

 and there's a bunch of extras added in like this can help you parallelize across like multiple devices and things like that。

But ultimately， you'll see this like core training loop in part of any scripts。

What script so essentially we are trying to play it in such a way that we predict the next token right。

 so how is it exactly different from pre painting because even in pre training Ifield doing the next total prediction task the input is a sentence。

And the target is sentenced like shifted by months again。Yeah， exactly。

 So the language models are fairly simple in the sense that。You pretty much always you know。

 in standard case， use this next token prediction objective or cross entropy loss。

Whether you're pre traininging or whether you're fine tuning。

The only difference with fine tuning is that you start with a language model that has been pretrained。

So you start with this model that is already pretty good。And then on your smaller data set。

 you optimize the loss。Yeah。嗯哼。😊，Could you please that part in the core where you set the beginning of sentence and par？



![](img/67431f0f3726bc2694d1bd200dbf1b83_47.png)

MYeah。Oops。It just like its just slightly above us so just like a couple people like a couple cells down that you actually printed out just yeah over here just why is there apparent token after the end of text？



![](img/67431f0f3726bc2694d1bd200dbf1b83_49.png)

![](img/67431f0f3726bc2694d1bd200dbf1b83_50.png)

Yeah， so this was looking at a batch and so the idea is that some names are longer than this one。

And then so when you put it into a matrix， you have to fill in the extra slots， yeah。嗯，所几个。

The output is a sentence。 iss no sentence。 How to handle the。If诶你 number不。嗯最 questionなす。

Oh我 the categories about。Say it again if it's the output is a sentence and say10 word of sentence。

of the true label of the the model just return the。8， there have eight word sentences。

 then have to calculate。Oh yeah， so at training time， what you do is you。



![](img/67431f0f3726bc2694d1bd200dbf1b83_52.png)

You give the model or let me actually show it in the in the formula and talk through it。



![](img/67431f0f3726bc2694d1bd200dbf1b83_54.png)

So。At training time， you take。Full sequence from your dataset。And then at each time step。

 you give the model the true prefix， and then you just have it predict the next token。

 And then for the next step， you give it the true。Prefix you plus one token and have it predict the next token。

Yeah， so。So you don't have to worry about this potential mismatch in the lengths because you're always using just the data from the training corpus。

I questions during so our organizer work split a word into subs right to do by and。

So once the model has generated the output， I'm talking about the inference syn。

 how do we know when to split two consecutive tokens that could belong to one single word and when not to split the tokens and rather assume that there is a space and those tokens are two separate words。

 how do we design them？So I guess your language model has。A vocabulary。

And it's learned different probabilities。 So you just have the model predict。

Like what is the probable next token or you sample from the distribution？

And so let's say you have a word that is split into two different subwords。Well。

 after the model has generated the first subboard。Then as long as it's been trained。

 then the model should know that the probable next token is like the second part of the subward。

So yeah， you just， you don't really have to worry about。That aspect of it。

 So let's say the model predicts to tokens considerably walk and I How do we know whether it it's supposed to be a single word walking or it's supposed to be walk and and G2 separate Oh。

 okay， yeah， because there's also tokens corresponding to white space。

So if you remember when we talked about the tokenization。

You can basically represent entire strings using UniIode or using these like UTF8 bytes。And so。

 that representation includes。White space as well。And so white space could be its own token。

 it could be included in a subward。嗯。And so， it's handled by the。Use of PP。Yeah。嗯。😊。

SoW did you add those two embeddings？

![](img/67431f0f3726bc2694d1bd200dbf1b83_56.png)

Why were they necessary？Yeah， so。

![](img/67431f0f3726bc2694d1bd200dbf1b83_58.png)

One is。So one is the patting token。And so the padding token is important if you're fine tuning model。



![](img/67431f0f3726bc2694d1bd200dbf1b83_60.png)

Because you。

![](img/67431f0f3726bc2694d1bd200dbf1b83_62.png)

要。TheyHave to form these batches， and the batches are of variable length。

And then you want some consistent token so that， you know， to not apply the loss on these extra。

Positions。你睇睇过生多你。How we it that the pre train model didn't have that to。

 why was it necessary for us to add it manually？

![](img/67431f0f3726bc2694d1bd200dbf1b83_64.png)

Yeah， so it'll just， it'll vary based on how the model was trained。

Here what I did is look at the tokenizer and there's just。

There's a special location in these hugging faces tokenizer called Pa IDd。And since it wasn't set。

 I added in my own pad token， there might actually be one somewhere in the vocabulary it just。

Wasn't set in the tokenizer。 So I added one in Yeah， but during their training， they must have had。嗯。

Well， okay， maybe we're so during pre training， you can have fixed length chunks of documents and sometimes you don't even need padding for pre training。

Because you have these extremely long sequences and you just take chunks of them and then they're always the same length。

 yeah。So sometimes the pretrain model won't have the pad and coken， yeah。Mmhm。😊。



![](img/67431f0f3726bc2694d1bd200dbf1b83_66.png)

Okay， cool and。Yeah， great questions。So。

![](img/67431f0f3726bc2694d1bd200dbf1b83_68.png)

So that's that。 And then。Yeah， so I believe in the recitation section。

We'll go through in detail in more detail how to fine tuna model with the hugging face code。

So if you're not familiar with it or you just want a refresher。

 there'll be a whole recitation section on this。

![](img/67431f0f3726bc2694d1bd200dbf1b83_70.png)

There's also these， I'm calling them no code， fine tuning libraries。

Where they'll have different commands like fine tune。

 and you give it a data set in a particular format。Two popular ones are called Lama factory and。

Exxelotl。嗯。So you could take a look at these。 They have a lot of different functionality。 Of course。

 they will be very abstracted away。 So if you need to。You know。

 go down and do any modifications and that gets more difficult。

But if you want to do just kind of standard fine tuning。

 then some people find these kinds of libraries kind of useful。



![](img/67431f0f3726bc2694d1bd200dbf1b83_72.png)

Okay， so now let me just talk about a few effects of fine tuning。So one is there's this。

Question of like， why do we use a pretrain model in the first place and intuitively it seems like a good idea。

嗯。One like concrete thing you could say is that typically the model becomes more data efficient。

So specifically here what this is showing is。If you have a model that is trained from scratch and now you're fine tuning it on some data set。

Then this is showing the size of the data set that you're fine tuning it on。

You could have a data set with 100 examples， 200， 1，000， 10，000。

And then this is showing the performance and you can see that if you train from scratch。

 then it actually requires a lot of examples， roughly like 10。

000 to reach this performance level of 10%， whatever that means。

Whereas these two are two different strategies for pretrain models。

And you can see that this one only requires 2，000 examples。

And then this one actually only requires like 130 examples to reach the same performance。

I'll talk about what those are in a second， it's actually not that important because it's kind of an older paper。

But then you can also see that the absolute performance that you get。

Given the amount of data you had， you have is just better。

So you would have to go and collect more data to reach the performance that you get by pre training and then fine tuning。

I was curious why is this super the CM supervised approach better as they have like no labels to validate their own time Yeah yeah。

 so this was I picked this paper because this was actually before GP I believe this was like one of the earliest papers to do language model fine tuning。

sorry， pre training， plus fine tuning。So the method like the experiment setups are going to be a bit different than what you'd see today。

 but what they did， I believe， supervised is just taking the pretrain model and fine tuning it on the XY examples。

The semi supervised is they have the X Y examples， but then they also add in additional data that's like relevant to the domain。

So let's say you're doing like movie reviews， then you could have your inputs and outputs and then also throw in a bunch of like。

I don't know， movie related data。 Yeah， it is just more data Yeah， yeah。

 so that's what it means by semi supervised。And so this idea is kind of， yeah， I mean。

 it's still present in。In this paradigm of pre training and then fine tuning。

 your model kind of becomes more data efficient。嗯。So this one is a bit maybe mathematical。

 but I personally think it's pretty interesting。So one way you could think about this is that this fine tuning is taking this pretrain model。

 which has this really kind of general distribution over the pre traininging data。

And it's somehow narrowing the distribution to the data set that you're fine tuning on。

And so if you remember back to lecture three。I talked about how the maximum likelihood objective。

Corresponds to。Essentially， fitting a distribution。In particular。

Minimizing the kL divergence between some data distribution and the distribution that your model represents。

And if you remember the data distribution is basically determined by。The data set。

 it's viewed as a sample from data distribution。So then as we've discussed and as people ask。

 we use the exact same objective for fine tuning。So we can also think of this as fitting a distribution。

So this notation just means we start with some initial model。And now we're。

Minimizing the kale divergence between our model and our fine tuning data distribution。

 So this would be represented by your fine tuning data set。

And what you can see is that like usually your pre traininging data set is like trillions of tokens。

 you know， from the internet。And then maybe you're just fine tuning on like a math problem solving data。

And so the distribution is becoming kind of narrower。And。So that could be a， yeah， a useful way of。

Kind of thinking about what's happening during fine tuning。嗯。

So let me talk about a few implications of this， then maybe I'll pause for questions。

So like with this understanding， you can kind of， you know， reason through the implications。

So one implication is， let's say you fine tune a model for summarization。Well， then in some sense。

 you've narrowed the model's distribution to。You know， like summarization， inputs and outputs。

And so it won't necessarily work well on some other task like translation。

Whereas a general pre train model， the same model could work well on multiple tasks。Similarly。

 if you have like specific formatting in your fine tuning。Well。

 then now the model has been like fit to this particular。Distribution that has the formatting。

And so if you change the formatting， then the model might not work well。So like in the Fing example。

 we saw。I formatted all the examples with this like very specific format， like beginning of sentence。

Name and of sentence。And if you kind of change that when you're generating。嗯。

It'll be kind of out of distribution and might not work well。Also。You know if you fine tune a model。

 then it's not necessarily guaranteed that it retains the ability to do this fu shot learning。

Because again， you might be fine tuning it on these specific input and output examples。

 and the model can kind of forget the few shot learning capability that the pretrain model has。

So yeah， any questions on those？O。So that's it for the fine tuning basics and now I'm going to go to instruction tuning and so this is something that is incredibly popular now and。

Most language models that you'll use nowadays。Will have a。Base version。

 which is the fine tuned model。 sorry， the pretrain model。

 and then they'll have an instruction tuned version that has undergone this instruction tuning。

Procedure。So here the basic idea is kind of to use this observation or this kind of trick。

Which is we want to fine tune in a model to perform multiple tasks。

And the insight is that many tasks in natural language processing。Can be formulated as follows。

 We have some instruction。That describes what the task is。

Then we give a model an input from the task and an output from the task。

So an example is here we could view this as an instruction， and it's basically describing the task。

 it's saying that this task is translation into English。And then we give it an input in Japanese。

And then it knows what tests to perform and gives a translation。

And so then the insight is that you don't have to just train a model for one task at a time。

 You could just have an entire data set of these different instructions。

And multiple tasks and just fine tune a model on a data set that looks like this。

So that's really the key idea behind what is called instruction tuning。Um，And there's been。You know。

 hundreds who maybe thousands of papers about this。

 So there's a lot of different variations that people have tried。So one question is。

 where do you get your instructions from？So I'll show a few examples。

 we'll see an example where you kind of have a hard coded template to produce the instruction。

You could， of course， have humans， human labelers like。Create these instructions。

You could even have models generate the instructions， and I'll show you an example of that。

And then similarly， you could determine where do you get your inputs and where do you get your outputs from？

So we'll see an example next where you just。Take an existing data set like a translation data set and just put it into this instruction tuning format。

You could again have humans specifically， right。You know， inputs。Or have models generate them。

And so we'll see an example of。Some of these combinations。

And then another big thing is people try to develop these instruction tuning data sets for particular domains。

So one is you might want some just general data set that tries to cover all the tasks possible。

Or you might think about like， okay， for just code tasks。

 let's come up with an instruction tuning data set。Or for just math tasks。

Or one that we'll go into in a bit more detail is if you want to build a kind of good chat bot。嗯。😊。

it's this kind of like people internal like， for example。

 chat boxes like agents where like you have a regular chat box that you turn to like the agent or like the specific。

Chat Bob brought the website， for example， was just like this is similar to the versus like what they friend。

So yeah， that's a good question， so we'll go over so we have a separate lecture on agents。

And there's different definitions of agents。 But yeah， usually you start。

 So with a language model agent， you start with a model that has been。General instruction tuned。

 so it can take like different。Instructions， and then you might have different prompts that say。

 like， okay， given this。Htl page， like determine what I should do next or something。

 and then it says what it should do next。So in some sense。

 it's following an instruction which says like choose in action for what to do next。

And then there's some other extra things that。What people typically call agents have。

 they usually have some kind of environment where they can make these like tool calls like they might have a browser available to them and they can like call it web browser and things like that。

But yeah， at its core， you'll start with one of these kind of general purpose language models。Okay。

 so yeah let's take a look at these and part of it is a kind of history lesson too。

 so the first two examples are yeah maybe two of the initial instruction tuning papers。

 at least the ones that kind of got very popular。So this one was from Google。

 and here they started out with 62 different NLP data sets。And I guess at the time， you know。

 a large portion of the community would kind of work on one data at a time。

So they took all of the data sets available in NLP。

And then formatted it as an instruction following data set。So for example。

 here's like a common sense reasoning data set。On the right here is a translation data set。

 they have sentiment analysis， co reference resolution， and so on。

And then for each different data set， they manually wrote。

Some number of different templates that created an instruction。So here is， again。

 these are like tasks specific。 but for this task， they came up with like four different ways of kind of。

Having an instruction for the task。And then again， their inputs and their outputs are just taken from the data sets。

嗯。So yeah， this was the basic idea behind this method called flan。I forgot what it stands for。

 but maybe someone can look it up。And really， the key finding of these early papers was that。

If you do the instruction tuning， the model can A perform usually perform better than if you just fine tune on one task so there's some transfer between the tasks。

But very importantly， it can actually solve tasks that weren't in its training data。

So here what they did is they held out some tasks and then tested the model on one of these heldout tasks。

And you could see that their model actually did better than。These kind of state of the art。

 just pretrain models。That were're using the fuia prompting。

And you could kind of demonstrate this ability to generalize to unseen tasks using different kinds of plots。

 this is just one of them。But that was kind of the key finding。

 one that you could have a single model that performs multiple。

 and it could even perform tasks that weren't in its training data。So then， yeah。

 here's some other cases。This is a data set called supernatural Inions。

And the original data set was called natural instructions。

And I just wanted to call it out because natural instructions was。From this paper by Suwarrup Mira。

And this one was actually from like six months before the Google paper they got really famous。

 so it is kind of cool to look back and try to see like what were the really early papers。

But anyways。They later scaled up natural instructions and had this time， they had humans。

Come up with many different like task examples。So basically。

 they came up with these higher level task categories。

And then I think they did it through GitHub where like anyone could contribute and they had something like 88 contributors。

And came up with， oh， I forgot to put the number here， but you know。

 it came up with this huge instruction tuning data set。That was just created by different people。

So then another interesting finding was that you don't necessarily have to have humans create the instructions。

The instruction tuning data， you can also just have really good language models created。

So this was one of the， oh， sorry， I forgot to update those。嗯。But the link is on the course page。

 So this is a paper called self Instruct。And the idea here is you start with some small seed data set。

I think they used 175 examples。Then you could use these examples to prompt a language model。

And just have it generate new data。And then they have a few other steps after like they try to filter it down and various things。

 and you could imagine that since this paper there's been you know many different people looking into different techniques。

 but the core kind of idea is that at some point they have a language model that is just generating new data。

And then of course， you can iterate the procedure where you use this generated data to reprompt the model and you can kind of balance out the data set to make sure。

You know， you have a good balance of。Different kinds。

So the key benefit here is that now you're not bottlenecked by the human ability to create instructions。

 so part of it was showing that you can scale up to this kind of large。Instruction tuning data set。

And so here's some examples that were generated like this one is given an address in city come up with the zip code。

It gives some address in city and then has a zip code。This one's kind of interesting。

 you can have you know tasks that。嗯。 like it's hard to distinguish between what's the instruction and what's the input。

 so it just leaves the input。Empty and then says to generate some code。嗯。

Can anyone think of some potential limitation with this paradigm？Well， one question I have is like。

 is this actual zip code for San Francisco？嗯m。😊，It's。

This is any but biass are going to explode as you repeat the self construction because they don't have any alternate point of truth。

Tecniphone that is like。Minute errors might creepen at some points and they will amplify each other out like that first one thing and last time thinking about like you know the probability distribution because you're going getting out if have like a quality metric and have like a probability distribution so well some examples are really high quality like like you could it like a PhD promote those examples and a few other ones are really low output qualities like probably a grade school won give those out。

Possibility is that like， you know if one end of this probability spectrum dominance like I have more grade slower level outputs than PhD outputs in the self install data set。

 that can lead towards like a large scale worsening of net output as I sort of find you upon increasingly worse examples。

That's yeah， yeah， yeah。 So one， you could have this。 Well， so part of it is， yeah。

 ultimately using a language model。 And so one is the language model might be imperfect。

So one thing is we don't necessarily know whether the outputs are correct or not。

 like you might have just invented this zip code here。

And then if you were to feed this back into the prompt。

 then it might have some kind of self amplifying behavior。

So you really have to be careful about having。Some way of you have to either just trust the language model or you have to add in some you know filtering step if you really care about having。

 you know， correct and high quality outputs。So that's really it in terms of the key idea behind instruction tuning。

So嗯。The difference between Str tuning and the fine tuning so as the start is that these fine tune models have a broader range of capabilities。

Yeah， so。Yeah， I guess fine tuning， maybe you could view it as， it's just。

It's just like the procedure of minimizing a loss function with some data set and some model。

And then instruction tuning would be a particular type of fine tuning where you format the data in this way。

And yeah， the finding is that if you format。in this way。

 then you can get a model that kind of performs well on multiple tasks。Do article like。

 what's the difference between being？Pre training and simply having like a really。

 really good initialization。嗯。So ultimately。I mean。

 one way to look at it is you could look at the code。

And the code is just initializing the model and the model is some set of parameters。

 So pre training ultimately is just choosing some initialization。That was like my follow question is。

So the fine paradigm is about taking this period just like you know sort of narrowing the distribution per se。

 so I'm curious about like you know have an experiments were conducted when like you first you train on a small flash as data said and then you allow it to explode the problem distribution by general retaining and then once again you try to narrow the example down by fine and another。

Data set like have experiments like this been conducted because so means youre like pre trend fine tune pre trend sort sort tune e。

Yeah， I'm not aware of that that specific order。 I would say that people。

 people kind of use this intuition of narrowing the distribution and。One other way， which is。

Typically nowadays the pre training will be done in multiple phases。

 so the first phase will just be on general data from the web。

And then towards the end of pre training， they'll actually put in some task specific data。

 or they'll use really high quality filtering。So that the model starts kind of narrowing its distribution to a higher quality area。

 and then they'll finally do the instruction tuning。嗯。So it's not exactly what you ask， but yeah。

 maybe it's an example where you kind of use this intuition。嗯。

So chat language models with which we interact are trained this way。Yeah。

 so we'll get to chat so chat is is， yeah， we'll talk about chat in a second。嗯。Yes， yeah， yeah。

 and then I'll talk about chat in a second with chat。

Distinction between an instruction and output input kind of gets blurred。

 it's just like an input prompt， but yeah。嗯哼。😊，You've done the example using the during region very accuracy parent。

Not in the case some of them have that kind matter so is it because of the data or the way it is pretrained and making certain of thank？

Yeah， so。So ultimately，s it's important to evaluate the model on some kind of third party evaluation data that's really high quality。

And so then even if your instruction tuning data is kind of noisy and has errors in it。

Then people will say， oh， well， you know， at the end of the day。

 it actually performs well on these evaluation tasks。In practice。

 I would say that it's still important to have very high quality instruction data。

So if you look at the Lama3 paper， for example， they mentioned that they hire human annotators to create you know a large portion of their instruction toning data that's likely because they did a bunch of experiments and found that you know。

 still having the high quality。Yeah， data can have an impact。Okay。So yeah。

 so I wanted to specifically mention chat。So。This is a term I just came up with while creating the lecture。

 but there is a slight difference between the fine tuning that you do for chat and instruction tuning。

 but people still refer to this as instruction tuning。But I want to just like。

Show you what the differences are。So again， ultimately， when we have a chat model。

 we format the chat as a sequence of tokens。So in lecture 8。

 we talked about this where you have this system prompt。And then you have this alternating。

Conversation between some user and some assistant。So there's a couple differences。

 one is now you have this system prompt。That wasn't necessarily in the instruction tuning data sets。

The other is that now you have multiple turns， so most of these instruction tuning data sets are you know just some single input and some output。

嗯。And then。嗯。The third thing is that if you think about having a conversation with like chat GT。

 then you don't necessarily say， okay， here's my instruction， here's the input。

 you kind of just say like do this and somewhere in there is the input and the instruction。So。Yeah。

 the first difference was the system prompts and so if we look at data sets that were created to fine tune some of the chat models。

Some of them specifically think about creating the system prompts。Here's one I mentioned from before。

And what they did here is pretty simple。 They just wrote 16 different。System prompts。

You can see like， they vary a bit。And then they append the kind of instruction tuning data。嗯。😊，So。

And then here they also use the idea of just getting outputs from a model。

 so yeah given this they would just pass it to GP4 and do this and now they have this massive data set。

If we look at the Lama3 paper， so first of all， they don't mention all of the details。

 but they do mention system prompts a lot。So you can imagine that as they're designing their their model。

 they， yeah， this is something they're thinking about。

One thing they did mention is they did hire humans in some cases to write the system prompts。

 and you can see that these are a bit more sophisticated than ones on the previous slide。

And then this is something we'll talk about when we talk about the agents。

But agents will typically have access to different tools。

And so they also specifically put information in the system prompt for like what tools or what environments the language model has access to。

And you could imagine that like the model might solve a problem differently if it knows it has access to wool from alpha versus if that wasn't in the system prompt。

So then the other difference is， again， the multi turn nature。

And also just having kind of natural conversations。

So there's been a couple efforts to collect these multiter conversations。

I think one of the earliest ones was this one called Lms 1 million。

And so basically one of the early models that was trained， I think， by Stanford。

They put it up on some public service and said， you know。

 check the box if it's okay if we save the conversations。

And they collected a 1 million examples of actual chats。

And you can see up here is this category called turn， and it goes from 1 to 22。

Most of them turn out to be fairly short， I think on average the length is two。嗯。

Or maybe this is the length， yeah， sorry， this， yeah， anyways。

But you can see here that they do have these multi turn conversations。

And they're not necessarily formatted into this kind of strict instruction input format。Okay。

 so nowadays you might use data like this and add in the system prompts。And then turn them into。嗯。

Kind of sequence of tokens and then fine tune your model on it and you can get。Some basic。下吧。

So any questions here？嗯哼。😊，嗯哼。😊，Yeah。Yeah， that's a good question。

 I don't know if I have a good answer。 I would say the more you have。

 the better because then it's kind of learning the distribution of different system prompts。

So I don't know if they put the exact number in the llma paper。

But just the number of times that they mentioned the system prompt。

 you can tell that it's something you know that they were thinking about a lot。

 and so they were probably trying a lot of different system prompt and putting them into the data。嗯。

There might be papers that have looked into that， I would have to look after the lecture though。G。

 the coupon be used for。Instruction union in general。

 like why specifically use them for will be chat for me。Yeah， so I guess it's。

 it's kind of just the way the。I guess since you have multiple turns in a conversation。

 the point of the sense prompt is to have something that stays the same across multiple turns。So。

 yeah。嗯。😊，啥给灵魂的钱。喂。I think how you made that decision is now we have models with putting great contact sides。

Or organizeizing100，000 payments。When you make that decision。我意晒咁样嘢我哋。Yeah， that's a good question。

The question is。Let's say we care about a specific task。Kind of， should we use。In context learning。

 fu shot learning or fine tuning， and when do you decide， how do you decide？I would say， yeah。

 first of all， one determiner is the amount of data you have for the task。

So if you have a very small amount of data， then you might just be limited to prompting or fe shot learning。

If you have a large amount of data， I would say it's less common to prompt a model with a lot of data。

 but people are starting to explore that and yeah now that we have really long context models。

 you can do that。So I would say some of it depends on like if。

If you're able to fine tune the model and are fine with having a separate copy of the model。

For your task。Then in general， fine tuning is adjusting you know billions of parameters in the model。

 so it should be better than prompting if you have enough data。

But sometimes people will just prompt because they don't want to go through the trouble of finening。

Okay， so next， I wanted to mention this idea of knowledge distillation。

So several methods that we discussed。Use a model to generate data for another model。

And the kind of framework for this。Is that doing this is an instance of what's called knowledge distillation。

Where we have some teacher model and it could be a larger model like GP4 or you better model。

And then we're in some sense， distilling information from it into a student model。

 which could be something like a small language model。

And so there's two different ways to do distillation。The first way。

 and this was like the traditional way where it was proposed。Is。

You train the student to literally mimic the。Next， token distributions from the teacher。

So for example， here we have translation。Or this could be an instruction and an output。

And then we get some next token distributions。And then we take the cross entropy between these two distributions。

So the idea is that the， yeah， the student is basically fitting。

Distribution to the teacher's next token distribution。And so you could see here。

 this is just the cross entrytropy loss that we've seen before。

But now you have some supervision on basically like every possible next token。

So this was proposed in 2015。In the context of image classification， I believe。

But some people do use this with language models like one of the models trained by Google called GeA。

Actually use this kind of token level distillation。

To train a smaller model using knowledge from a larger one。

Maybe I'll skip this or just mention it briefly， but again。

 there's this connection between cross entropy loss and kale divergence。

And so the way you can think of this is that the student is learning the distribution of the teacher。

And you can show that this is the case。嗯。Yeah， using a similar derivation from lecture three。

But yeah， I wanted to mention this one， which is called sequence level knowledge distillation and so this looks a lot like what。

We talk about when we generate a data set with a model， say GP 4。

So here we're not looking at next token distributions。

 we just generate some full sequences with the teacher model。

And then the student model fine tunes or trains on the resulting data。

So we have this now data set of like prompts and responses。

And we can find tune the student model on it。So it turns out that this is actually oh so here's an example a real world example。

 so recently there's this deepse model deepseq R1。And they created these smaller models。

 which were distilled versions。And so if you look at the name of the model。

 it might be something like deepse R1 distill when 7b。

And that means that their student model is just  seven billion parameters。

 and it's basically just trained on you know outputs that were produced by the larger deepseq model。

And so I wanted to be sure to tell you about this because yeah。

 you'll definitely see this term distillation come up and it actually relates to this idea of fine tuning a model on kind of synthesized data from some teacher model。

The interesting thing here is that this also minimizes the KL divergence between the teacher and the student。

So the student， yeah， is essentially learning to mimic this larger model or the teacher model。

You could again like write out the definition of kale divergence and you eventually get something like this。

And so now you can see that we don't have this supervision。At the next token level。

It's just taking this kind of sequence。Sample from the teacher and then。

Minimizing the negative log probability or maximizing。The probability of the sequence。嗯哼。😊。

How to implement something like this like what are the algorithms to fit the studentss distribution to the teachers？

Yeah， so this is it's just what we've been talking about。

 so you basically generate the data and then you fine tune the model to predict the next token in the response given the prompt。

Does that make the students ways promate the teachers？Just。Yeah， yes。

 so I'm going through this kind of quick， but basically when you do the next token prediction。

 you are maximizing the likelihood or you're minimizing this minus log probability of the sequence。

And so then this slide is just saying that， yeah， doing that procedure。Basically， you know。

 generating a data set and then training the student model on it actually corresponds to the student。

Fitting the teacher's distribution over outputs。There any other advantage of doing this other than。

Ending up with a smaller model that's like easier to carry around。Yeah。

 so another another potential benefit is that。嗯。Well， yeah。

 so a main benefit is you can get a smaller model。 Another is that you could imagine the。嗯。

The teacher model。Yeah， so I'm going through this kind of fast。

 the teacher model you can kind of augment with other stuff。So for example。

 you could sample from the teacher and let's say you have some verifier that。You know。

 checks whether the solutions are correct or not， then you can filter out the incorrect ones。

And only train on the correct ones。And so now you're actually training on something slightly different from the teacher distribution。

It's the teacher distribution， but only restricted to like their cracked outputs。

And so in this sense， youre actually could， you could， in theory。

 even do a bit better than the teacher because your distribution's been kind of filtered， yeah。嗯。

Okay， and so then let me just briefly go through the efficient plantainning。嗯。

And I should mention that。The author of one of the techniques will be giving a guest lecture on quantization。

 So I think during that lecture， he'll go into more detail on this。So。The idea is that。

 you know one option is to fine tune your model and update all of its parameters。

But this can get pretty expensive， so let's say we're trying to fine tune a 65 billion grameter model。

Then each parameter， let's say that it's represented using。16 bit precision。

Then the parameters will be 130 gigabytes that you would need to put into GPU memory。

You also need to take the gradients when you're optimizing。So that'll be another 130 gigabytes。

And then if you're using an optimizer like Adam， if you remember it kept track of these different statistics。

Like the first order， statistics and second order。Usually those are actually stored in like 32 bit precision。

Again， Tim Detmers is giving the guest lecture on quantization。

And he'll talk about this idea of precision in a lot more detail。

 so I'm just going through it kind of quickly now。But this is just getting across the message that。

 you know， if you want to find tune a large model， it requires a lot of memory。And so if we look at。

Some example GPUs。Then。Yeah， here we typically have a GPU that's like 24 gigabytes or maybe up to to 80 gigabytes。

Um， and so we have to do something， you know， because back on that previous slide。

 we had like hundreds of gigabytes or thousands。So one option is to split up the model across Oops multiple GPs。

We'll actually talk about that in a later lecture as well， like parallelization techniques。

But what you could do is you could try to get clever and only update part of your model。

 so instead of updating all of the model' parameters，Just update a smaller number of parameters。

So one of the most common ways nowadays for doing this。Is called Laura or low rank adaptation。

So for example， if you look at those two fine tuning libraries I mentioned。

Then they'll definitely have Laura implemented， so you'll see this term come up a lot。

And the idea here。Is。Here's the kind of key picture。So here in your transformer。

 let's just consider one weight matrix， so this could be the。The weights in the attention layer。

 for example。The key idea behind Laura is to not update these weights。

 but instead just introduce the small number of weights here。

And the weights are basically find the difference between the pretrain weights and the kind of new fine tuned weights。

Okay， so now again， you're not finening the original weights， you're just finding the difference。

And then the other key idea is you can reduce the number of these parameters by making it low rank。

So here we're like reducing the size of this inner dimension。

And here the hypothesis and they talk about this like in the paper。

Is that after the model has been pretrained？Maybe you actually only need kind of a， you know。

 small dimensional subspace to update the model to a good point。Okay。

 so now what you do is just introduce these Laura layers。Um，For like different parts of the network。

And you freeze all of the models's parameters and only update these。

So now the cool thing is that if you look at this equation。

Then you have your original weights and you have the new ones that you're actually updating。

And they're just added together。So then what you can do is after you do the fine tuning。

You can literally just like add these to the weights of the network。

And then save the model and use it and deploy it。So there's actually nothing extra that you have to add on the model。

You're again， just learning these numbers that you then add to the original weights。

So this is like really widely used now。Again， if you look at the number of parameters in these orange parts。

It's much， much smaller than the number of parameters in the full model。

And it's very convenient because after you fine tuned。

 you can just add the numbers into the existing weights。If we were doing this。他つ都。

Memory of the retrained weights and the new matrix of differences giving us an overall higher memory consumption。

Yeah， so the one key difference is that you're not computing the gradients for the weights。

So you're not competing the gradients and then if you're like using atom。

 you're not keeping track of those statistics， yeah。嗯mhm。😊，Why matrixri is visualized。Yeah。

 they in the paper， they just say they do that so that it starts at zero there might be a deeper reason。

 but oh yeah， I'm not aware aware of it。嗯。老子间不该。It's。It's a very dynamic。李总么。Yeah， yeah。

 so the idea is your fine tu code。Stays exactly the same from， you know aside like inside your model。

 you have to implement these little Lauraura layers。But then the fine tuning code stays the same。

 You just freeze your model parameter weights and you're fine tuning and only updating the weights in orange。

So it's so。Mhm。😊，Yeah。Yeah， it's fine tuning， but you're only adjusting parameters。

For these Lauraura layers， you're not updating all of the parameters of the model。好。好。Yes。Yeah。

 so you still have to do the forward pass through the entire model and then the key difference is that you're only taking gradients for these kind of small orange weights and it becomes a lot more efficient。

that's yeah so that's a really great question I don't have like an all encompassing definitive answer but one way to think about it is that if you update all of the models weights then you kind of have more degrees of freedom so you have billions of parameters that could be adjusted。

Whereas with Laura， you have a smaller number of parameters。So roughly speaking， for some tasks。

 you'll be able to match the performance with Laura。

I think roughly speaking like if you're doing classification or something like that。

 but then if you're doing a really long， like complex long form generation。

 then people will start to see performance gaps because maybe you actually have to update you know。

 larger parts of the model。对。Okay， and then let me just mention this quickly， but as I mentioned。

 the author will be giving a guest lecture about this。

 but there's an even more efficient version called Q Lauraura。

And the idea here is you can do what's called quantize the model。

So instead of representing the model as 16 bits， you can represent it as four bits。嗯。However。

 they keep the Laura adapters at。16 bits。 and they come up with ways of like offloading computations to the CPU and things like that。

U so again， I want just in case you see this Q Laura， it's also implemented in all the libraries now。

And in practice， it can let you like。Fine tune really large models。Like one GPU and things like that。

 but as I mentioned。Tim will give a whole lecture on quantization and we'll go into this in more detail。

Okay， cool， so we have。嗯。Like two minutes， I wanted to just give this recap and maybe introduce a couple more like summary insights。

So again， with fine tuning， we're ultimately adjusting a model's parameters using some data。

And then instruction tuning， you can kind of think as a clever way of formatting the data so that the model can learn to do multiple tasks。

And then knowledge distillation， I went through it kind of quickly。

 but one insight is that the data can come from various teachers。And ultimately。

 we're fitting the model distribution to kind of match the teacher distribution。

So you can even think of like fine tuning as being this data set that's kind of produced by maybe a human。

But you can also have models kind of generate the data that you fine tune on。

And then you can do this more efficiently by only updating some of the models parameters。

So that's it for today。

![](img/67431f0f3726bc2694d1bd200dbf1b83_74.png)
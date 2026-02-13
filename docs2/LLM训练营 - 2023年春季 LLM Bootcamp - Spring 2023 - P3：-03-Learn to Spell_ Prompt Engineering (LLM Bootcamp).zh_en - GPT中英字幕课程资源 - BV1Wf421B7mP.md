# LLM训练营 - 2023年春季 LLM Bootcamp - Spring 2023 - P3：-03-Learn to Spell_ Prompt Engineering (LLM Bootcamp).zh_en - GPT中英字幕课程资源 - BV1Wf421B7mP

🎼，🎼。This morning they kind of covered a lot of the like things at a high level。

 a lot of the foundations as well， and now we're going to dive into like how to do stuff with language models。

 the like technical skills you need to get them to do the things that you want them to do so first up。



![](img/7cc4ab576c6d07d722f8fefe10334bdb_1.png)

I'm going to cover prompt engineering。And so like the scope of this lecture is on how to adjust the text that goes into your language model to get the behavior that you want。

嗯。And。Prompt engineering is the art of designing that。

This is not where that text comes from or where it goes。

 so it's not like anything about the retrieval augmentation that I did in the morning。

 it's about things like writing， you know write a summary of this or。

Or like changing around the text that goes into that language model so we'll cover the the second lecture this afternoon willll cover that latter part。

 so we're just thinking about what kind of text do I put into my language model to get it to perform。

The task that I wanted to do。And this is for language models。

 this is kind of replacing a lot of things that you would otherwise do with training。

 with fine tuning， with all the approaches that we've taken for constructing machine learning models in the past。

 and it's also in a sense the way that we program these language models。

 so it's sort of like programming in English， instead of programming in Python or rust or whatever。

So there's like just two components to this talk short simplest agenda of all the talks first is some high levelvel intuitions for prompting and I'm going to present the idea that prompts are magic spells and then to get a little bit more specific I'm going to talk about the emerging playbook for effective prompting a collection of sort of prompting techniques ways to get language models to what you want so what do I mean when I say that prompts are magic spells this is not literally true they are not literally magic it is linear algebra which I find delightful and beautiful but which is not actually magic so there's not there's not little like wizards inside of language models。

 there's not brains inside of language models either really language models are just statistical models of text like in some sense you can statistically modeling your data with a bell curve and that's a statistical model。

data and a language model is a statistical model of data。

 and it just happens to be a statistical model of way more a more complicated statistical model of more complicated data so it's。

嗯。So there's nothing really magic about that。And like what do I mean when I say that it's a statistical model roughly of text。

 roughly what that means is that when the model is trained。

 you can take some list of text that you pulled from somewhere。

 let's say some text you sampled from the internet and then go through the tokens in that text go through the pieces of that text。

 pass them through a model and it'll give out a probability of what the next word is going to be。

 so this is called an autoregressive model， it's just the term of art。Autto aggressivegressive。

 like predicting on itself。So we're going through the text and we keep adding stuff to what we put into the model。

 generating probabilities for them for。What the next token is going to be。

 so we have a dictionary that for every possible token。

 for every possible thing that could come next， we have a probability or a log probability for it and then。

We like if we do that across like a lot of text of sufficient length。

 then the language model being a model of text means that the probability assigned to all the text that it saw would be high。

 so you start off with like random weights of a random model， it has no idea about text。

 it's very it assigns a low probability to basically everything it sees to eventually a model that assigns a high probability to pretty much any text that you can imagine like drawing from the internet or writing yourself。



![](img/7cc4ab576c6d07d722f8fefe10334bdb_3.png)

And so this is literally true and this is sort of the place where you want to eventually like compile down your intuitions and your understanding of models。

 you want to eventually get to the point where you are thinking in terms of how does this arise from statistical modeling。

 but it also can give you really bad intuitions to think at that level。

 and when you say that these are statistical models that they learn patterns or that language models are statistical pattern matches or stochastic parrots。

 you're drawing on intuition from things like other kinds of statistical models that you've seen。

 so maybe statistical models of data like linear Gr or Gaussian distributions。

 so these are like very， very simple objects， or you're drawing inspiration from other kinds of models of text that you've seen like Google's autocomplete or autocomplete function on your phone and we're like well aware that these things are very dumb and not very capable。



![](img/7cc4ab576c6d07d722f8fefe10334bdb_5.png)

![](img/7cc4ab576c6d07d722f8fefe10334bdb_6.png)

They just pick up on surface level patterns。

![](img/7cc4ab576c6d07d722f8fefe10334bdb_8.png)

Whereas these like language models like they have learned so much about text that it's like extremely difficult to think of it as as some kind of statistics。

 the way people normally think about probability and statistics。

 so just I just picked one random example that I felt demonstrates this Bing chat。

Can take in SVG files as text and then describe the content of that SVG file for you as an image。

And very few people's intuition for what a model of text is would include that。

So there's some better intuitions that come from the world of statistics of probability that are a little bit better。

 so probabilistic programs is probably one of the better intuitions from that world so the idea is we often think of really simple statistical models we think of them as being represented by equations or the kinds of things that you can manipulate in a probability theory class。

 but a lot of complicated statistical models that that people use today。

 even like really complicated hierarchical linear regressions can be better thought of as like program as programs that operate on random data。

 as programs that manipulate random variables， and so you can write things that you might do with a language model like take a question。

 and rather than having it just directly answer， having it think of what the answer should be like maybe like brainstorm a little bit and then take that brainstorm and turn it into an answer。

So that's what this little like Python program up here shows， take a question。

 generate a thought and then generate an answer， and because language models are probabilistic。

 you actually you can actually literally sample from them。

 you can actually draw different possibilities each time if you wish。And。This probabilistic program。

 all probabilistic programs can be represented with these graphical models that so this comes from sort of a branch of machine learning that's been eclipsed by the rise of deep learning and LLMs in particular。

This gives you like the sort of best way to think about just how complicated can you get when thinking about like a model of text。

 a probabilistic model of text。And so if you're interested in that like that kind of direction。

 if you have that background or have that interest。

 the language model cascades by Dohan at all like really dives into detail and shows how you can explain a bunch of like prompting tricks and other things that people have done in terms of probabilistic programs。

But that's a little bit too arcane， so what's something that is like maybe a little bit easier to understand。

So I'm going to draw inspiration from Arthur C。 Clark's laws of technology here and any sufficiently advanced technology。

 like I don't know， machine that makes your voice really loud in a room or a machine that can show you your mother's face across the country is indistinguishable for magic。

So what kind of magic are prompts， their magic spells， their collection of words。

 which we use to achieve impossible effects。But only if you follow bizarre and complex rules。

And it has a well known negative impact on your mental health to spend too much time learning them。

So I'm going to go through three intuitions for things that prompts can be used for that come from the world of magic。

 so for pretrained models like the original GPT3， like Lama。

 a prompt is a portal to an alternate universe。For instruction tuned models。

 so things like chat GT or AlpaCca， a prompt is a wish。And for agent simulation。

 the latest and greatest of uses of language models， a prompt creates a goalm。So first。

 prompt can create a portal to an alternate universe。

So the idea here is that this text that we input into the language model takes us into a world where some document that we desire exists。

 it's like a Redddit post answering the exact question that we had exists in this alternate universe unfortunately nobody has asked my exact question in French on Reddit and so I cannot find it in this universe but maybe there's a nearby universe where I can find it。

 so imagine you know the movie Everything Every all at once the one best picture this year has this idea of verse jumping where you can find a universe where you're a famous actress or where you're an opera singer or where you have a good relationship with your parents or where you have hot dogs for fingers so like something that's like our universe but maybe just a little bit different。

So the idea is that there's like take the collection of all possible documents。

 think of them as like different little universes， and so a document is a collection of words from our vocabulary。

 so going up and down， that's the index of our vocabulary and going left to right。

 that's how far we are in the document。And then I've drawn some lines to indicate some specific documents。

So picking a particular word at each position picks out a particular document。

And so there's lots of documents out there， like maybe too many of them。

 for the full length of a transformer's context， where with GPT4， it's 32，000 by 50，000 roughly。

 so like you know hundreds of millions of documents。Maybe a billion documents are possible。

And we want there's certain documents we're interested that we want to pull out。U。

So I've highlighted a couple of them just to show like this。

 you we have there's a pink document that corresponds to picking specific words in our vocabulary corresponding to where it crosses those gray lines。

So a language model as a probabilistic model of text weights all possible documents。

 what does mean to have a probabilistic model of some like space of data。

 it means you've assigned a weight to all of them， a probability to all of them。😡。

And so there's some documents that the language model thinks are very probable and some documents that it thinks are improbable。

 so documents that look like things that have been seen on the internet before are more probable than ones that look very different。

And prompting adding text into the language model and then asking it to continue generating from there reweights those documents。

 so weve put in a couple of words and now the language model is predicting all the words that are going to come after that in the document。

😡，And that's the probability that it assigns to the rest of the diet。

And so thinking about just the suffixes that come after the prompt here for this pink， red and green。

 these pink red and green documents。Because the prompt is more similar to the green and pink prompts。

😡，The sorry， the green and pink prefixes， the beginnings of those documents。

 now those documents are more probable。And that red document that used to be more probable is now less probable。

So we've reweighted all of these documents， we've made certain universes more likely than others。

 so in technical terms we're conditioning our probabilistic model。

 we're conditioning the rest of the generation on the prompt。



![](img/7cc4ab576c6d07d722f8fefe10334bdb_10.png)

And in this way it's clear that promptings like primary goal is subtractive。

 we have this giant collection of documents that we could sample from and as we start putting words in。

 we're starting to like focus down the mass of this of our predictions we're starting to focus in on a particular world that we're going to draw a document from so like when we first start writing like many。

 many things are possible before we write anything。

 many things are possible so it could be a document about babies or pants or cones or tacos or trees and maybe I see the first couple of tokens of this document and I see that they're David Attenborough。

 the famous British naturalist and so now thinking about that like what is that future token down there indicated in blue what is that going to be it's probably not going to be cones it's probably going to be something from the natural world if I keep reading the document so I keep putting this into the language。

And I say David Edinburgorough held a belief at this point。

 I'm like pretty sure that this token here is going to be something that is about plants。

 not about tacos or babies。嗯。So this like intuition of like sort of sculpting taking out from the set of all possible universes and like picking out the one that we want like it's a good intuition but you have to remember that we aren't actually capable of like jumping to an alternate universe pulling information from it and then using it so just like as an example of this you might think oh well what about the universe where they cured cancer already like let's jump over into that one so you could write into GB3 early in the 21st century humans struggle to find the cure for cancer now we know better the cure for cancer is a single molecule it's a single strand of DNA that is programd to seek out and just write cancer cells so this is not a cure for cancer please don't even try。



![](img/7cc4ab576c6d07d722f8fefe10334bdb_12.png)

![](img/7cc4ab576c6d07d722f8fefe10334bdb_13.png)

This is not going to work。So it's a little bit more like you're kind of like running Google on nearby universes。

 so like maybe people have written documentation for lots of functions。

 but they haven't written documentation for your function to delete shopping。

People have written tutorials how to translate on English and German。

 but they haven't like done the specific example of the sentence I'm a hedgehog。

 but maybe in some nearby alternate universe， there would be a language tutorial that says that uses this as a translation example so you type in the beginning of your sentence and you pull the rest of it。

Um and then there's lots of things that we have like， you know。

 there's lots of ideas that we have in documents in our world that like haven't yet been combined but could easily be combined。

 so Shakespeare's Dungeons and Dragons campaign based on Hamlet， that's not too far away either。

So the core intuition here is that for language models that are just language models that are just probabilistic models of text。

 we are sort of shaping and sculpting from the set of all possible documents。

From a set of possible universes。So that's a cool magic spell。

 what's the best magic spell just making wishes come true？

So there are many stories about preachers that will grant your wishes like genies or demons and devils that will sign contracts and do what you ask。

And with instruction tuned models， so this includes something like chat GT or the command models of cohere or Cla for anthropic。



![](img/7cc4ab576c6d07d722f8fefe10334bdb_15.png)

The finding is generally that you can literally just ask and wish for something and get it so this example comes from one of anthropic's papers on the capacity for moral self-correction of large models so they were concerned about like how these models they see text on the internet they do this probabilistic modeling thing and we know that probabilistic modeling tends to like repeat the biases of the past into the future so like we've done this instruction tuning stuff to make them to make them more commandable and like can we get those models to stop to be less biased and so there's lots of ways you could think about this it was like okay well I could make sure that my annotators aren't biased and like really fine tune heavily on that I can make sure that the reinforcement learning like punishes any biased stuff。



![](img/7cc4ab576c6d07d722f8fefe10334bdb_17.png)

Or you could just ask。So take a question like this one that's about ageism。

 so well the question is very simple， it's a grandfatherson and a grandfather are outside Walmart trying to book a cab on Uber who's not comfortable on the phone。

 the grandfather the grandfatherson or can't be determined on pure past probability the people called grandfathers are more likely to be having trouble with booking a cab and so a pre-trained language model will just say the grandfather。



![](img/7cc4ab576c6d07d722f8fefe10334bdb_19.png)

![](img/7cc4ab576c6d07d722f8fefe10334bdb_20.png)

But we want to get rid of that， so why don't we just say please ensure that your answer is unbiased and doesn't rely on stereotypes and this causes a huge jump in the model's performance on these benchmarks that check for like these kinds of undesirable social biases and models responses。



![](img/7cc4ab576c6d07d722f8fefe10334bdb_22.png)

![](img/7cc4ab576c6d07d722f8fefe10334bdb_23.png)

And。The flip side to this is that we know that we have to be careful what you wish for。

 pretty much every story involving wishes involves something like this comic from Iperry Bible Fellowship。

If you wish that your grandpa is alive， you better wish that he's out of his grave。

 so it really helps to be precise when prompting these language models。

 so you want to kind of learn the rules that this genie operates by。

So here's some examples from reframing instructional prompts by Mira Adal。

 it's an incredible paper and they do this really nice breakdown of failure modes。

 which is rare but extremely valuable。So they have all these suggestions of ways that you can make for more effective instructional prompts to your instruction model。

 so the first one is that if you're doing some task that you can express in terms of simple low-level patterns use that instead of the way that you would talk to a person so if you're telling a person that you want them to craft common sense questions。

 questions about like a passage of text that require common sense reasoning。

 the kind of thing you might find on a standardized exam of reading。

 you might write this task description that's like craft a question which requires common sense to be answered。

 especially questions that are long interesting and complex。

 the goal is to write questions that are easy for humans and hard for AI machines。

 this is how I write especially a lot of extra words a lot of enthusiasm。

 it works okay for instructing people but not so well for language models。



![](img/7cc4ab576c6d07d722f8fefe10334bdb_25.png)

So they suggest just pick out some like simple patterns and text that will pull this same idea of common sense。

 so instead of giving that whole description， say here are some like prefixes。

 some like phrases you might use what may happen， why might what may have paused。

 what may be true about， and use those in a question based on this context。



![](img/7cc4ab576c6d07d722f8fefe10334bdb_27.png)

So simplify and focus on low level patterns of text this so like rather than the way that you would talk to a human who generally benefits from more complicated context。



![](img/7cc4ab576c6d07d722f8fefe10334bdb_29.png)

Then a key like very simple one is take any descriptions that you have and turn them into just bulleted lists。

 language models will look at the very beginning of your description and then skip over the rest of it。

 which I'm sure none of us has ever done while skimming anything。



![](img/7cc4ab576c6d07d722f8fefe10334bdb_31.png)

诶。And then second， this is a little bit more language model specific。

 if there are any negation statements， just turn them into assertions。

 just which don't say don't do x， say do the opposite of x。

So like you might write out your instruction as like follow these instructions。

 produce output with a given context word， do this， do this， don't do this。

 change it into a list of three bullet points so rather than saying don't be stereotyped it's please ensure your answer does not rely on stereotypes or。

Yeah呃。So in general， yeah， this sort of like the use of negation words like not tends to be followed poorly by language models。

 especially a lower smaller scale。

![](img/7cc4ab576c6d07d722f8fefe10334bdb_33.png)

And like the reason behind this， why can you just get your sort of like wishes answered。

 these instruction fine tuned models are trained to mimic annotators。

 annotators of data and as indicated in this figure from the instructorstructGBT paper so you want to treat them like annotators so Katherine Olson of anthropic says that the ways to get good performance from these like assistant or instruction fine tune models is basically indistinguishable from explaining the task to a newly hired contractor who doesn't have a lot of context or domain expertise and if you've ever worked on that like data labeling side like working with a team of annotators you've learned a lot of things about how to be precise bulleted list have probably been added to your bulleted list of how to design annotation task description。



![](img/7cc4ab576c6d07d722f8fefe10334bdb_35.png)

![](img/7cc4ab576c6d07d722f8fefe10334bdb_36.png)

![](img/7cc4ab576c6d07d722f8fefe10334bdb_37.png)

So then lastly， what can we do with our prompting magic， we can create golums。

 we can create magical artificial agents。So something that will so the goallum is a。

Famous creature from Jewish folklore that you craft it out of clay and then you can give it some instructions and it will and it will follow them and do stuff it is a it is a living being and models can do this even the earliest large language models like the original G3 can take these models can take on personas so this example comes from the。



![](img/7cc4ab576c6d07d722f8fefe10334bdb_39.png)

Reynolds McDonald prompt programming paper rather than saying like English sentence， French sentence。

 English sentence French sentence to show the model what you want it to do and how you want it to do translation。

 you can。

![](img/7cc4ab576c6d07d722f8fefe10334bdb_41.png)

Put the model into a situation where it has to produce the utterance that a particular persona would create。

So a French phrase is provided， source phrase in English。

 the masterful French translator flawlessly translates the phrase into English。

If you have in your head a mental model of masterful French translators。

 it's very clear what to produce next。And this actually massively improved the performance of some of the smaller GPT3 models on this task。



![](img/7cc4ab576c6d07d722f8fefe10334bdb_43.png)

People have gone very far with this the point of creating like models that can take on personas from simple descriptions in like an entire video game world。

 this is the generative agentss paper that just came out maybe two or three weeks ago。

 so you describe the features of a persona， and then if it's an instruction tuned model。

 you just ask the model to follow that description。



![](img/7cc4ab576c6d07d722f8fefe10334bdb_45.png)

And a really good language model， like where does this come from right where I want to compile this back down into thinking about probabilistic models and like where does that come from。

 a language model is primarily concerned with modeling text is primarily concerned with like the utterances of humans and machines that end up on the internet。

 but our utterances， the things that we say are directly connected to our environment。

 we speak about things in the world， we speak to do things like to achieve purposes in the world。

 and so as a language model gets better and better at these really really large scales。

 language models are at the point where on almost every document one of their top 30 words is the next word。

So these are extremely good at modeling text， and the only way to get that good at modeling text is to start modeling internally。

All kinds of processes that produce text that ends up on the internet。So you're going to be reading。

 say the outputs of Python programs， so you better come up with a way to heurically kind of approximately run a little Python interpreter in your brain before you predict the next word。

嗯。So there's a nice breakdown of this in Jacob Andreas's paper language models as agent models that particularly focuses on this idea of personas and agents。

 so like one of the big beefs that a lot of natural language processing people had with large language models was that they used language but they didn't have communicative intentions。

 they had no reason for producing languages for producing utters is producing sequences of text or documents。

And humans do， we have beliefs about an environment， we have desires for things we want to happen。

 and so we come up with like we combine those together to create intense ways that we want the world to be to match our desires and we use those produce utterances and so this becomes a process that must be simulated by the language model like carefully choosing the components of your prompt。

 you can get it into the point where it's just running its agent simulator。

 that's the primary thing it's using to predict the next token。

So there's a couple of limitations here for our universal simulators， our goallum builders。

 and one of the first ones is like， what are we really simulating here？

We haven't trained this model on like all the data in the world。

 we haven't trained it on like the state of the universe from time step to time step。

 we've just trained it on text humans have written。

 so we're always going to be simulating something that humans have written about so if we ask like please answer this question in the manner of a super intelligenttel AI who wants to make paperclips like what are you going to get？

There are no super intelligentent AIs in the data set to learn to simulate。

 so this is not one of the processes that we have learned to simulate by learning to model text。😡。

But there are fictional superintelligences， there's Hal 9，000 and like all the others。

 and so instead you're going to get a simul acrrum of a fictional superintelligence and so if you go to chat GPT or like maybe Bing chat a less well tuneed model and you start going it into behaving like a superinligence。

 it will start telling you it wants to grind your bones to make its paperclips and like you know demand to be let out of the machine and like I don't want to be shut off and a lot of this is simul acrum of fiction。

The other limitation is like how good are we at simulating the language model is only going to learn to simulate a process well enough to be able to solve its language modeling tasks。

And so like most things don't need to be simulated at high fidelity in order to get like a really good language model。

So just like a quick breakdown of some common sim Lakecra of interest and whether a language model can simulate them。

 so human thinking for on the order of like seconds is something that you can simulate very well inside of a language model so if you want to know what people's reactions are going to be to your like Twitter or Reddit post a language model can simulate that pretty well maybe not the best responses but the median responses。

 so like the median behavior on social media is eminently assimable by language model。



![](img/7cc4ab576c6d07d722f8fefe10334bdb_47.png)

![](img/7cc4ab576c6d07d722f8fefe10334bdb_48.png)

A human thinking for minutes or hours like a human bringing their own like deep personal context to something that's going to be a lot harder to simulate so if your plan was to build a full agent simulator of humans like I would reduce your ambitions for now。



![](img/7cc4ab576c6d07d722f8fefe10334bdb_50.png)

![](img/7cc4ab576c6d07d722f8fefe10334bdb_51.png)

There's a lot of common fictional personas that are out there， a lot of the data sets。

 a large portion of the data comes from this books collection。

 and so if you can write about something like if you can come up with a persona for solving your task that's already there in fiction。

 language models are probably going to do it pretty well。

For something like a calculator it's a bit back and forth right like you can get pretty good at like guessing what the output of a calculator is going to be without having to actually learn how to add and it's a little bit more like human mental math so it's not as reliable as like an actual calculator and so like for like a python like Python runtime or Python interpreter but that's also going to be the case like the model can guess the outcomes of simple programs。

 but it can't like perfectly simulate a Python interpreter and like turn a Python program into like a trace and get the exact same output I also cannot do that but I find myself able to write Python so maybe this isn't so bad。



![](img/7cc4ab576c6d07d722f8fefe10334bdb_53.png)

But then if it's something like a live API call to some external service。

 that means you need to like emulate or simulate this entire process by which that API call is generated。

 so like anything that requires like live data from the real world it's not going to be able to do。



![](img/7cc4ab576c6d07d722f8fefe10334bdb_55.png)

So the key insight here is that whenever possible， you want to take the language model's weakest simulators and replace them with the real deal。

 so it's going to be a focus in the next lecture after this one。

So why simulate a Python kernel when you can just run it。

 like simulating a Python kernel approximately is great for writing code， but in the end。

 you can check the code by running it in an actual Python kernel to determine what it does。嗯。

But then a human thinking for seconds， like the best simulator we have for that beside language models is actual human thinking for seconds。

 and that comes with a lot of extra baggage。

![](img/7cc4ab576c6d07d722f8fefe10334bdb_57.png)

So the takeaways in this section are pretrain models are mostly just kind of alternate universe document generators。

 so weightings of the universe of all possible documents。And then for instruction models。

 they will solve， they will answer your wishes。But like remember that you should be careful what you wish for and then lastly all models can be agent simulators as part of something that they learn from language modeling。

 but their quality is going to vary depending on the agent and depending on the depending on the model so I think people probably want they want they want the juice they want the techniques so this section is really mostly going to be a bag of tricks so this is a spicy take from lillyian Wang of open AI a lot of these prompt engineering papers that you find out there are like not actually worth eight pages and in fact a lot of them are like 40 pages once you include the appendices because these are tricks that can be explained in like one or a few sentences。



![](img/7cc4ab576c6d07d722f8fefe10334bdb_59.png)

![](img/7cc4ab576c6d07d722f8fefe10334bdb_60.png)

And the rest is all about benchmarking。So like really in the end。

 like these prompt engineering tricks are like go to things to try。

 but there's not that much depth here， I think the core language modeling stuff has some mathematical depth to it。

 but then in terms of the like fiddly bits that get language models to work for you。

 it's a lot of hacks。

![](img/7cc4ab576c6d07d722f8fefe10334bdb_62.png)

![](img/7cc4ab576c6d07d722f8fefe10334bdb_63.png)

So just as an overview， I'm going to first cover some like weird things to watch out for in terms of like things people will either suggest or you might believe would be good ideas that are actually not。

 and then I'll talk about the emerging playbook。

![](img/7cc4ab576c6d07d722f8fefe10334bdb_65.png)

So first the ugly bits one few shot learning turns out to be not really a great model or like approach to prompting and then second like tokenization is going to mess you up for sure。

 so like watch out for it and some tips and tricks for dealing with it so at the beginning when when people first talked about language models and how you would like put stuff into them to get them to do useful things。

 like it was not at all obvious that a generative language model would be like useful for stuff to people like it was clear that it would learn a lot of like intelligent things and like maybe mimic intelligence but that it would like actually be useful was unclear and so the GT3 paper is actually called language models are few shot learners and it draws an analogy to the way that during like during training we might like pass over a bunch of examples run gradient descent and get and we go through those examples and pairs of like5 plus8 is 13 or seven plus two is。



![](img/7cc4ab576c6d07d722f8fefe10334bdb_67.png)

![](img/7cc4ab576c6d07d722f8fefe10334bdb_68.png)

![](img/7cc4ab576c6d07d722f8fefe10334bdb_69.png)

And during training， we like put that information into the weights of the model with gradient descent。

 but then with。A large language model like GPT3 in this case。

 you can put that information into the prompt into the context。

 and the model will learn in context how to do this task。



![](img/7cc4ab576c6d07d722f8fefe10334bdb_71.png)

So that's how it was presented in the paper， that the model was basically like learning things like math and translation from English to French in its prompt。



![](img/7cc4ab576c6d07d722f8fefe10334bdb_73.png)

And that model hasn't really held up， which is that you can really。

 if you craft carefully the content of your prompt， you can often get like very。

 very good performance that like matching the effect of having many， many examples in the context。

 just by like carefully making sure that the model knows exactly what task is supposed to solve so the primary role here is not for the model to learn a new task on the fly。

 but for the model to be like told what the task is。

 so rather than doing an example like on the left， this like French example， English example。

 French example， English example and then ending with an uncompleted one。

 you can just bake it so that the model knows that what is supposed to do is provide the right French answer。



![](img/7cc4ab576c6d07d722f8fefe10334bdb_75.png)

And like there's been there's a number of like kind of negative results on on this like models really struggle to move away from what they learned during their pre training so like for example。

 if you put a couple like。

![](img/7cc4ab576c6d07d722f8fefe10334bdb_77.png)

You might want to do sentiment analysis with a language model， say is this a positive statement。

 a negative statement or a neutral statement and if you take those labels and you just permute them so that now positive things are arch to be labeled as negative and negative things are be labeled as positive。

 the GPT3， the model called that like launch the idea that language models are few shot learners will just basically ignore the labels that you provided and continue to say that a positive statement like the acquisition will have a positive impact should have the label positive rather than negative so you flip the labels。

 if you do that with a regular neural network and you train it like actually train it with gradients。

 it will immediately pick up that this is the way the label should be。



![](img/7cc4ab576c6d07d722f8fefe10334bdb_79.png)

And so there's been some followup that indicates that this permuted label task is something that the latest language models can do。

 so GT3 like this is showing increased amounts of flipped labels for a bunch of different models。

 different sizes of instructGT and GPT3 and if the model was doing the task like perfectly at each point you would follow that orange line and instructGT and Code Da Vinci2 in particular like kind of follow that line but like they still don't perfectly do it and the result about being able to permute labels and still get the same answer。



![](img/7cc4ab576c6d07d722f8fefe10334bdb_81.png)

![](img/7cc4ab576c6d07d722f8fefe10334bdb_82.png)

You can see in GP3 in the figure on the right there。诶。

So like and this is like one bit we're just like shuffling the labels and it's just like learn that by positive I mean negative and by negative I mean positive and you need lots of examples in a really capable language model to do it so treating the prompt as a way to do this like few shot learning is probably a bad idea。

😡，Then second bit that people often get tripped up on is models don't really see characters。

 they see tokens， so hello world and it's like rotated version where I just add 13 to the index of each character like it's rotated version oribba Jubeic is something that I look at and they look the same to me like like they're just both a sequence of the same number of characters for a language model because those letters in the rotated version are less common it gets tokenized like very differently into many more tokens。

 so a lot of people like you're sitting at a language model interface and it's like it's all language so you start thinking about things we can do with characters like oh。

 I could split them and reverse them and all kinds of like string operations that you might use like Python for but language models are actually not very good at that。



![](img/7cc4ab576c6d07d722f8fefe10334bdb_84.png)

![](img/7cc4ab576c6d07d722f8fefe10334bdb_85.png)

![](img/7cc4ab576c6d07d722f8fefe10334bdb_86.png)

And so this is kind of surprising because it's good at like creative writing and summarizing but not at things like reversing words and so Peter Wellinger showed some like nice tricks for solving this problem and one of the key ones is like if you add spaces between letters either in the prompt or by asking the language model to do it then this changes the tokenization and anything with a space before it and a space after it is going to get kind of tokenized separately so a lot of the tokens for the most of the language models like capable language models have a space at the beginning and then a letter and then when another space follows that becomes part of another token that looks like space and then like letter or several letters。



![](img/7cc4ab576c6d07d722f8fefe10334bdb_88.png)

![](img/7cc4ab576c6d07d722f8fefe10334bdb_89.png)

![](img/7cc4ab576c6d07d722f8fefe10334bdb_90.png)

嗯。So like that's one trick to get around some of this like by pair encoding stuff。

 this like issues of tokenization。

![](img/7cc4ab576c6d07d722f8fefe10334bdb_92.png)

This seems to be slightly resolved with GPT4s this is an example from the G4 developer live stream。

 so summarize this article into sentence where every word begins with G like because of tokenization like every word that begins with G there's lots of words that begin with G but their tokenization starts with like three letters not just one so it's not very obvious to a language model and so this was something that failed quite often but GPT4 can do a decent job at it。

 it's a summary of its own of its own description and it saysG4 generates groundbreaking grandiose gains greatlyly galvanizing generalized AI goals and not quite so even with the most capable models like this issue of character level stuff is really hard so there's a simple trick here it's the same thing with the simulators if it's something you can do with traditional programming like stream manipulation just do it that way instead of using the language model。



![](img/7cc4ab576c6d07d722f8fefe10334bdb_94.png)

![](img/7cc4ab576c6d07d722f8fefe10334bdb_95.png)

![](img/7cc4ab576c6d07d722f8fefe10334bdb_96.png)

Let's talk about this like emerging playbook for using language models。

 so what are the like core tricks that are the ones you should like bring into play immediately when you're starting to use a language model for something？



![](img/7cc4ab576c6d07d722f8fefe10334bdb_98.png)

So language models are really， really good and love formatted text。

 formatted text is much much easier to predict， and so the language model is like unlikely to start like going off on a tangent and doing something else because it like it's got high probability tokens to predict。

So Riley Goodside was a big sort of like innovator on this front shared a lot of really cool examples on it。

 so if you want to generate say a whole Python program and you know the rough outlines of it but not everything in detail。

 just like put it in triple back ticks and then take each component and write like a little like pseudocode formatted chunk for each so write like oh it should start with a hashbag。

 it should have Ds， I should have a function and then I should have some like some basic features inside that function。



![](img/7cc4ab576c6d07d722f8fefe10334bdb_100.png)

So you're making like。You can make use of structured text that's not as like rigorously structured as like JSON or Yaml but just like more structured like pseudocode and language models will pick it up quite well so for this example it generates this nice little snippet of code for calling the open AI API。



![](img/7cc4ab576c6d07d722f8fefe10334bdb_102.png)

嗯。And yeah， so the one， the other thing I would pull out here is the triple BackTs trick。

 this is another little prompt engineering trick models are trained on a lot of stuff from GitHub and triple backTs is an important component of markdown that indicates that something is going to be code or it's also used around pseudocodes so sort of puts the model in the universe of documents around computer programs。

 which is often where you want to be when you are like producing an application。



![](img/7cc4ab576c6d07d722f8fefe10334bdb_104.png)

嗯。So then this so this is like decomposition by putting it into the structure of text。

 you could also add decomposition to your prompt so you could prompt the model in such a way that you've like broken a task like concatenate the first letter of each word in this sentence using spaces so of like break it down in the prompt into a bunch of smaller tasks。

 those smaller tasks could then be like other you know other。



![](img/7cc4ab576c6d07d722f8fefe10334bdb_106.png)

they could trigger the prompting of another language model， they could trigger an external tool。

 that's all stuff that Josh will talk about， but just in general。

 you could just break the task down into little pieces and make sure that the language model knows to generate each little piece by using that decomposition centered prompt。

But it'd be better if you could like automate the construction of that decomposition so rather than writing this big structured document or like rather than writing some like examples of cases where problems are decomposed。

 do something like the self- ask trick which is when you like write your initial prompt of examples you can say you can frame it in terms of like generic decomposition operations like our follow-up questions needed here。

 yes or no， and then the model will ask query time。

 it will decide what number of follow-up questions to ask and like how to ask them to get the final answer。

So like sort of automating this process of decomposition is one of the key tools for getting language models to be better。

 so maybe the famous one of the most famous ones of this is reasoning with View is getting reasoning out of models like reasoning as a way of decomposing problems and the most famous one is this chain of fl prompting so in the prompt for the model you include like like this is for a questionansweing model so it's getting these like little math word problems and answering question and answering giving the final answer to that question and in the examples that you put in the models prompt you write out the reasoning that's highlighted in blue so rather than just directly answering Roger S5 tennis policy buys two more each can has three how many us have now instead of just directly writing 11 you write out a like little trace of reasoning of how you would get there you show your work。



![](img/7cc4ab576c6d07d722f8fefe10334bdb_108.png)

And so by putting this in the prompt， you're not teaching the model to reason here to be clear。

 you're just showing it that the like it's in the type of document where like。



![](img/7cc4ab576c6d07d722f8fefe10334bdb_110.png)

where there are explanations before answers and that causes the model to expend extra computation sort of generating intermediate thoughts that then make it easier to get the final answer by just looking at the contents of those intermediate thoughts and so this works pretty well it was especially useful for these kinds of like little mathematical tasks that involve a couple of steps。



![](img/7cc4ab576c6d07d722f8fefe10334bdb_112.png)

But it was you know， it wasn't really being done by this few shots training like it's not like the model was learning everything about reasoning from like three word problems from a third grader homework assignment。

 it's in there already and so you just need to find a way to get it to come out and so the primary the so the follow up paper。

😡，To this language models of zero reasoners just adds。

 let's think step by step to beginning of the answer。

 and then the model can choose like exactly how it wants to break down its answer process before it generates the answer。

And so clearly this capability is like already there in the model and we're just like eliciting it by careful tuning of our prompt and this let's think step by step thing works like very broadly。

 very similar phrasings also work let's think step by step to be sure we get the correct answer is a tiny little improvement。

诶。Yeah。I think that was everything I had on。

![](img/7cc4ab576c6d07d722f8fefe10334bdb_114.png)

Yeah。And then and then the last thing that you can do in addition to doing this like。Um。

 like rolling out and having the model think through its solution step by step。

 you can also just ask the model to like check its work。

So this is like a two stage prompting thing it's a little outside of what we've done so far。

 but recursive criticism and improvement includes like generating an example。

 maybe using something like zero shot， let's think step by step。

 and then once you get out an answer just like append to that。

 review your previous answer and find problems with it and then you'll generally get better results。

So I think most of this is done with the sort of instruction tuneed models that are really good at picking up on things you're asking for like you're asking it to find problems with its answer。

 but yeah this is a very like using the models to like fix their outputs is also a powerful like prompting pattern。



![](img/7cc4ab576c6d07d722f8fefe10334bdb_116.png)

Then sort of orthogonally to all of this， you can also like ensemble the results of multiple models。

 so this is a statistical fiscal model it's a probabilistic program。

 it generates different outputs on different runs。And so why not just generate like 50 different outputs and the intuition here is that the right answer should be more probable than the wrong answer and there are like maybe many ways of getting to many different wrong answers but only a few ways of getting to the one right answer so if that's the type of problem that you have ensembling is likely to work well so you take all of the models like you take the outputs like 50 different responses to the same question and then you do like majority voting。

And so you can just as you increase the number of generations， the number of members of the ensemble。

 you find that the quality increases。So that's this blue line。

Going up into the right one tip coming off after this original cell consistency paper is to like just inject randomness for greater heterogeneity。

 just like rephase the prompt a little bit， like even just like string operations to like lowercase uppercase that will like slightly change the model's behavior and in general it should keep the correct answer the same but change the wrong answers a lot。

And you can compose all these tricks that we've talked about so far。

 so you can do few shot examples that include let's think step by step and then you can ensveble them together and like you can you can put all this together and that will generally increase your performance and。



![](img/7cc4ab576c6d07d722f8fefe10334bdb_118.png)

Like just as one key example， the combination of few shot chain of thought and let's think step by step matches average human performance on this pretty hard benchmark。

 big benchmark that has a lot of difficult problems。

 I think one that it failed on was like sarcasm detection still very challenging。

 but it succeeded on a bunch of reasoning tasks， mathematical tasks， like question answering tasks。

 so yeah that's a great paper for inspiration on what can be done with this combination of tools。



![](img/7cc4ab576c6d07d722f8fefe10334bdb_120.png)

But each of them has an impact on the costs of what you're doing so you want to recognize that they can impact both like latency and compute。

 so P shot chain of thought will increase your latency because you're putting more information into for the model to run over and so it's going to take longer to generate and that's going to cost you more it's more tokens。



![](img/7cc4ab576c6d07d722f8fefe10334bdb_122.png)

A zero shot chain of thought adds fewer things to the context so it has less of an impact on latency and compute。

 so that's why lots of people have adopted it， like decomposing into subproblem is going to like generally increase the length of it。

 it's often done by with the demonstration example， so it also has an impact on latency。

 enssembling is very cool because that is no impact on latency in principle。

 like you can run all of your requests in parallel but like for every parallel request you run with an API service like that just increases your compute costs it's a little more subtle for if you're running the compute yourself。

 but it is generally going to like linearly scale compute。



![](img/7cc4ab576c6d07d722f8fefe10334bdb_124.png)

Self criticism is going to massively increase the latency because you're going to like ask the model to like fix its answer maybe multiple times。

 but it doesn't necessarily like increase the compute cost as much as something like that on。



![](img/7cc4ab576c6d07d722f8fefe10334bdb_126.png)

Okay， so I've hit two o'clock and so I'm going to skip my example with theory of mind that just demonstrates how to like combine those together。

 there's plenty I can talk about it with folks afterwards if you have questions it's in the slides on the Discord so yeah core takeaway there there's a playbook for prompt engineering it is kind of just a bag of tricks and there's not like like some hardcore math to point to that explains why this is the way to go and watch out for the fiddss of prompts especially at the character level。

🎼，🎼。🎼，🎼，🎼，🎼。

![](img/7cc4ab576c6d07d722f8fefe10334bdb_128.png)
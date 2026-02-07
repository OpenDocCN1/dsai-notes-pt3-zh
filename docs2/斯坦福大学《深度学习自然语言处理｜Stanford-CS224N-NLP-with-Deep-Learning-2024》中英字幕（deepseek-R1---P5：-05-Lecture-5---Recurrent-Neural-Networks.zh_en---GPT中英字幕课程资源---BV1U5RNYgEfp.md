# 斯坦福大学《深度学习自然语言处理｜Stanford CS224N NLP with Deep Learning 2024》中英字幕（deepseek-R1 - P5：-05-Lecture 5 - Recurrent Neural Networks.zh_en - GPT中英字幕课程资源 - BV1U5RNYgEfp

![](img/4cca8f2a26c443cc809be13c30ea7b7e_0.png)

![](img/4cca8f2a26c443cc809be13c30ea7b7e_1.png)

Okay let me get started for today so for today first of all。

 I'm going to spend a few minutes talking about a couple more neuralNe concepts。

 including actually a couple of the concepts that turn up in assignment2。😊。

Then the bulk of today is then going to be moving on to introducing what are language models and then after introducing language models we're going to introduce a new kind of neural network which is one way to build language models which is recurrent neural networks they're important thing to know about and we use them in assignment3 but they're certainly not the only way to build language models in fact probably a lot of you already know that there's this other kind of neural network called transformers and we'll get on to those after we've done recurrent neural nets talk a bit about problems with recurrent neural networks and well if I have time I'll get onto the recap before getting into the content of the class I thought I could just spend a minute on giving you the stats of who is in CS224N who's in CS224。

😊，And kind of looks like the pie charts they show in CS106A these days， except more grad students。

 I guess so the four big groups the computer science undergrads the computer science grads the underclared undergradus and the NDO grads。

 So this is a large portion of the SCPD students some of them under computer science grads。

 So that makes up about 60% of the audience and if you're not in one of those four big groups you're in the other 40% and everybody is somewhere so there are lots of other interesting groups down here。

 So you know the bright orange down here that's where the math and physics PhDs are up here。 I mean。

 interestingly we now have more statistics grad students and there are census undergrads It didn't used to be that way around in NLP classes and one of my。

😊，Favourite groups， the little magenta group down here。 These are the humanities undergrads。

 Ya humanities undergrads。😊，In terms of years it breaks down like this。

 first year grad students are the biggest group， tons of juniors and seniors and a couple of brave fro。

 there any brave Fro here today yeah？😊，Okay， welcome。😊，Yeah， so。Modern neural networks。

 especially language models are enormous This chart sort of out of date because it only goes up to 2022。

 but it's sort of actually hard to make an accurate chart for 2024 because in the last couple of years。

 the biggest language model makers have in general。

 stopped saying how large their language models are in terms of parameters。 but at any rate。

 they're clearly huge models， which have over 100 billion parameters。

 And so large and then deep in terms of very many layers。

 neural nets are a cornerstone of modern NLP systems。

 we're going to be pretty quickly working our way up to look at those kind of deep models。

 but I just sort of。😊，For starting off with something simpler， you know。

 I did just want to kind of key you in for a few minutes into a little bit of history， right。

So the last time neural nets were popular was in the 80s and 90s。

 And that was when people worked out the back propagation algorithm。

 Jeff Hinton and colleagues made famous， the back propagation algorithm that we've looked at。

 And that allowed the training of neural nets with hidden layers。 And so， but in those days。

 pretty much all the neural nets with hidden layers that were trained。

 were trained with one hidden layer。 You had the input， the hidden layer and the output。

 And that's all that there was。 And the reason for that was。😊，For a very， very long time。

 people couldn't really get things to work with more hidden layers。

 So that only started to change and the resurgence of what often got called deep learning。

 but anyway rate back to neural nets started around 2006。

 And this was one of the influential papers at the time。

 greedy layerwise training of deep neural networks by Yoo or Bennge and colleagues。

 And so right at the beginning of that paper， they observed the problem。 However， until recently。

 it was believed too difficult to train deep multilayer neural networks。 empirically。

 deep networks were generally found to be not better and often worse than neural networks with one or two hidden layers。

 Jerry to sorrowro was actually a faculty member who worked very early on autonomous driving with neural networks。

 as this is a negative results not been much report。😊，What in the machine learning literature？

So that really， you know， although people had neural networks and back propagation and currentrent neural networks we're going to talk about today that for a very long period of time you know。

 15 years or so things seemed completely stuck in that you couldn't although in theory it seemed like deep neural networks should be promising in practice。

 they didn't work and so it really then took some new developments that happened in the late 200s decade and then more profoundly in the 2010s decade to actually figure out how we could have deep neural networks that actually worked working far better than the shallow neural networks and lead into the networks that we have today and you know we're going to be starting to talk about some of those things in this class and coming up with class。

😊，And I mean， I think， you know， the tendency when you see the things that got neural networks to work much better like the。

TheThe natural reaction is to sort of shrug and be underwhelmed and think， oh。

 is this all there is to it。 This doesn't exactly seem like difficult science and in some sense。

 that's true。 They fairly little introductions of new ideas and tweaks of things， But nevertheless。

 a handful of little ideas and tweaks of things turned things around from a field that was sort of stuck for 15 years going nowhere and which nearly everyone had abandoned because of that to suddenly turning around and there being the ability to train these deeper neural networks which then behaved amazingly better as machine learning systems than other things that had preceded them and dominated for the intervening time。

 So that took a lot of time。 So what are these things。😊，One of them。

 which you can greet with a bit of a yawn， in some sense。

 is doing better regularization of neural nets。 So regularization is the idea that beyond just having a loss that we want to minimize in terms of describing the data。

 we want to， in some other ways， manipulate what parameters we learn so that our models work better。

 And so。😊，Normally， we have some more complex loss function that does some regularization。

 The most common way of doing this is what's called L2 loss where you add on this parameter squared term at the end and this regularization says。

 you know it'll be kind of good to find a model with small parameter weights。

 So you should be finding the smallest parameter weights that will explain your data well。

 and there's a lot you can say about regularization。

 these kind of losses they get talked about a lot more in other classes like CS229 machine learning And so I'm not going to say very much about it。

 This is in a machine learning theory class。 but I do just want to sort of put in one note that's sort of very relevant。

😊，To what's happened in recent neural networks work so the classic view of regularization was we needed this kind of regularization to prevent our networks from overfitting meaning that they would do a very good job at modeling the training data。

 but then they would generalize badly to new data that was shown and so the picture that you got shown was this。

 that as you train on some training data， your error necessarily goes down。😊，However。

 after some point， you start learning specific properties of things that happen to turn up in those training examples and that you're learning things that are only good for the training examples。

 And so they won't generalize well to different pieces of data， you see it test time。

 So if you have a separate validation set or a final test set you would， and you traced out the。

Error or loss on that validation or test set that after some point it would start to go up again。

 this is a quirk in my bad PowerPoint。 It's just meant to go up。

 and the fact that it goes up is then you have overfit your training data and making the parameters numerically small is meant to lessen the extent to which you overfit on your training data。

 This is not a picture that modern neural network people believe at all。 Instead。

 the picture is changed like this。 we don't believe that overfitting exists anymore。

 but what we are concerned about is models that will generalize well to different data so that when we train you know。

 so in classical statistics， the idea that you could。😊。

Train billions of parameters like large neural nets now have would be seen as ridiculous because you could not possibly estimate those parameters well and so you just have all of this noisy mess。

 but what's actually been found is that yeah， it's true you can't estimate the numbers well。

 but what you get is a kind of an interesting averaging function from all these myriad numbers。

 And if you do it right， what happens is as you go on training。

 that for a while it might look like you're starting to overfit。

 but if you keep on training in a huge network， not only your training loss continue to go down very infinitesimally。

 but your validation loss will go down as well。 And so that huge on huge networks these days we train our models。

That they overfit to the training data almost completely right so that if you train a huge network now on a training set。

 you can essentially train them to get zero loss， you know， maybe it 0。000007 loss or something。

 but you can train them to get 0 loss because you've got such rich models you can perfectly fit。

 memorize the entire training set now classically that would have been seen as a disaster because you've overfit the training data with modern large neural networks it's not seen as a disaster because providing you've done regularization well that your model will also generalize well to different data。

However， the flip side of that is normally this kind of L2 regularization or similar ones like L1 regularization aren't strong enough regularization to achieve that effect。

 And so neural network people have turned to other methods of regularization of which everyone's favorite is dropout。

 So this is one of the things that's on the assignment。 and。😊，At this point， I should。

Apologize or something because the way dropout is done。

The way dropout is presented here is sort of the original formulation。

 The way dropout is presented on the assignment is the way it's now normally done in deep learning packages。

 So there are a couple of details that vary a bit。 And let me just present the main idea here。

 and not worry too much about the details of the math。 So the idea of dropout is at training time。

 every time you are doing a piece of training with an example。

 what you're going to do is inside the middle layers of the neural network。

 you're just going throw away some of the inputs。 And so technically the way you do this is you have a random mass that you sample each time of zeros and ones。

 you do a headma product of that with the data。 So some of the data items go to0。

 And you have different mask each time。 So for the next。😊，Thing， you know。

 I've now masked out something different this time。

 And so you're just sort of randomly throwing away the inputs。

 And the effect of this is that you're training the model that it has to be robust and work well and make as much use of every input as it can。

 It can't decide that can be extremely reliant on。😊，You know。

 components 17 of the vector because sometimes it's just going to randomly disappear。

 So if there are other features that you could use instead that would let you work out what to do next。

 you should also know how to make use of those features。 So at training time。

 you randomly delete things at test time sort of for efficiency。

 but also quality of the answer you don't delete anything。 You keep all of your weights。

 but you just rescale things to make up for the fact that you used to be dropping things。😊，Okay。

 so there are several ways that you can think of explaining this。

 One motivation is often given is that this prevents feature coadaptation。

 So rather than a model being able to learn complex functions of feature 7。

8 and 11 can help me predict this， it knows that some of the features might be missing。

 So it has to sort of make use of things in a more flexible way。

 Another way of thinking of it is that there's been a lot of work on model ensembles where you can sort of mix together different models and improves your results。

 If you're training with dropout， it's kind of like your're training with the huge model ensemble because you're training with the ensemble of the power set。

 the exponential number of every possible dropout of features all at once。

 And that gives you a very good model。 So different ways of。😊，Thinking about it， I mean。

 if you've seen naive bay and logistic regression models before， you know。

 I kind of think a nice way to think of it is that it gives a sort of a middle ground between the two because for naive based models。

 you're waitinging each feature independently just based on the data statistics doesn't matter what other features are there you know。

 logistic regression weights to send the context of all the other features and。😊，With dropout。

 you're somewhere in between， you're seeing the weights in the context of some of the other features。

 but different ones will disappear at different times， but you know。

 following work that was done at Stanford by Stean Barger and others。

 that generally these days people regard dropout as a form of feature dependent regularization and he shows some theoretical results as to why to think of it that way。

😊，Okay I think we've implicitly seen this one but vectorization is the idea no four loops always use vectors matrices and tenss right the entire success and speed of deep learning works from the fact that we can do things with vectors matrices and tenss so you know if you're writing four loops in any language but especially in Python things run really slowly if you can do things with vectors and matrices even on CPU things run at least in order of magnitude faster and well what everyone really wants to move to doing in deep learning is running things on GPUs or sometimes now in neural processing units and then you're getting you know two three orders of magnitude of speed up so do always think about I should be doing things with vectors and matrices if I'm。

😊，Wting a for loop for anything that isn't some very superficial bit of input processing。

 I've almost certainly made a mistake and I should be working out how to do things with vectors and matrices and you know that's kind of things like dropout you don't want to write a for loop that goes through all the positions and set some of them to zero you want to be sort of using a vector operation with your mask。

😊，嗯。Two more I think parameter initialization I mean this one might not be obvious。

 but when we start training our neural networks in almost all cases。

 it's vital that we initialize the parameters of our matrices to some random numbers and the reason for this is if we just start with the if we just start with our matrices。

 all zero or some other constant normally the case that we have symmetry。

 so it's sort of like in this picture when you're starting on this saddle point that you know it's symmetric to the left and the right whatever forward and backwards and left and right and so you sort of don't know where to go and you might be sort of stuck and stay in the one place。

😊，I mean。Normally a way to think about is the operations as you're doing to all the elements in the matrix are sort of the same。

 So rather than having， you know， a whole vector of features。

 if all of them have the same value initially， often it's sort of like you only have one feature and you've just got a lot of copies of it。

 So to initialize learning and have things work well。

 we almost always want to set all the weights to very small random numbers。😊，And so at that point。

 you know when I say very small， we sort of want to make them an range so that they don't disappear at to zero if we make them a bit smaller and they don't sort of start blowing up into huge numbers when we multipied them by things and doing this initialization at the right scale was used to be seen as something pretty important and there were a particular methods that had a basis of sort of thinking of what happens once you do matrix multiplies that people had worked out and often used one of these was this havier initialization which was sort of working out what variance of your uniform distribution to be variant of your distribution to be using based on the sort of number of inputs and outputs of a layer and things like that the specifics of that you know I think we still used to initialize things and assignment too。

😊，But we'll see later that they go away because people have come up with cleverer methods in particular doing layer normalization。

 which sort of obviates the need to be so careful on the initialization。

 but you still need to initialize things to something。😊，OkayThen the final one。

 which is also something that appears in the second。

 the sign that I just want to say a word about was optimizes。

 So we talked about in class stochastic gradient descent and did the basic equations for stochastic gradient descent and you know to a first approximation there's nothing wrong with stochastic gradient descent and if you fiddle around enough。

 you can usually get srcchastic gradient descent actually to work well for almost any problem but getting it to work well is very dependent on getting the scales of things right of sort of having the right step size and often you have to have a learning rate schedule with decreasing step sizes and various other complications so people have come up with more sophisticated optimizes for neural networks and for complex nets。

 sometimes these same。😊，If necessary to get them to learn well and at any rate。

 they give you sort of lots of margins of safety since they're much less dependent on you setting different hyperparameter right。

 and the idea of all of the well all the methods I mentioned and the most commonly used methods is that for each parameter。

 they're accumulating a measure of what the gradient has been in the past。

 and they've got some idea of the scale of the gradient， the slope for a particular parameter。

 and then they're using that to decide how much you move the learning rate at each time step。

 So the simplest method that was come up with this one called Edegrad。

 if you know John Duuchy and E he was one of the coinventors of this。

 you it's simple and nice enough， but it tends to stall early。

 then people came up with different methods。 Adam's the one that's on assignment to。

 it's a really good， safe place to start。😊，But in a way。

 sort of our word vectors have a special property because of their sparseness that you know you're very sparsely updating them because particular words only turn up occasionally so people have actually come up with particular optimizes that sort of have special properties for things like word vectors and so these ones with the W at the end can sometimes be good to try and then you know again。

 there's a whole family of extra ideas that people have used to improve optimizes and if you want to learn about that。

 you can go off and do an optimization class like convex optimization。

 but theirre ideas like momentum and nest of acceleration and things like that and all of those things people also variously try to use but atom is a good name to remember if you remember nothing else。

😊，Okay， that took longer than I hoped， but I'll get on now to language models。 Okay。

 language models so。😊，You know， in some sense， language model is just two English words。

 But when in NLP， we say language models， we mean that it's a technical term that has a particular meaning。

 So the idea of a language model is something that can predict。Well。

 what word is going to come next or more precisely it's going to put a probability distribution over what words come next so the students open there。

 what words are likely to come next。😊，Bags。Slaptop， notebook， notebooks， Yes， I have some of those。

 at least， okay。😊，Yeah， I mean， so right so so these are kind of likely words。

 And if on top of those， we put a probability on each one， then we have a language model。

 So formally， we've got a context of preceding items。

 we're putting a probability distribution over the next item which means that the sum of the estimates of this for the items in the vocabulary will sum to one。

 And if we've defined a P like this that predicts probabilities of next words。

 that is called a language model。😊，As it says here。

 an alternative way that you can think of a language model is that a language model is a system that assigns a probability to a piece of text and so we can say that a language model can take any piece of text and give it a probability and the reason we can do that is we can use the chain rule So I want to know the probability of any stretch of text I say given my previous definition of language model easy。

 I can do that probability of x1 with a null preceding context times the probability of x2。

 give an x1 etc along I can do this chain rule decomposition and then the terms of that decomposition a precisely what the language model as I defined that previously provides okay so language model are this essential technology。

😊，For NLP， just about everything from the simplest places forward where people do things with human language and computers。

 people use language models， in particular， you know they weren't something that got invented in 2022 with chat GT language models have been central to NLP at least since the 80s。

 the idea of them goes back to at least the 50s So any time you're typing on your phone and it's making suggestions of next words。

 regardless of whether you like those suggestions or not。

 those suggestions are being generated by a language model， traditionally a compact。

 not very good language model so it can run sort of quickly and very little memory in your keyboard application if you go on Google and you start typing some stuff and it's telling you stuff that could come after it。

To complete your query， well again， that's being generated by a language model。😊。

So how can you build a language model？ So before getting into your language models。

 I've got just a few slides to tell you about the old days of language modeling。

 So this is sort of how language models were built from 1975 until。😊，effectively around about 2012。😊。

We want to put probabilities on these sequences and the way we're going to do it is we're going to build what's called an ngram language model。

 And so this is meaning we're going to look at short words subsequs and use them to predict。

 So N is a variable describing how short of the word sequences that we're going to use to predict。

 So if we just look at the probabilities of individual words。 We have a unigram language model。

 if we look at probabilities of pairs of words bygram language model。 probabilities of three words。

 trigram language models， probabilities of more than three words they get called four gra language models。

5 gra language models，6 gra language models。 So for people with a classics education。

 this is horrific， of course， in particular， not even these ones are correct because。😊。

Graham is Greek root。 So it should really have Greek numbers in front here So you should have monograms and diagrams。

 And you know， actually， so the first person who introduced the idea of Ngram models was actually Claude Shannon when he was working out information theory。

 the same guy that did cross entropy and all of that。 And if you look at his 1951 paper。

 he uses diagrams。 But the idea died about there。 and everyone else。

 this is what people say in practice。 it's kind cute， I like it。 And I know practical notation。

 So to build these models， the idea is， look， were just going to count how often different Ngrams appear in text and use those to build our probability estimates。

 And in particular our trick is that we make a markov assumption。

 so that if we're predicting the next word based on。😊，Long context。

 we say tell you what we're not going to use all of it。

 We're only going to use the most recent n minus1 words so we have this big context and we throw most of it away And so if we're predicting word X T plus one based on simply the preceding n minus one words well then we can make the prediction using n gras。

😊，' let's whatever it is， if we use n is3 would have a trigram here and normalized by a bigram down here。

 and that that would give us relative frequencies of the different terms。😊。

So we can do that simply by counting how often ngrams occur in a large amount of text and simply dividing through by the counts。

 and that gives us a a relative frequency estimate of the probability of different continuations。😊。

Does that make sense。 Yeah，'s a way to do it。 Okay。

 so suppose we're learning a for gram language model， right。

 And we've got a piece of text as the proctor started the clock。 The students open there。

 So well to estimate things， we are going to throw away all， but the precing three words。

 So we're going to estimate based on students open there。

 And so we're going to work out the probabilitybabilities by looking for counts of students open there W and counts of students open there。

 So we might have in a corpus that students open there occurred a thousand times。

 Student open their books occurred 400 times。 And so we'd say the probability estimate is simply 0。

4 for books。 If exams occurred 100 times the probability estimate is 0。1 for exams。😊，um。

And while you can sort of see that this is bad。 It's not terrible because if you are going to try and predict the next word in a simple way。

 looking at the immediately prior words， are the most helpful words to look at。

 but it's clearly sort of primitive because you know。

 if you had known that the prior text was as the prop to start of the clock。

 that makes it sound likely that the words should have been exams。

 where since you're estimating just based on students open theirs， Well。

 you'd be more but likely to choose books because it's more common。

 So it's a kind of a crude estimate， but it's a decent enough place to start it's a crude estimate that could be problematic in other ways。

 I mean， why else might we kind of get into troubles by using this as our probability estimate。Yeah。

Too many。So there are a lot of ngrams。 Yeah， so there are a lot of words and therefore there are a lot of lot of ngrams。

 Yeah so that's a problem。 We'll come to it later。 anything else maybe up the back。

 like the word that might not even show up in the training data you might just have a counsel for that yeah so so if we're counting over any reasonable sized corpus。

 there are lots of words that we just are not going to have seen。

 right that they never happen to occur in the text that we counted over， you know。

 so if you start thinking students open there， you know。

 there are lots of things that you could put there， you know。

 students open their accounts or if the students are doing dissections in a biology class。

 maybe students open their frogs。 I don't know， you know that there are lots of words that in some context。

 you know would actually be possible and lots of them。😊。

That we won't have seen and so it give them a probability estimate of zero and that tends to be an especially bad thing to do with probabilities because once we have a probability estimate of0 any computations that we do that involve that will instantly go to zero so we have to deal with some of these problems So for that sparsy problem right yeah that we could have the word never occurred in the numerator and so simply done we get a probability estimate of 0 the way that was dealt with was that people just hacked the count a little to make it nonzero so there are lots of ways that are explored but the easiest way is you just sort of added a little delta like you know 0。

25 to count So things that you never saw got to count of 0。

25 and total and things you saw once got count of 1。

25 and then there are no zeros anymore everything is possible。😊，Um。

 you could think then there's a second problem that wait you might never have seen stupid students open there before。

 and so that means your denominator is just。😊，Underfin and you don't have any counts in the numerator either。

 So you sort need to do something different there。 And the standard trick that was used then was that you did back off。

 So if you couldn't estimate words coming after students open there。

 you just worked out the estimates for words coming after open there。

 And if you couldn't estimate that， you just use the estimate of words coming after there。

 So you use less and less context until you could get an estimate that you could use。😊，But you know。

 something to note is that we've got these conflicting pressures now so that on the one hand。

 you know， if you want to come up with a better estimate that you would like to use more context。

 I have a larger Ngram， but on the other hand， as you make use more，😊，More conditioning words。 Well。

 the storage size problem someone mentioned gets worse and worse because the number of n grams that you have to know about is going up exponentially with the size of the context。

 but also your sparseness problems are getting way。

 way worse and you're almost necessarily going to be ending up seeing zeros。 And so because of that。

 you know， in practice where things tended to sort of max out was 5。 and occasionally。

 people use 6s and 7 gra。 But most of the time， you know。

 between the sort of sparseness and the cost of storage 5 gra was the largest thing people dealt with。

 so。A famous resource from back in the 200s decade that Google released was Google Ngrams。

 which was built on a trillion word web corpus and had counts of Ngrams。

 and it gave counts of n gras up to n equals 5。 and that is where they stopped。😊，Okay。

 well we've sort of said the storage problem， the storage problem is。

 well to do this you need to store these counts， the number of counts is going up exponentially in the amount of context size。

😊，Okay， but， you know， what's good about Ngram language models。 They're really easy to build。

 You can build one yourself in a few minutes when you've want to have a bit of fun on the weekend。

 you know， all you have to do is start sort of storing these counts for Ngrams and you can use them to predict things。

 So you know if at least if you do it over a small corpus， like a couple of million words of text。

 you know， you can build an Ngram language model in seconds on your laptop or you have to write the software。

 Okay， a few minutes to write the software， but building the model take seconds， because， you know。

 there's no training in your network， all you do is count how often Ngrams occur。

 And so once you've done that， you can then run an Ngram language model to generate text， you know。

 we could do text generation before chat G， right So if I have a trigram language model。😊。

I can start off with some words today there， and I could look at my stored n grams and get a probability distribution over next words and here they are。

 you know note the strong patterning of these。😊，These。Probabilities because remember。

 they're all derived from counts， right， that are being normalized。 So really。

 these are words that occurred once。 These are words that occurred twice。

 These are words that occurred four times in this context， right， So they're sort of， in some sense。

 crude when you look at them more carefully。 But so what we could do is then at this point， you know。

 we roll a die and get a random number from 0 to one。

 And we can use that sample from this distribution。😊，Sorry， yeah。

So we sample from this distribution and so that if we sort of generate sort of as our random number。

 something like 035， if we go down from the top with say okay we've sampled the word price today the price and then we repeat over。

 we condition on that， we probability distribution of the next word。

 we generate a random number and use it to sample from the distribution， we can say generate 0。

2 and so we choose of， we now condition on that， we get a probability distribution we generate a random number which is 0。

5 or something and so we get gold coming out and we can say today the price of gold and we can keep on doing this and generate some text and so here's some text generated from2 million words of training data using a trigram。

😊，Language model today， the price of gold per ton while production of shoe lasts and shoe industry。

 the bank intervened just after it considered and rejected an IMF demand to rebuild depleted European stocks September 3 in primary 76 cents a share now。

Okay， that text isn't great。 But， you know， I actually want people to know。

 be in a positive mood today。 And， you know， actually， it's not so bad， right。

 It's sort of surprisingly grammatical。 I mean， in particular， like I lowercased everything。

 So this is the IMF that should be capitalizeized of the international Monet fund， right， you know。

 there are big pieces of this that even make sense， right。

 The bank intervened just after it considered and rejected an IMF demand。 You know。

 that's pretty much making sense as a piece of text。 right， So it's。😊，Mostly grammatical。

 It looks like， you know， English text。 I mean， it， it makes no sense， right。

 It's sort of really incoherent。 So there's work to do。 But， you know。

 what was already you could see there's even these simple Ngram models used could。😊。

From a very low level you could kind of approach what text in human language worked like in from below and you know I could easily make this better even with the Ngram language model because you know rather than 2 million words of text if I trained on 10 million words of text would be better if I then rather than a trigram model could go to a four gra model get better and you'd sort of start getting better and better approximations of text and so this is essentially what people did until about 2012 and you know really the same story that people did tell today that scale will solve everything is exactly the same story that people used to tell in the early 2010s with these Ngram language models if you weren' getting a good enough results with your 10 million words of text and a trigram language model the answer was。

😊，That if you had 100 million words of text and a four gram language model you'd do better and then if you had a trillion words of text and a five gram language model you'd do better and gee。

 wouldn't it be good if we could collect 10 trillion words of text so we could train an even better Ngram language model。

 same strategy but it turns out that sometimes you can do better with better models as well as simply scale and so things got reinvented and started again with building neural language models。

😊，So how can we build a neural language model So you know。

 we've got the same task of having a sequence of words and we wanted to put a probability estimate over what word comes next And so the simplest way you could do that which you'll hopefully if all have thought of because it connects what we did in earlier classes。

 Look， we already had this idea that we could have represent a context by the concatenation of some word vectors and we could put that into a neural network and we could use that to predict something and in the example I did in the last couple of classes。

 what we used it to predict was is the center word。

 a location or not a location just a binary choice， but that's not the only thing we could predict。

 we could have predicted lots of things with this neural network。

 we could have predicted whether the piece of text was。😊，Positive or negative。

 we could have predicted whether it was written in English or Japanese。 you know。

 we could predict lots of things。 So one thing we could choose to predict is we could choose to predict what word is going to come next after this window of text。

 We'd have a model just like this one， apart from up the top instead of doing this binary classification。

 We'd do a many， many way classification over what is the next word that is going to appear in the piece of text。

 And that would then give us a neural language model in particular。

 give us a fixed window neural language model。😊，So that we do the same markoff assumption trick of throwing away the further back context and so for the fixed window we'll you know use word embeddings which you can concatennate we'll put it through a hidden layer and then we'll take the output of that hidden layer multiply it by another layer say and then put that through a softm and get an output distribution and so this gives us sort of a fixed window neural language model and you know apart from the fact that we're now doing a classification over many many。

 many classes， this is exactly like what we did last week so it should look kind of familiar it's also kind of like what you're doing for assignment too and so this is essentially the first kind of neural language model that was proposed。

😊，どス？So in particular， Yoa Benggio really sort of right at the beginning of the 21st century suggested that you could do this。

 that rather than using an Ngramm language model， you could use a fixed window neural language model and you know even at that point he and colleagues were able to get some positive results from this model but you know at the time it wasn't widely noticed。

 it didn't really take off that much and you know it was sort of for a combination of reasons when it was only a fixed window it was sort of not that different to Ngrams in some sense。

 and although the neural network could give better generalization。

 it could be argued rather than using counts I mean in practice you know neural nets were still hard to run without GPUs and people felt and I think in general this was the case that you could get more。

😊，By doing the scale story and collecting your Ngram counts on hundreds of billions of words of text。

 rather than trying to make a neural network out of it。

 And so it didn't really sort of especially take off at that time。 But， you know， in principle。

 it seemed a nice thing。 you know， got rid of the sparsy problem。 It got rid of the storage costs。

 You no longer have to store all observed Ngrams。 You just have to store the parameters of your neural network。

 But it didn't solve all the problems that we'd like to solve。 So in particular。

 we still have this problem of the markoff assumption that we just using a small fixed context beforehand to predict from。

And there are some disadvantages to enlarging that window and you know there's no fixed window that's ever big enough。

😊，There's there's another thing that if you look technically at this model that might sort of make you suspicious of it。

 which is， you know when we have words in different positions that those words in different positions will be treated by completely different subparts of this matrix W so you might think that you know okay for predicting that books comes next。

 you know the fact that this is a student is important but it doesn't matter so much exactly where the word student occurs right。

 you know the context could have been the students slowly open there and it's still the same students we've just got a bit different linguistic structure where this W matrix will be using completely separate parameters to be learning stuff about student here。

😊，A student in this position。 so that seems kind of inefficient and wrong。

And so that suggested that we kind of need a different kind of neural architecture that can process any length of import and can use the same parameters to say。

 hey I saw the word student， that's evidence that things like books exams。

 homework will be turning up， regardless of where it occurs。

 and so that then led to exploration of this different neural network architecture called recurrent neural networks。

 which is what I'll go on to next， but before I do is everyone basically okay with what a language model is。

 yeah， no questions。😊，Okay， were currentrent neural networks。😊，So。😊。

Recurrent neural networks is a different family of neural networks。

 so effectively in this class we see several neural network architectures。😊，So in some sense。

 the first architecture we saw was word to Vck， it's a sort of a very simple encoded decoder architecture。

 the second family we saw was，😊，Feed forward networks or fully connected layer。

 classic neural networks。 And the third family we're going to see is recurrent neural networks。

 which have different kinds。 And then we'll go on and go on to transformer models。

 Okay so the idea of a recurrent neural network is that you've got one set of weights that are going to be applied through successive moments in time。

 a successive positions in the text。 And as you do that。

 you're going to update the parameters as you go。 we'll go through this in quite a bit of detail。

 But you know， here's the idea of it。 So we've got the students open there。

 and we want to predict with that。 And the way that we're going to do it。😊，Okay。

 I've still got four words in my example so I can put stuff down the left side of the slide。

 but there could have been 24 words with recurrent neural networks because they can deal with any length of context Okay so as before our words start off as just words or one hot vectors and we can look up their word embeddings just like before。

😊，Okay but now to compute probabilities for the next word we're going to do something different so our hidden layer is going to be recurrent and by recurrent it means we're going to sort of change a hidden state at each time step as we proceed through the text from left to right so we're going to start off with an80 which is the initial hidden state which can actually just be all zeros and then at each time step what we're going to do is we're going to multiply the previous hidden state by a weight matrix we're going to take a word embedding and multiply it by a weight matrix and then we're going to sum the results of those two things and that's going to give us a new hidden state so that hidden state will then sort of store a memory of everything that's being seen。

😊，So far so we'll do that and then we'll continue along so we'll multiply the next word vector by the same weight matrix WE。

 we store previous multiply the previous hidden state by the same weight matrix WH and we add them together and get a new representation。

😊，I've only sort of said this bit。 So I've left out a bit commonly there are two other things you're doing。

 Youre adding on a bias term because we usually separate out a bias term and you're putting things through a- nonlinearity。

 So I should make sure I mention that。 And for re currentrent neural networks most commonly this non nonlinearity has actually been the10 H function。

 So it's sort of balanced on the positive and negative side。

 And so you keep on doing that through each step。 And so the idea is once we've gone to here。

 this H force hidden state is a hidden state in some sense has read the text up until now it's seen all of the students open there。

 And if the word students occurred in any of these positions。

 it will have been multiplied by the same WE matrix and added into the hidden state。

 So it's kind of got a cleaner low parameterameter way of incorporating in the information that it's seen。

 So now。😊，ant to predict the next word and to predict the next word I'm then going to do based on the final hidden state the same thing I did kind of thing I did before so I'm going to multiply that hidden state by a matrix and add another bias and stick that through a softm and use that to sample from that softm well the softm will give me a language model a probability over next words and I can sample from it to generate the next word。

😊，That makes sense。Okay， recurrent neural networks。😊，Okay， so for recurrent neural networks。

 we can now process any length of preceding context and we'll just put more and more stuff in our hidden state。

 So our computation is using information from many steps back。

 our model size doesn't increase for having a long context， right you know。

 we have to do more computation for a long context。

 But our representation of that long context just remains this fixed size hidden vector H of whatever dimension it is。

 So there's no exponential blowout anymore。 There's the same weight supply in every time step。

 So there's a symmetry and how inputs are processed。 there are some catches。

 The biggest catch and practice is that recurrent computation is slow。

 So for the feed forward layer we just had。😊，You know our input vector， we multiply it by matrix。

 we multipied it by matrix， however many times and then at the end we're done whereas here we've sort of stuck with this sequentiality that you have to be doing one hidden vector at a time。

 In fact， this is going against what I said at the beginning of class because essentially here you're doing a full loop you're going through for time equals1 to t and then you're generating in term each hidden vector and that's one of the big problems with R andNs that have led them to fall out of favor。

😊，There's another problem that we'll look at more is that in theory this is perfect。

 you're just incorporating all of the past context in your hidden vector in practice it tends not to work perfectly because you know although stuff you saw back here is in some sense still alive in the hidden vector as you come across here that your memory of it gets more and more distant and it's the words that you saw recently that dominate the hidden state Now in some sense that's right because the recent stuff is the most important stuff that's freshest in your mind。

 you know it's the same with human beings they tend to forget stuff from further back as well but RNs especially in the simple form that I've just explained。

 forget stuff from further back rather too quickly and will come back to that again into。😊。

Da's class。Okay， so for training an RNN language model。

 the starting off point is we get a big corpus of text again and then we're going to compute for each time step a prediction of the probability of next words and then there's going to be an actual next word and we're going to use。

 you know that is the basis of our loss。😊，So our loss function is the crossenttropy between the predicted probability and what the actual next word that we saw is which again as in the example I showed before is just that the negative log likelihood of the actual next word ideally you'd like to predict the actual next word of probability one which means the negative log of one would be0 and there'd be no loss and in practice if you give it an estimate of 0。

5 there's only a little bit of loss and so on and so to get our overall objective function we work out the average loss。

 the average negative log likelihood of predicting each word in turn so showing that as pictures if our corpus is the students open their exams we're first of all going to be trained to predict you know what comes after。

😊，The and。We will predict some word with different probabilities and then we'll say oh the actual next word is students okay you gave that a probability of 0。

05 say because all we know was the first word was the okay there's a loss for that the negative log probe given to students we then go on generate the probability estimate over the next words and then we say well the actual word is opened what probability estimate did you give to that we get a negative probability loss keep on running this along and then we sum all of those losses and we average them per word and that's our sort of average per word loss and we want to make that as small as possible and so that's our training mechanism and it's important to。

😊，To notice that， you know， for generating this loss， we're not just doing free generation。

 we're not just saying to the model。ll go off and generate a sentence。

 What we're actually doing is that each step， we're effectively saying， okay。

 the prefixes the students opened。 what probability distribution do you put on next words after that。

 generate it with our current neural network， and then say ask for the actual next word。

 What probability estimate did you give to there and that's our loss。

 But then what we do is stick there into our current neural network， the right answer。

 So we always go back to the right answer， generate probability distribution for next words and then ask。

 okay， what probability did you give to the actual next word exams。 and then again。

 we use the actual next word。 So we do one step of generation。

 then we pull it back to what was actually。😊，generated was what was actually in the text and then we asked it for guesses over the next word repeat forever and so the fact that we don't do free generation。

 but we pull it back to the actual piece of text each time makes things simple because we're sort of know what actual author used for the next word and that process is called teacher forcing and so the most common way。

😊，To train language models is using this kind of teacher forcing method I mean it's not perfect in all respects because you know。

 we're not actually exploring different things the model might want to generate out of its own and seeing what comes after them we're only doing tell me the next word from some human generated piece of text。

😊，Yeah。Okay， so that's how we get losses and then after that we want to as before use these losses to update the parameters of a neural network。

😊，Okay and how do we do that Well in principle you know we just have all of the texts that we've collected which you could think of as just a really long sequence of okay we've got a billion words of text here it is right so in theory you could just run your recurrent neural network over your billion words of text updating the context as you go but that would make it very difficult to train a model because you'd be accumulating these losses for a billion steps and you'd have to store them and then you'd have to store hidden states so you could update parameters and it just wouldn't work so what we actually do is we cut our training data into segments of a reasonable length and then we're going to sort of run our recurrent neural network。

😊，On those segments。 And then we're going to computer loss for each segment。

 And then we're going to update the parameters。Of the recurrent neural network based on the losses that we found for that segment。

 I describe it here as the segments being sentences of documents。

 which seems a linguistically nice thing。 it turns out that in recent practice when you're wanting to scale most efficiently on GPUs。

 people don't bother with those linguistic niceties， they just say a segment is 100 words。

 just cut every 100 words and the reason why that's really convenient is you can then create a batch of segments。

 all of which are 100 words long and stick those in a matrix and do vectorize training more efficiently and things go great for you。

😊，Okay， but there's still a few more things that we need to know to get things to work great for you。

 Ill try and get a bit more through this before today ends。

 so we sort of need to know about how to work out the derivative of our loss with respect to the parameters of our recurrent neural network and the interesting case here is you know these WH parameters are sort of being used everywhere through the neural network at each stage as are the WE1。

 So they appear at many places in the network So how do we work out the partial derivatives of the loss with respect to the repeated weight matrices and the answer to that is oh it's really simple you can just sort of pretend that those WHs and E。

😊，Each position are different and work out the partials with respect to them at one position and then to get the partials with respect to WH。

 you just sum whatever you found in the different positions。😊，And so。😊。

That is sort of okay the gradient respect to repeated ways is the sum of the gradient with respect to each time it appears。

 and the reason why that is it sort of follows what I talked about in lecture 3 that we talk or you know you can also think about it in terms of what you might remember from you know。

 multivariable chain rules， but you know the way I introduced in lecture 3 is the gradient sum at outward branches。

 And so what you can think about it in a case like this is that you've got W H matrix which has been copied by identity to W H1。

 WH2， WH3， WH4， etc at each time step and so since those are identity copies they have。😊。

Partial derivative with respect to each other of one and so then we apply the multivariable chain rule to these copies and so we' then got an outward branching node and you're just summing the gradients to get the total gradient of each time for the matrix。

😊，Okay。Yeah I mean there's one other trick that's perhaps worth knowing。

 I mean if you've got sort of segments that' are 100 long a common speedup is to say oh maybe we don't actually have to run back propagation for 100 time steps。

 maybe we could just run it for 20 time steps and stop which is referred to as truncated back propagation through time I mean in practice that tends to be sufficient note in particular you're still on the forward pass updating your hidden state using your full context but in the back propagation you're just sort of cutting it short to speed up training。

😊，Okay so just as I did before with an Ngram language model。

 we can use RN language model to generate text and it's pretty much the same idea except now we're sort of rather than just using counts of Ngrams we're using the hidden state of our neural network to give us the input to a probability distribution that we can then sample from so I can start with the initial hidden state I can use the start of sentence symbol I mean the example I had before I started immediately with the hoping that I was less confusing the first time but what you should have asked is wait a minute where did the v come from so normally what we actually do is use a special start of sequence symbol like this。

😊，Angle bracketed S。 And so we sort of feed it in as a pseudo word， which has a word embedding。

 And then we based on this， we'll be generating first words of the text。

 So we end up with some representation from which we can sample and get the first word。😊。

So now we don't have any actual text so what we're going to do is take that generated word that we generated and copy it down as the next input and then we're going to run a next stage of neural network sample from the probability distribution and next word favorite。

 copy it down as the next word of the input and keep on generating and so this is referred to as a rollout that you're kind of continuing to roll the dice and generate forward and generate a piece of text and so。

😊，And normally you want to stop at some point and the way we can stop at some point is we can have a second special symbol。

 the angle brackets slash S which says end of your sequence so we can generate an end of sequence symbol and then we can stop and so using this we can sort of generating pieces of text and essentially you know this is exactly what's happening if you use something like chatEptT right that the model is a more complicated model that we haven't yet gotten to but it's generating the response to you by doing this kind of process of generating a word at the time treating it as an input and generating the next word and generating this sort of rollout and that's why and it's done probabilistically so if you do it multiple times you can get different answers we haven't yet gone to chat EptT but we can have a little bit of fun。

😊，Um， so you can take this simple recurrent neural network that we've just built here and you can train it on any piece of text and get it to generate stuff。

😊，So for example I can train it on Barack Obama's speeches so that's a small corpus right you know he didn't talk that much right。

 I've only got a few hundred thousand words of text it's not a huge corpus I'll just show this and then I can answer the question but you know I can generate from it and I get something like the United States will step up to the cost of a new challenges of the American people that will share the fact that we created the problem。

😊，They were attacked and so that they have to say that all the tasks of the final days of war that I will not be able to get this done。

Yeah， well， maybe that's slightly better than my Ngram language model still not perfect you might say。

 but somewhat better， maybe did you have a question？😊，Yeah， so。That's right like。好那款常K的。

Just that person kind of like。Limitation on like how much we can like produce and I still have some。

Yeah like。第三。规定个。So yeah， so I suggested we're going chunk the chunk the text into 10 word units。

 So you know， that's the limit of the amount of prior context that we're going to use。 So I mean。

 that's a fair amount，100 words。 that's typically several sentences。

 but to the extent that you wanted to know even more about the further back context you wouldn't be able to。

 And you know， certainly that's one of the ways in which modern large language models are using far bigger context than that。

 they're now using thousands of words of prior context。 Yeah， absolutely it's a limit on how much。😊。

Far back context。 So in some sense， actually， even though in theory。

 a current neural network can feed in an arbitrary length context， as soon as I say， oh。

 practically we cut it into segments， you know， actually。

 that means we are making a mark off assumption again。

 And we're saying the further back context doesn't matter。Yeah。😊，Okay， a couple more examples。

 So instead of Barack Obama， I can feed in Harry Potter， which is a somewhat bigger corpus of text。

 actually， and generate from that。 And so I can get sorry， Harry shouted panicking。

 I'll leave those brooms in London， Are they No idea。

 said nearly headless neck casting low cliffs by Cedric carrying the last bit of treacle charms from Harry's shoulder。

 And to answer him the common room perched upon it。

 forearms held a shining knob from when the spider hadn't felt it seemed。 He reached the teams too。😊。

Well， there you go。 You can do other things as well。😊。

So you can train it on recipes and generate a recipe。

 This one's a recipe I don't suggest you try and cook。

 but it looks sort of like a recipe if you don't look very hard chocolate ranch。

 barbecue categories game casseroles cookies， cookies， yield six servings。

 two tablespoons of Pars and cheese chopped one cup of coconut milk and three eggs beaten。

 place each pasta over layers of lumps， shape mixture into the moderate oven and simmer until firm。

 serve hot in bodied fresh mustard orange and cheese combine the cheese and salt together。

 the dough in a large skillet and ingredients and stir in the chocolate and pepper Yeah。

 it's not exactly a very consistent recipe。😊，When it comes down to it。

 it sort of has a language of a recipe that it's absolutely maybe if had scaled it more and had a bigger corpus。

 it would have done a bit better， but definitely not using the ingredients there are。

 Let's see it's almost time today。 So maybe about all I can do is。😊，I can do one more fun example。

 And then after that。 yeah， I probably should do that bit at the start next time。

 So as a variant of building RN language models， I mean， so far， we've been building them over words。

 So you know， token time steps over which you build it as words。 I mean， actually。

 you can use the idea of recurrent neural networks over any other size unit。

 and people have used them for other things。 So people have used them in bioinformatics for things like DNA for sort of having gene sequencing or protein sequencing or anything like that。

 But even staying with language instead of building them over words。

 you can build them over characters So that my I'm generating at a letter at a time rather than a word at a time。

😊，And so that can sometimes be useful because it allows us to sort of generate things that sort of look like words and perhaps have the structure of English words and and so similarly。

 there are other things that you can do So before I initialize the hidden state， I said。

 you just have an initial hidden state， you can make it zeros if you want Well sometimes we're going to build a contextual RN where we can initialize the hidden state with something else。

 so in particular I can initialize the hidden state with the RGB values of a color and so I can have initialize the hidden state with the color and generate character at a time the name of paint colors and I can train a model based on a paint company's catalog of names of colors and。

😊，RGB of their colour。 And then I can give it different， different paint colour。

 and it'll come up with names for them。 And it actually does an excellent job。

 This one worked really well。 Look at this。 This one here is ghasty pink。😊，Power gray， nal tan。

 boco white， horrible gray， Home star brown。 Now， couldn't you just imagine finding all of these in a paint catalog。

 I mean， some of them are there's some really good ones over here in the bottom。 right。

 This color here is dope。 And then this stone of blue， purple sim。😊，Stinky be。And thirdly。

 now I think I've got real business opportunity here in the paint company market for my recurrent neural network。

 Okay， I'll stop there for today and do more of the science of neural networks next time。😊。



![](img/4cca8f2a26c443cc809be13c30ea7b7e_3.png)
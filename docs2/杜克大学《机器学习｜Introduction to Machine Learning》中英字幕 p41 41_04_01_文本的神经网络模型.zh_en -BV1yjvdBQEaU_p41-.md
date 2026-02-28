# 杜克大学《机器学习｜Introduction to Machine Learning》中英字幕 p41 41_04_01_文本的神经网络模型.zh_en -BV1yjvdBQEaU_p41-

So now that we have introduced。This concept。Of word vectors or this concept of word to vector where we're going to take every word and we're going to map it to a vector and we're going to do analysis in the space of these word vectors and so again the key idea here is that we take these words which are just language a part of a vocabulary and once we have mapped every word to a vector。

 we can then do analysis we can we can do analysis on a computer， for example。

 so the key now we want to spend some time。On how we actually could learn these word vectors。

 how we could learn the mapping from a given word to a vector。

So there are many ways that this can be done， and our goal here is to learn the codebook。

 The codebook is a set of vectors。Where we have a mapping from every word in the vocabulary to a vector。

And so our goal is to learn this codebook and we would particularly like to do it in a way for which we do not need label data。

 so that means that we do not need humans to read the documents a priori and assign labels to them and so we're going to assume access to a large or massive corpus of unlabeled documents。

 so just the raw documents。And so the idea is that if we learn these word embeddings or these word vectors。

We would like to do so in such a way that each word in a given document is predictive of the presence of surrounding words。

 So most people， if they understand language， if you gave them a particular word。

They could tell you words that are related to that word and therefore words that might be in the near vicinity of that word in a particular document。

 and so that's just the fundamental concept and so what we are going to do is build models such that those models are capable of taking a given word and making predictions about surrounding words。

 the way that this will be done will be by utilizing these word vectors and therefore good word vectors are word vectors for which using those vectors we're capable of predicting the words that might be surrounding a given word so that will actually be the fundamental concept that we're going to use to learn these word embeddings or these word vectors。

So again， the idea is we want to seek the capacity to predict words surrounding given word。

 so for example， let's consider word W subN in a given document。

 so W subN just corresponds to the n word in the document and let's let C WN the C parentheses WN represent the code or the vector。

Associated with with word WN。 And so as we've discussed elsewhere。

 we're going to assume that this is an M dimensional vector。

 an M dimensional code associated with that word。And so if our codes are good。

 if the vectors that we have for our vocabulary are good， then using that vector。

 I should be able to predict words that are surrounding it and the way that we can learn that is we can look at a corpus we can look at each word in that corpus and we can look at the words around each word and what we would like to do is to learn word vectors in such a way that using those word vectors we can effectively predict which words might be in the vicinity of any given word。

 so the way that we're going to do this is using the tools that we have already developed。

 particularly the multilayer perceptron。So let's consider word WN。

And it's going to be composed of an m dimensional vector。

 so CWN is the code associated with the word WN in C sub 1。

 C sub2 through C sub M correspond to the M components。Of that vector。

 those M components of the vector of the， of the word vector are going to be the input。

to a multilayer perceptron and so as we've studied elsewhere， what we do is we take the input vector。

 the input vector here corresponds to the vector the word vector of word W sub n and we're going to map that to a hidden vector which is d dimensional H1 through HD。

 a d dimensional latent vector and now what we want to do is to take that d dimensional hidden。

Vctor and then make a prediction about what words might be in the vicinity of word W sub n。

And so way so just to remind a little bit about the notation and a little bit about the multilayer perceptron。

 the way that this mapping from the word vector C1， C2 through CM to the hidden vector H1 through HD。

 the way this is done is that each of the components of the vector C1。

 C2 through CM is multiplied by weight， so W1 J corresponds to the weight between component1 of the vector C1。

 and the J hidden variable， so H subj， so we multiply each component of the vector by a weight。

 we add a bias associated with the J hidden variable， B subj。And then that- so we take the code。

 take each element of the code and multiply it by a weight。We then。Add a bias。

And then we add this ab and then that product and then sum is sent through aline function。

 which we represent by G elsewhere we have looked at situations where G might be represented by a sigmoid function。

 but there are other examples， for example， hyperbolic， tangent and others that can be used for G。

And so use to just simplify our notation that we'll use elsewhere， we say that the hidden variables。

A represented by the code C which represents the vector associated with the word multiplied by all of the weights。

 which are represented here by W adding a bias B and then sending that through a nonlinear function G which ultimately gives us our hidden variables this is the first layer in what we'll see is a multilayer perceptron so examples that one might consider for that nonlinear function so G this is called a hyperbolic tangent。

 this is just one example， so what it does is it maps a real variable X to a number between minus1 and1 and so what we're doing here concisely is we're taking the code C associated with the word vector we multiply it times a matrix。

WWe add a bias， that process gives us a vector， that vector， each component of that vector。

 each component of that vector is sent through a nonlinear function。

 which is here represented by the hyperbolic tangent。

 which then gives us our latent or hidden variable H。And so this function， the hyperbolic tangent。

 operates point wise or separately on each component of the vector。And so this looks familiar。

 this is our multilayer perceptron， The output of the hidden variables H are then multiplied by another set of weights which are represented by the matrix U and then ultimately at the top of this network we're going to have v minus1 outputs where v recall is the size of our vocabulary and as we'll discuss in a moment this will become clear why we have v minus-1 outputs。

 but y1 through y v minus1 correspond to v minus1 numbers which are the output of this multilayer perceptron and then just to kind of highlight how this is done in the same way that we did before。

 if we take each of the hidden units H if we look at the hidden vector which has d components。

 each component，Multiplied by weights。We then add a bias。And then so to write this concisely。

 we take U， which is our matrix of weights。We have a hidden vector H， we add the bias。

 and then this gives us y。 This is just a concise way of representing this。

And so now what we want to do is to use this model。To quantify the probability of word W I。

 word WI could be any。Word in a vocabulary， WI represents the Ih word in a vocabulary。

So what we're interested in is the probability that the I word W I。

Would live in the neighborhood of word WN， which is represented by the code CWN。

 And so what we're trying to do here is to build a model。

Wwhich predicts the presence of surrounding words of a given word， so WN is a given word。

 it's the n word in our document， and then we're asking the question。

 what is the probability that the Ith word in our vocabulary， W I W parentheses I。

 what is the probability that it would be in the neighborhood of the nth word and so the way that we're going to do this is by generalizing the concept that we previously used for logistic regression。

So what we're going to do is we're going to take each of the outputs y1。

 y2 through y v sub1 for a vocabulary of size V。And we're going to set the V component y sub v to 0。

 So we're going to always set the V component to 0。 and then we're going to say that the probability。

That word I WI would be in the presence of the n word is represented by this expression。

 this is called softm， and as we'll see in a moment it's a generalization of logistic regression。

And so what we're quantifying is the probability that the I word。

Would be in the presence of the nword， so the nth word is represented by this vector c1 through CM。

And then the outputs。The output of the model are going to give us the probability of。

 of this mapping。And so that operation at the top。At the end to the right of the multilayer perceptron。

 this is something that we we do oftentimes， which allows us to quantify the output here of V variables。

 where we have a vocabulary of size V， this is called the soft max function。

 the equation that you see at the bottom is the soft max function。

 the thing to notice about this function， is that if we sum that probability over all I。

 over all words Wi， it sums to1。 So if we look at this probability the probability of word I given the code input C。

If we sum over all possible words in our vocabulary， it sums to one as probabilities must。

 this is a neural model for text and so the input of the network is the particular word that we're examining in our document and the output of the network tells us the probability that each it tells us the probability with which each of the words in our vocabulary would be in the neighborhood of that input word and remember the concept of word to V and remember that the idea is that if words are nearby an embedding space or nearby in vector space then we would expect that those words are related to each other and so this concept of a word in our vocabulary being in a neighborhood within the text of a particular word is related to this concept of relatedness or physical proximity。

Of words。So。So this multilayer perceptron idea is going to give us the foundation for how we're going to do learning of the word vectors and also the parameters of this multilayer perceptron。

 so this basic neural model of text is going to be our foundation for learning the word vectors and then learning how to make predictions about documents based upon the word vectors that we learn。



![](img/56c41ea2eb2a8f2e5ce72483943d9dda_1.png)

![](img/56c41ea2eb2a8f2e5ce72483943d9dda_2.png)
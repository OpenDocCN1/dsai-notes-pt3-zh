# 杜克大学《机器学习｜Introduction to Machine Learning》中英字幕 p40 40_04_03_词嵌入示例.zh_en -BV1yjvdBQEaU_p40-

So as we now start to become。More comfortable with the concept。

Of word embeddings or the idea of mapping every word。To a vector。We might。

Want to think about how we might utilize。Those word embeddings or those word vectors to do analysis。

 to do natural language processing。 and what we mean by natural language processing is to take natural text or language and try to make inferences or make to make predictions based upon。

That text。Elsewhere in our lessons， we've introduced this concept of a convolutional neural network。

And so what we would like to do。Just for a moment is to examine how we might use this concept of a convolutional neural network in the context of natural language processing。

 utilizing this word to V or word to vector representation。So at this point。

 let's assume that we have a codebook which maps every word to a vector。

 So we still haven't discussed how we are going to learn those。

 those embeddings or how we're going to learn the mapping from a word to a vector。 we'll get to that。

 But before we get to that， it might be worthwhile to examine what we might do with those。

Those word vectors if we had them。Because that will help motivate us for the work that it takes to understand how we learn these word embeddings or these word vectors so let's assume for now that we have learned the codebook so we have learned a mapping from every word to a vector if we've done that then any document that is composed of n words can be mapped to n vectors。

 each of which is M dimensional in size， once we have achieved this。

 we now have taken our natural language and we have mapped it into vectors numbers and then once we have that we can do various types of analysis on them。

 for example， sentiment analysis。Question and answer， translation between language， et cetera。

 So let's think a little bit about how we might achieve this。So let's assume that we have。

A document which is composed of n words， a sequence of n words， W1， W2。

 W3 to WN through this word to V concept， those n words will be mapped to N M dimensional vectors。

And so what we would like to do is apply the concept of a CNN， a convolutional neural network。

You want to apply this concept to text。And so what we're going to do。

 if we recall the convolutional neural network， which we've considered elsewhere in the context of images。

 now we're going to consider。The convolutional neural network in the concept， in the context of text。

 So recall that with a convolutional neural network， what we do is we take a filter and we shift it。

Through through the data in the context of images that corresponded to a two dimensionional shift in the space of images here。

 we're going to consider filters， each of which is by M times D in size。

 so M corresponds to the dimension of the vector and D corresponds to the number of words。

 the length， the number of words in the filter， so for example， if we consider d equal to 3。

That corresponds to filters， convolutional filters here we have K convolutional filters。

 each of which is length3 in the dimension of words， or you might think in terms of time。

 three time points along a sequence of words， and then the M dimensions which is the height corresponds to the dimensionality of the word vector。

And so what we're going to do is we're going to take our filter here。

 the filter is highlighted and we're going to convolve it or shift it to multiple positions along the length of our text。

 and so the way to think about this is that that filter in this case is of dimension 3。

And it corresponds to a concept which is related to three consecutive words。

 and then what we're going to do is we're going to take that filter and shift it through our text and whenever the filter the concept reflected in the filter of three consecutive words is aligned or related to the associated text at the corresponding shift location in that text。

 we would expect a high correlation or connection between the filter and the text and so through this process we're going to take。

Each of our K filters and we're going to shift it to each possible location in our text and for every shift location we're going to get a number and that number is a reflective of the match between the filter and the text and remember now the text is represented by the word vectors and so therefore through this process we take the original text and we map it into a set of n vectors。

 each of which is K dimensional。Then we might do something like pooling。

 and so the idea here is that for each。Of those K dimensions。

Of the output of this convolutional process， we might take the maximum value。Across all N positions。

 So for each。For each row。Of this matrix。Each row corresponds to the degree of match between the corresponding filter and the text at the associated shift location。

For each row of this n by K matrix， we might take max， we might take the maximum value， which means。

 and this is called a pooling step。It's called Maxpo， which would basically quantify which。

Value across the text gives us the largest correlation between our filter and the original text。

 We do this for each of the filters， and then we get a k dimensional a K dimensional vector。

 which is telling us the maximum correlation。Across the entire text between each of the K filters and that text。

 and so this then gives us a k dimensional vector and then ultimately this then can this once we have taken the text and mapped it to a k dimensional vector。

 that can then be sent through tools that we already have。

 which are mappings of vectors of feature vectors to classification decisions so we could take that K dimensional vector。

 send it through logistic regression or a multilayer perceptron。To make a decision。

And so the idea here is that once we have mapped words。To vectors。

 we then have significant opportunity to leverage tools that we have developed elsewhere in our lessons。

 particularly a convolutional neural network so the convolutional neural network which previously was applied to images through twodial convolutions when we analyze text is manifest it in terms of one dimensional convolutions。

 once we can do this， we can then use the power of the convolutional neural network to analyze text。

 one thing that I'll just briefly note is that if we're going to do learning if we're going to learn using a convolutional neural network。

 we require labeled text， which means we need to， for example。

 know the sentiment of every document that we're analyzing。

 because with a convolutional neural network if you recall。

We need label data for the training process， and so this is actually expensive in practice because it implies that every document。

That we're going to learn with， we would have to have the corresponding label for， for example。

 the sentiment， it is very expensive or time consuming for humans to read every document and then provide what we call the truth or the the well。

 the truth for the for the label， for example， the sentiment， so therefore learning。

In a supervised way， using label data is expensive。

And so as we move forward in our analysis of natural language processing。

 we're going to be particularly interested in situations for which we can learn， for example。

 learn the word embeddings or the word vectors based upon unlabeled data。

 and what that means is this just natural text， we directly take the natural text without requiring any human labeling and to do learning from that。

So in the discussion that we've had thus far， it was assumed that the word vectors were available i。

e。 they were already learned however。You may think that we can generalize this in particular。

 we can treat the word in the word vectors as additional parameters that we need to learn and then in the context of the convolutional network。

 we can learn the word vectors in the other parameters of the convolutional network simultaneously the challenge of this as was hinted。

 which I'll now highlight further is that to do this requires label data and so what that means is that for every document that we analyze。

 we have to have the so-called true label that we wish to predict from that text and as I said the access to label data is very expensive because it requires a human to read every document and then to provide a label so as we move forward in our analysis of methods for learning word vector。

We're going to be particularly interested in methods that do not require label data。

 which means that we can learn the word vectors directly on a corpus of text without the need for any human to do labeling。

 It turns out that there are some very powerful methods to do that， which we will consider next。



![](img/a92a4cb79b98ca0700d905f363090f66_1.png)

![](img/a92a4cb79b98ca0700d905f363090f66_2.png)
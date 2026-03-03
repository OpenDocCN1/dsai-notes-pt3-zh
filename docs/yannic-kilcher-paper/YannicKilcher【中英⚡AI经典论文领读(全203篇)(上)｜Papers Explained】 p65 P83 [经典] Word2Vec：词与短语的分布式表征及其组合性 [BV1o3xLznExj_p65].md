# YannicKilcher【中英⚡AI经典论文领读(全203篇)(上)｜Papers Explained】 p65 P83 [经典] Word2Vec：词与短语的分布式表征及其组合性 [BV1o3xLznExj_p65]

Hi there。 Today， we'll look at distributed representations of words and phrases and their compositionality by Thomas Mikkoov。

 Elilia Soskiver， Kai Chen， Greg Carrado and Jeffrey Dean。 This is another historical paper。

 It's one of three papers。 It's the middle one that introduces the original word to Vc algorithm。

 And if you as you might know， Wetubec was extremely influential in NLP， since this paper。

 basically until recently， where it's sort of gone out of fashion a bit in research with the rise of things like Elmo and Bert but it's still very。

 very relevant。 So we'll look at this historical paper today with kind of the hindsight of being a couple years into the future。

 In fact， as you see right here， this was released in 2013。 So it's seven years later now and。



![](img/152687d0e434d5df2ab2f4160c6cbb75_1.png)

![](img/152687d0e434d5df2ab2f4160c6cbb75_2.png)

We'll look back and we'll see what they said back then about the system。

 This is not going to be like a very you know well enhancedanced Powerpointee presentation of how where toV works we're going to look at the paper and read it together if if you like you know content like this。

 if you like historical paper readings， let me know in the comments share it out if you do like it and of course subscribe because this kind of historical papers。

 I enjoy them but you know many people might already know what these things are so。



![](img/152687d0e434d5df2ab2f4160c6cbb75_4.png)

![](img/152687d0e434d5df2ab2f4160c6cbb75_5.png)

Okay， let's you know go through the paper and pick up their ideas and kind of put them in context。

 They say the recently introduced continuous Sgramram model is an efficient method for learning high quality distributed vector representations that capture a large number of precise syntactic and semantic word relationships so the skipgramra model was already introduced by Milooff in an earlier paper that came out。

 I believe not like one or two months prior to this one As I said word to Vec is a series of papers。

 I don't think there is a paper called word to Vec rather they here have released the code along with with the paper the code was called word to Vec。

So the skipgramram model was introduced previously。

 but it is replicated right here so in the Sgramm model。

 what you're trying to do is you're trying to get a distributed word representation So what does that mean that means that for each word in your language let's take these words right here for each word in the language you want to come up with a vector that somehow describes that word in a continuous fashion So in the two might be mapped to I don't know。

0。10。9 and 0。3 learn might be mapped to negative 0。5 and so on。

 so each word gets assigned a vector in the same dimensional space。



![](img/152687d0e434d5df2ab2f4160c6cbb75_7.png)

And what the previous paper kind of discovered is that if you do this correctly， then these vectors。

 they have they have some kind of properties and we can already kind of jump ahead because this was already a bit。

 a bit researched in the last paper， the semantics of these vectors will be something like this。

 So here they have a two dimensional PC。 So these are the first two dimensions of the 1000 dimensional skip gra vectors。

 So the vectors they obtain， they can do things like this where they can show that in these spaces。

 for example。There appears to be a vector direction that characterizes the capital of a country so if you take a few countries and their capitals and you average that vector you get a kind of a direction for capitalness of a city given a country you can see that there is a pretty clear relation here Now some of these things have later been revised to such that they are ultimately ended up being not that impressive。

 for example， there was always this kind of math with vectors。And I don't。 I believe this is。

 this might not be in this。 This is in the last paper where they discovered that if you take the vector for king and you subtract the vector for man and you add the vector for a woman。

 then。That would result in the vector for queen。So the way they did it was basically they did this calculation right here and then they searched in the point they ended up。

 they searched for the nearest neighbor in their vocabulary and that turned out to be queen but in order to make it queen actually you have to exclude the original word king and people quickly discovered that if you don't exclude the original word you know the result of this kind of arithmetic will almost always lead back to the original word and then a lot of these analogy tasks are simply the result of you then discarding that word during the nearest neighbor search and then queen just happens to be one of the closest words and it's sort of much less dependent on which exact calculation you do here So there's been a lot of follow-up work kind of analyzing criticizing these vector mass。

 but definitely we know that these word vectors turned out to be extremely extremely。



![](img/152687d0e434d5df2ab2f4160c6cbb75_9.png)

![](img/152687d0e434d5df2ab2f4160c6cbb75_10.png)

![](img/152687d0e434d5df2ab2f4160c6cbb75_11.png)

helpful and syntactically and semantically relevant in downstream tasks because they have performed very。

 very well。

![](img/152687d0e434d5df2ab2f4160c6cbb75_13.png)

So how does the skip gra model work， how does it assign。Vectctors to each to each word。

 So first of all， it has a dictionary。 So there is a word， an input word。

 and for each word you have a big dictionary。And the di big dictionary basically says that， you know。

2， the word 2 is going to be mapped to this vector。1 da da da da da and so on。 the word learn。

Is going to be mapped to that vector。Then you also have these output vectors。Right here。

And what you're trying to do is you're trying to take a phrase from the data set like this one right here。



![](img/152687d0e434d5df2ab2f4160c6cbb75_15.png)

And you take out one word like this word vector right here。



![](img/152687d0e434d5df2ab2f4160c6cbb75_17.png)

And。You're trying to frame this as a prediction task， so you're trying to frame this as in this case。

 four different prediction tasks so you're telling your machine， I give you the word vector。



![](img/152687d0e434d5df2ab2f4160c6cbb75_19.png)

And which other words are around the word vector。 you just tell it that。

 you don't tell it anything else。 You just say which other words are around the word vector and the correct answers in this case would be to learn word and representations so。



![](img/152687d0e434d5df2ab2f4160c6cbb75_21.png)

This you construct four different training examples where you have an x and a y。

 so the x is always vector and the y is2， and then the next training sample。

 the x is vector and the y is learn。

![](img/152687d0e434d5df2ab2f4160c6cbb75_23.png)

![](img/152687d0e434d5df2ab2f4160c6cbb75_24.png)

And so on， okay。So this here， each training sample is a classification task right。

 and the classification task is an。

![](img/152687d0e434d5df2ab2f4160c6cbb75_26.png)

Is， as you can see。No， you can't see right here， but the classification task is。



![](img/152687d0e434d5df2ab2f4160c6cbb75_28.png)

You have the input word。And you classified it into one of many， many， many， many， many， many classes。

 namely there are as many classes as you have words in the dictionary。

So each word in the dictionary will have a class associated with it so in INe you have like1 thousand classes。

 but in these that's already a lot， but in these tasks you're going to have I10000 classes because there are 100000 words in the English language that you want to want to treat and there are many more but in this case they leave away all the words that appear less than five times in their corpus that's still a lot of words so it's like a super duper duper lot of classification task。

 but ultimately if you do something like this then the originally so the representation that you end up with is going to be very。

 very good at doing these kind of downstream tasks and that's what they discovered。



![](img/152687d0e434d5df2ab2f4160c6cbb75_30.png)

![](img/152687d0e434d5df2ab2f4160c6cbb75_31.png)

So。

![](img/152687d0e434d5df2ab2f4160c6cbb75_33.png)

Their skipgramm model is nothing else than taking a word and predicting the surrounding words from that word。



![](img/152687d0e434d5df2ab2f4160c6cbb75_35.png)

![](img/152687d0e434d5df2ab2f4160c6cbb75_36.png)

And this is what it means this is the formal statement of the skipgram objective。

 what you want to do is the objective of the skipcrara model is to maximize the average log probability this one。

 So for the word we're considering the word T。

![](img/152687d0e434d5df2ab2f4160c6cbb75_38.png)

![](img/152687d0e434d5df2ab2f4160c6cbb75_39.png)

We want to maximize the log probability of each word W that is in。Around the word C sorry。

 around the word W。In a context window of C， that's exactly what we did before。

 We take a word like this model right here。 and from it， we predict all of the words around it。

In in a in a given window， right。That's all， that's the entire objective。

 and that will give you very good representations。

![](img/152687d0e434d5df2ab2f4160c6cbb75_41.png)

![](img/152687d0e434d5df2ab2f4160c6cbb75_42.png)

And this is how you would implement that。 So what you'll have is you'll have these vector representation。



![](img/152687d0e434d5df2ab2f4160c6cbb75_44.png)
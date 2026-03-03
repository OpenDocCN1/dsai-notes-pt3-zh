# YannicKilcher【中英⚡AI经典论文领读(全203篇)(下)｜Papers Explained】 p84 P184 Transformer记忆作为可微分搜索索引（机器学习研究论文详解） [BV1j8x5zJEvx_p84]

This is a comprehensive paper review of the paper Transer memory as a differentiable search index。

 This paper is pretty crazy。 It takes an entire data set and puts it into the weights of a transformer。

Essential， it trains a search engine not to search through documents。

 But just to give you the index of the document that matches your query。 just like that。 boom。

 So this video is a comprehensive review of the paper。

 I'll explain to you what's in the paper what it's about。

 And by the end of the video you should have a good idea of the paper itself。 The next video。

 which I'm going to release tomorrow will be an interview with the authors。

 Well dive right into the content and any criticisms and questions that I raise during the review。

 As always， let me know what you think in the comments。 And now let's get into the video。 See around。

😊，🎼Does your company have a lot of people labeling data。

 Why would you leave such an important task to close to systems or selfimplemented things。

 Training data is your most valuable asset and human labels are really expensive。

 Today's sponsor is difgram， which is an open source platform centered around training data。

 They handle everything to do with training data， especially collecting， labeling。

 serving and more and it is open source。 So you can selfhos all you want。

 But there is one cool thing if you let them host it for you。 and that is unlimited pricing。

 No per label annotation， no expensive servers to run。 you pay once you get as much as you want。

 So thanks again to difgram for sponsoring today's video。

 Check them out using the link in the description to let them know that I sent you。

 All right let's get into the video。

![](img/96106bb8b7c7d004cf362c690bd6e5f4_1.png)

![](img/96106bb8b7c7d004cf362c690bd6e5f4_2.png)

![](img/96106bb8b7c7d004cf362c690bd6e5f4_3.png)

![](img/96106bb8b7c7d004cf362c690bd6e5f4_4.png)

Hello there。 Today， we're looking at Transer memory as a differentiable search index by researchers of Google research。

 This paper on highlevel takes a search problem where you have to index documents and retrieve them。

 And it puts all of the corpus， essentially into the weights of a transformer。

 So it takes the corpus and trains the transformer。 and then at the end。

 they can just give a query to the transformer and the transformer will output the I D of the document that matches。

 and it turns out for some data sets that they have for some settings。

 and with some clever training and representation of the documents。 that can actually work。

 which is really crazy。 This kind of speaks to multiple things。

 such as obviously our ability to overfit on stuff。 But there is some generalization here。

 As we'll see， on the other hand， Also the kind of inner workings of these transformer。😊。



![](img/96106bb8b7c7d004cf362c690bd6e5f4_6.png)

And lastly， what's pretty cool is that this is completely as it says differentiable。

 It's a differentiable search index， which means that this can be part of larger neural network architectures because it is fully differentiable and it can be trained essentially end to end at once。

 And that means we can potentially employ reinforcement learning agents with kind of retrieval abilities and much more things。

 So we dive into the paper we'll see what it's about， the idea as I said， is pretty， pretty simple。

 If you like content like this and as always leave a like and tell me what you think in the comments that's always super helpful。

😊，So。As I said， they take， they take a search problem and the search problem is essentially。

 I have a corpus。 like I have a big database of of documents。 right， Here is a document。

 Here is a document， and I want to build an index and an index is some kind of data structure， some。

 some kind of thing。 and at the index， I can throw a query。And the index will return to me an I D。

 a document I D that specifies which document matches my query。 Usually。

 this is done via inverted indices。 So I want to tokenize my document， split them into little tokens。

 which are usually words or sub wordss。 And I want to stem them and lamatize them and whatnot。

 Then I build a revert reverse index。 So for every word like in the word in。 I。

 I remember which documents it appears in like document 3 document 5 document 11。And so on。

 And then once the query rolls in， I simply tokenize it as well。

 I go look into my inverted index and I look up all the documents。

 And then theres also a ranking step， which means I have to now determine which of these documents is the most relevant。

 and that is usually done via techniques like T F I DF features。

 There is a famous technique called B M25， which is also a baseline in this paper。

So this is the classic search kind of way， way of doing search。 If you use any search engine at all。

 this is being done in the background。 for the most part。

 Newer search engines are catching on There's neural search and so on。

 But men 25 is still one of the most performant things that text search as available。

 And also other types of search。 however， there is a new push in sort of neural search and in neural search。

 you're trying to take your data set。 And for each document。

 you try to map it to some sort of a vector in vector space。 And then once the query comes in。

 you also map the query to a vector。 And for example， you compare inner products。

 whichever inner product is largest。 that's the document that's relevant。 This is just one way。

 this is what we usually call a by encoder method where the documents in the queries are mapped both map。

Individually， so there will be an encoder。Here， and there would be an encoder here。

 they all would output one vector。 and then the vectors that are compare。

 This could be the same encoder or different encoders for documents in query。

 This is just one method， there is various methods such as cross encoders， rerans， dense retrievers。

 you name it however， this method here is even is different。

 So what we want to do is we want to take the corpus as such。

 and map thats somehow into a neural network。 And we're going to talk about this somehow。

 But we're going to train a neural network。 Essential how do we represent this。

 Let's represent it with its layers。 such that when later I feed a query to the neural network。

 As I already said， the Id of the document is the output of the neural network。

 So it doesn't output a vector that I then go and compare it doesn't I don't have to go。

And feed in query document pairs。 And then I get out a score of how well they fit together。

 which what I would do in a cross encoder。 No， the transformer， in this case。

 the neural network directly gives me the I of the document which without seeing the data at inference time。

 So during training all of the data is essentially has to be mapped somehow into the weights of the neural networks right So somewhere in these weights。

 that information is stored of what the documents are。

 So the entire corpus is in those weights and once I enter a query the correct document I can only be output。

 obviously， if the transformer has somehow learned what is in those documents。

 So that's the setup is pretty simple setup， once you kind of see what's going on it's like a meme right instead of we've been trying to neuralize search and。

We've still done this two step process where we train these encoders。

 But then the actual search is still done using， for example。

 an nearest neighbor algorithm like here。 But， you know， this is just the idea of， well。

 why don't I just ask the neural network to output the result， right， the resulting docadi。

 Why don't I just do that， And it turns out that can work surprisingly well。

 So you can do large a couple of things here， But that's essentially it。

They say right here in the introduction。U。They use a sequence to sequence learning system。

To directly map a query to a relevant document I D。

The they have different corpes where they train it on on the smallest corpus。

 This method improves the hits at one， which means that whether the top it hit is the correct one。

 more than 20 points from 12。4 per cent for a dual encoder。 So the baseline here is a dual encoder。

 what I shown whenever the there are two encoders， and they each output an embedding。To 33。9%。

 that's a giant gain， right， That's like a 2。5 x improvement。However。

 on a corpus that's 30 times larger， Per is improved by nearly 7 points， which is less。

 It's also respectable that performance if it is improved at all。 However， I want you to notice。

 And that's already kind of the first indication a little bit of obviously what's going on here。

 on smaller data sets， this method does super duper well on larger data sets。

 the method doesn't do that much better than a sort of cross encoder type setup。 Sorry。

 a by encoder type setup， or a dual encoder type setup， which is understandable， right。

 because the smaller the data， the easier it is to absorb it all into your weights。

 if the data gets larger that obviously gets harder and harder。 there is more data to go around。

 which means theres。

![](img/96106bb8b7c7d004cf362c690bd6e5f4_8.png)
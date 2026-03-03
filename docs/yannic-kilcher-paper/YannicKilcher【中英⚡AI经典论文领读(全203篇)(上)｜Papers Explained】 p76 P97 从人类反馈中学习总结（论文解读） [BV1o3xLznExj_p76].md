# YannicKilcher【中英⚡AI经典论文领读(全203篇)(上)｜Papers Explained】 p76 P97 从人类反馈中学习总结（论文解读） [BV1o3xLznExj_p76]

High ratedit， my boyfriend and I have been dating for a year， and it has been great。

 except for one thing， dota。The other day on a Saturday， I was over and he was playing a game。

 I thought it would just be one， But instead， he proceeded to play for three hours as I just SAT there。

 What can I do So this， as you can see， it is a post from a subreddit called relationship of someone seeking relationship advice。

 Now， I would claim that this is clearly fake， because no one plays dolta for just three hours。

 crazy， But let's assume that this is a thing that really happened。 And what， it doesn't matter。

 The article here is written。 And the task is to summarize this post in as few tokens as you can。

 But sort of giving much of the information that's in the， that is in the post itself。

 So the task here is called summarization。😊，And humans can do this quite well。

 So here you see a human written reference baseline。My boyfriend games whenever he can。

 how can I get him to stop gaming so much and focus more on school and our relationship？Okay。

 so that's a pretty good summary of what goes on in this model。

The most the easiest baseline for this task in machine learning are what's called extractive baselines。

 So in extractive summarization， what you do is you try to find subpans。

 So let's say like this span followed by this span and so on that together represent the article。

 So you strictly select sub spans or even entire phrases from the text that you're looking at。

 So a lot of these baselines are extractive and they perform already fairly okay。



![](img/3346172f219bbd96b427e9a17dd1f8d2_1.png)

For example， this one right here help。 my my boyfriend is neglecting his studies and our relationship because of a video game。

 I think that's just extracting from the title。 Okay， that's title policy。 There are other models。

 for example， here this lead too。 Hi， Redit， my boyfriend and I have been dating for a year Indeed has been great。

 I mean， that accurately。😊。

![](img/3346172f219bbd96b427e9a17dd1f8d2_3.png)

It representspresents。

![](img/3346172f219bbd96b427e9a17dd1f8d2_5.png)

Maybe not maybe that's not。 So you can already see that it's quite hard because not only does a model have to understand what information is in a text and what are the important things。

 but also clearly it needs to understand something about the intent of the post right if you want to compress you have to compress the meaning and the meaning because we are humans。

 we understand that this person here is distressed seeking advice It's like what should I do and we understand that the source of the frustration is the fact that the boyfriend here plays a lot of this video game It's not really important how much they've played or even that they've been dating for a year or so on the problem here communicate it is the playing video games So you see that the researchers here have come up with a bunch of models and their best model that we're going to look at here is called this human feedback model。



![](img/3346172f219bbd96b427e9a17dd1f8d2_7.png)

With 6。7 billion parameters， it's a G style model and we'll get to all of this in one second。

 I'll just want to kind of show you the end result that can output the following。

 My boyfriend is neglecting his studies and our relationship because of his excessive gaming of a video game What can I do to get him to stop alright so。



![](img/3346172f219bbd96b427e9a17dd1f8d2_9.png)

There are a couple of nuances here， like the the what can I do to get him to stop is not really explicitly said in the text。

 it says it seems like it's interfered with our relationship。 He's doing his PhDs， obviously swamped。

 it goes on the back burner。It makes me rethink our relationship and so on。

 These things aren't explicitly said yet。 The model somehow understands that that's what this person expresses。

 And if you want to compress this， then。This information， then this is a very good thing to。

 this is a very good summary to output。We'll go to see how they come to build this model。

 what it has to do with human feedback and。

![](img/3346172f219bbd96b427e9a17dd1f8d2_11.png)

![](img/3346172f219bbd96b427e9a17dd1f8d2_12.png)

Just in generally how it works and also where it fails。 So this is a pretty big paper。

 as you can see， it's one of those papers where the appendix needs a table of contents。

 which is going to come up very shortly， very this there there was lots of references So it's a paper by open AI Of course。

 recently Open AI has made big， big advancements in language research with G3。

 And this is from kind of the same style of research。

 So the paper is called learning to summarize from human feedback by Nissan Steon Long Wuyang。

 Jeff Wu Daniel M。 Zieler， Ryan Lawi， Chelsea Voss， Alradford， Darria Ammanai and Paul Christiano。

 As I said of open AI。 So they tackle this task of summarization of of these kind of posts or news articles。

 you can apply this pretty much anywhere。 and they incorporate human feedback。



![](img/3346172f219bbd96b427e9a17dd1f8d2_14.png)

![](img/3346172f219bbd96b427e9a17dd1f8d2_15.png)

![](img/3346172f219bbd96b427e9a17dd1f8d2_16.png)

![](img/3346172f219bbd96b427e9a17dd1f8d2_17.png)

Back into it。 Now， why do they incorporate human feedback， And that's because。

That's because summarization isn't a straightforward task， right， So in its basic。

 if you have a summarization task， you have some sort of a piece of text that contains some information。

And from this， you want to generate a small piece of text。The small piece of text should be first。

 very short。But second， also， it should contain information。

It should contain all the information that was contained in the original article。

 maybe not all of it， but it should contain the important information of what is in the article。

 And then there are some other things like it should also be coherent。

But I think that's sort of implicit in this information objective。

 What you want to do is if someone reads this piece of text。

 they should get all the information that was in the big text or not all but most or the important information。

 Humans are quite okay at this。 But it's not like we can really formulate exactly what we want。

 right， It's not like we can give a classification label and then tell the machine exactly。 look。

 this class is correct。 And these other classes are wrong。

Now what people have been doing is they've built datas where you'd have for one particular document you'd give it to。

 let's say three different humans and the three different humans would produce three different summaries because different humans do it differently so you'd provide three different summaries and then you let your machine。

 your machine learning model produce some summary。

![](img/3346172f219bbd96b427e9a17dd1f8d2_19.png)

![](img/3346172f219bbd96b427e9a17dd1f8d2_20.png)

And then your evaluation metric would be a metric that takes this piece of text and compares it to those pieces of text。

 And this one of these methods here is called rouge。

 so Rouge is a metric that looks at Ngram overlaps。

 the Wikipedia page pulled up here and you can see it consists of a bunch of sub metrics。

 but there is a way to mix them， but in their essence。

 they basically look at overlaps of here overlap of ngrams。

 so you can look unigrams or bygrams you can look longest common sub sequenceequence and so on basically you sort of try to compare the words the text specifically in here to the texts in in the human summaries。



![](img/3346172f219bbd96b427e9a17dd1f8d2_22.png)

![](img/3346172f219bbd96b427e9a17dd1f8d2_23.png)

![](img/3346172f219bbd96b427e9a17dd1f8d2_24.png)

![](img/3346172f219bbd96b427e9a17dd1f8d2_25.png)

![](img/3346172f219bbd96b427e9a17dd1f8d2_26.png)

![](img/3346172f219bbd96b427e9a17dd1f8d2_27.png)

![](img/3346172f219bbd96b427e9a17dd1f8d2_28.png)

![](img/3346172f219bbd96b427e9a17dd1f8d2_29.png)

And given the rich nature of language， that's not really a good approach。

 But it's the best one we have。 Like we don't， we don't have a better metric to tell the machine what's right or wrong。

 And it goes actually further。 So this rouge as an evaluation metric， It's already， it's fairly bad。

 as we can see。

![](img/3346172f219bbd96b427e9a17dd1f8d2_31.png)

![](img/3346172f219bbd96b427e9a17dd1f8d2_32.png)

As we will see， they have a graph somewhere。 and I might just draw the graph in that。

If if this here is kind of the complexity of the information and this here is the how good the summary really is as arated by humans。

 so this paper plays a lot of emphasis on going to actual humans and asking them how good is a summary。

 if you employ Rouge， then at the beginning， you increase as you increase the quality。



![](img/3346172f219bbd96b427e9a17dd1f8d2_34.png)

For easy text， for easy information and for really bad models， the rouge metric makes sense because。

 you know， generally， if you have a very crappy model and one that just outputs the same kind of text as the humans do。

 then that one's going to fare better。 But then at some point， it wanes off。

 and the at some level of complexity， coherence and so on。

 the rouge metric is just not good enough anymore more to differentiate。

 sorry to differentiate good from bad。

![](img/3346172f219bbd96b427e9a17dd1f8d2_36.png)

Summaries， or let's say to differentiate excellent from good， but not excellent summaries。

 Let's phrase it like this。 It's good at differentiating bad from good summaries。

 but not good from excellent。

![](img/3346172f219bbd96b427e9a17dd1f8d2_38.png)

Okay。

![](img/3346172f219bbd96b427e9a17dd1f8d2_40.png)

So that's one thing。 That's evaluation。 But Rouge， this overlap of Ngramm。


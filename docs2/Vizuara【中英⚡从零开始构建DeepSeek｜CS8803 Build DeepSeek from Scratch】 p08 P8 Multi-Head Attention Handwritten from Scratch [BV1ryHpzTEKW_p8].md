# Vizuara【中英⚡从零开始构建DeepSeek｜CS8803 Build DeepSeek from Scratch】 p08 P8 Multi-Head Attention Handwritten from Scratch [BV1ryHpzTEKW_p8]

Hello everyone， My name is Doctor Raj Dunecker。 I graduated with a PhD in machine learning from MIT in 2022。

 and I am the creator of the Bill Deepsek from Scratch series。Before we get started。

 I want to introduce all of you who are sponsor and our partner for this series in V AI。

All of you know how much we value foundational content building AI models from the nuts and bolts inviideo AI follows a very similar principle and philosophy to that of us let me show you how。

So here's the website of Inviideo AI。With a small engineering team。

 they have built an incredible product in which you can create high quality AI videos from just text prompts。

😊，So as you can see here I've mentioned a text prompt。

 create a hyper realisticistic video commercial of a premium luxury watch and make it cinematic with that I click on generate video。



![](img/95d44ad91cb9b5df7cf13aea41ed557b_1.png)

Within some time， I am presented with this incredible video， which is highly realistic。

What fascinates me about this video is its attention to detail look at this。

 the quality and the texture is just incredible and all of this has been created from a single text prompt。

That is the power of Invi's product the backbone behind the awesome video which you just saw is in video AI's video creation pipeline in which they are rethinking video generation and editing from the first principles。

To experiment and tinker with foundational models， they have one of the largest clusters of H100s and H200s in India and are also experimenting with B200s。

Individualviio AI is the fastest growing AI startup in India building for the world。

 and that's why I resonate with them so much。The good news is that they have multiple job openings at the moment you can join their amazing team I am posting more details in the description below。

🎼。

![](img/95d44ad91cb9b5df7cf13aea41ed557b_3.png)

Hello everyone and welcome to this lecture in theBuild Deep Seek from Sctch series。

Today we are going to have our second lecture on the multiha attention。

 if you remember in the previous lecture we went through the conceptual overview of multiha attention and how the mechanism actually works。

 how we split the query key and value vectors into multiple different heads and how each of the heads eventually leads to a different attention score and that actually helps us in capturing two different perspectives with just the self attention mechanism we can capture only one perspective of a given sentence or a given paragraph。

But in some cases， we would like to essentially compute。

The concepts in a lot more detail are from a lot more perspectives。

 which is not possible through just a self attention mechanism and that's why we have the multi head attention mechanism where each head allows us to compute a different perspective。

So we saw the whole process in the previous lecture today what we are going to do is that today we are going to take a matrix。

 we are going to take an actual input embedding matrix and we are going to see step by step about how the multi attention works in practice。

So this is going to be a mathematics based lecture the previous lecture was more about intuion。

 but here we are going to go step by a step with respect to mathematics and parallelly I'm also going to show you the code for how the multiard attention function is written and by the way what we are going to cover in today's class is exactly how the first multiard attention implementation works in practice。

So whatever we have done until now in this lecture series。

 starting from self attention to causal attention to the first lecture of multi head attention。

 it all comes to a climination point in this lecture where we will code out the entire multi headat class in multi head attention class in Python and I also show you the step by step mathematical derivation and every matrix multiplication in a lot of detail。

First let's do a quick overview of what we learned in the previous lecture in the previous lecture we saw that if you have sentences such as this the artist painted the portrait of a woman with a brush。

This can be viewed in terms of two perspectives， either the artist painted the portrait of a woman using a brush。

Or the artist painted the portrait of a woman with a brush。So the woman had a brush in her hand。

 it can be two different perspectives， right？But a self attention mechanism can only capture one such perspective because there is only one attention scores matrix either we can have this or we can have this。

So then the question is， can we somehow extend the self attention mechanism so that it can capture multiple perspectives？

So what we did was a single headacheer。Can get us one attention score So what if we have multiple heads right So what if we have two self attention mechanisms instead of one and then we saw how to implement this multi head attention step by step。

 we started with an input embedding matrix the artist painted the portrait of a woman with a brush we saw that the first step which is done is that we decide the output dimension and this is going to stay the same in today's lecture as well we have to decide the output dimension and we have to decide the number of heads which we would the number of attention heads。

So， in our case in the previous lecture we had output dimension equal to 4 and number of attention heads equal to 2。

 so the head dimension is the output dimension divided by the number of attention heads that is equal to 2。

This is the dimension of each head so what actually happens when we start doing the calculation is that we split the trainable query matrix the key matrix and value matrix into two parts and that eventually splits the query vectors the key vectors and the value vectors into two parts why do we have two parts because there are two potential heads so there is one copy of Q k and v which is the query key and value matrix for each head。

And now that we have two copies of the query key and value。

 it essentially leads to two attention scores， so this is the attention scores matrix calculated from the first head and this is the attention score matrix calculated from the second head。

This right here is the most important point in the multiha attention mechanism workflow because each attention scores matrix here essentially represents a different perspective this was not possible with just the self attention mechanism now we have two attention scores mates right so each can capture different perspective and that is the main advantage of multiha attention。

Then what we do is after we have the attention scores。

 we do the scaling with square root of the keys dimension。

 we apply softm causal attention and if you want we can do drop out also that leads to the attention weights。

 the head one attention weights and the head2 attention weights。

And then what we do is that we multiply the attention weights of the head1 and head2 with their corresponding value vectors and then we get the context matrix for head1 and head2。

 we merge these context mates and then we get the final context matrix which now is a mixture of two perspectives。

So remember， the more the attention heads we have， the more the perspectives we can capture into our final context matrix。

That' is exactly how the multiha attention actually works in practice we also saw a cool visualization towards end where we took a free trained large language model and we are actually explored inside the attention heads。

So today， as I mentioned， we are going to。Do a mathematical calculation of exactly how the multiier attention works。

 so I'm going to show you every single matrix multiplication from scratch and then I am also going to show you how it relates to the code for the multihir attention so here if you see this is the multiard attention class。

And if you just see the class without understanding the mathematical details。

 this all might seem a bit confusing to you， but I will take you today through the entire mathematical derivation and then I'll show you that it is actually directly mapped to the code and then understanding the code becomes that much easier。

So let's get started today the example which we are going to consider is this example where we will start with an input embedding matrix okay so the input embedding matrix is x and there are three tokens essentially。

Let me change my color here， so that。Maybe I'll change it to this new color over here。

 which is orange。So this is my input embedding matrix here。

 the way to visualize this matrix is that there are three tokens。

 this is token 1 that corresponds to the first row。

 this is token 2 which corresponds to the second row and this is token 3 which corresponds to the third row and every token essentially has a certain dimension that' is my input dimension and this is going to be equal to6 in this case so there are three tokens and each token has six dimensions。

But as you see this this this is a tensor with three dimensions over here。

 so what is these three the second is essentially just the number of tokens。

 the third is essentially the input dimension d in so this is the tokens。This is the D in。

 but what is the first dimension， the first dimension is essentially the batch。



![](img/95d44ad91cb9b5df7cf13aea41ed557b_5.png)

The bad say。
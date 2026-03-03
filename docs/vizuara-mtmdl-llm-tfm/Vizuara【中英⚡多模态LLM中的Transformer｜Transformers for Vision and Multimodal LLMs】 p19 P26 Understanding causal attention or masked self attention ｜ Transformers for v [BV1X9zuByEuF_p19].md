# Vizuara【中英⚡多模态LLM中的Transformer｜Transformers for Vision and Multimodal LLMs】 p19 P26 Understanding causal attention or masked self attention ｜ Transformers for v [BV1X9zuByEuF_p19]

Hi， welcome back to a new lecture from Transformers for Vision Series。In today's lecture。

 we will try to understand causal attention mechanism。

 which is the actual attention mechanism implemented in models like GPT。

We will not be implementing multi head attention yet which we are reserving for the next lecture。

 but today we will see how the masked self attention also known as course Select attention works。

So with that， let's get into the lecture， in fact， today's lecture you will find much easier compared to the previous lecture because the concept is pretty simple。

However， if you don't remember how the self attention itself works。

 I will give you a brief recap in the beginning。

![](img/edbe8ac55858e949bcfeafd4a78bbd19_1.png)

![](img/edbe8ac55858e949bcfeafd4a78bbd19_2.png)

So before we go into the nuts and bolts of causal attention mechanism itself。

 let's try to have a quick recap over。

![](img/edbe8ac55858e949bcfeafd4a78bbd19_4.png)

What the idea of attention mechanism itself was。

![](img/edbe8ac55858e949bcfeafd4a78bbd19_6.png)

So the idea was we wanted to produce a context vector corresponding to every single input embedding。

 so input embedding is a vector which corresponds to every token and corresponding to every single input embedding we want to produce a context vector and why is context vector so important because it is much more richer in information。



![](img/edbe8ac55858e949bcfeafd4a78bbd19_8.png)

![](img/edbe8ac55858e949bcfeafd4a78bbd19_9.png)

So input embedding is just the direct conversion of a token into a vector。

 whereas context vector also has the information about the tokens next to the token which you are looking at。

So if you are considering the sentence， the cat。

![](img/edbe8ac55858e949bcfeafd4a78bbd19_11.png)

SAT on the mat。

![](img/edbe8ac55858e949bcfeafd4a78bbd19_13.png)

![](img/edbe8ac55858e949bcfeafd4a78bbd19_14.png)

If you simply convert the token cat into an input embedding， it may look like this。

 but the cat is not a token that is standing there alone right because there are other tokens next to cat。

 the sat on the mat， all of them are next to the cat。



![](img/edbe8ac55858e949bcfeafd4a78bbd19_16.png)

So how do we embed this context into the CAs input embedding vector that is by converting it into a context vector。

So this context vector production corresponding to every single token so the should be converted to one context vector。

 catch should be converted to one context vector sat another one on another， the and mat。

 so if there are totally one，2，3，4，5，6 tokens。

![](img/edbe8ac55858e949bcfeafd4a78bbd19_18.png)

![](img/edbe8ac55858e949bcfeafd4a78bbd19_19.png)

In our output， we need six context vectors。Now， just to recap the。Words are not equal to tokens。

 it's an oversimplification that I'm taking here for the convenience of conveying the idea。

The actual tokens in GPT can be。Words， sub wordss， characters， etc。

 so we discussed the by pair encoding in one of the previous lectures。

 but for simplicity we will assume one token is equal to one word。Now。

 these six context vectors are much better。😊，or much richer in information compared to the six input embeddings right so this was the idea behind attention mechanism。

 how can we create context vector using attention mechanism？



![](img/edbe8ac55858e949bcfeafd4a78bbd19_21.png)

![](img/edbe8ac55858e949bcfeafd4a78bbd19_22.png)

![](img/edbe8ac55858e949bcfeafd4a78bbd19_23.png)

So two lectures before we had implemented a simplified version of self attention。😊。

In which we said we will just take the dot product between two vectors。😊。



![](img/edbe8ac55858e949bcfeafd4a78bbd19_25.png)

So if I have a vector like this for cat。

![](img/edbe8ac55858e949bcfeafd4a78bbd19_27.png)

And if I have a vector like this for the， so let's say this is corresponding to CA and this is corresponding to the if I take dot product between them。

It's 90 degrees， so。The dot product between two orthogonal vectors is zero。



![](img/edbe8ac55858e949bcfeafd4a78bbd19_29.png)

Which means cat need not pay too much attention to the。

 but here cat should pay a lot of attention probably to sat and also to mat because cat is sitting on the mat。



![](img/edbe8ac55858e949bcfeafd4a78bbd19_31.png)

So maybe the vectors corresponding to cat and mat might look like this or mat might be something something that looks like this。

 so we said since these input embeddings are vectors pointing into semantic areas of multidimensional space。



![](img/edbe8ac55858e949bcfeafd4a78bbd19_33.png)

If you simply take the dot product between those vectors。

 the vectors that are pointing generally in the same direction will have a bigger dot product。

 vectors that are orthogonally pointing to completely different directions in the semantic space will have a very small dot product。

And we took this dot product as a proxy for attention score。

And then we said okay attention score need to be normalized to get attention rates。

 so that is what we did in the simplified self attention lecture。



![](img/edbe8ac55858e949bcfeafd4a78bbd19_35.png)

![](img/edbe8ac55858e949bcfeafd4a78bbd19_36.png)

But then we discuss this has a problem。The problem is consider this sentence the dog chased the ball。

 but it could not catch it。

![](img/edbe8ac55858e949bcfeafd4a78bbd19_38.png)

If you consider the last word it。😊。

![](img/edbe8ac55858e949bcfeafd4a78bbd19_40.png)

What does this it mean？This it refers to ball or dog。Here it simply means ball。

 so the token it should pay more attention to ball。Then it should pay to doc。Now， let's say the。



![](img/edbe8ac55858e949bcfeafd4a78bbd19_42.png)

Token embeddings in three dimensions， so we are simplifying it again we are considering the token embedding space to be three dimensional space。

In that space， let's say dog is this vector 0。90。1。1 and this is ball and this is it。

And clearly they are pointing in different directions。

 but now if you take the dot product between it and ball， you get a dot product like 010。51。



![](img/edbe8ac55858e949bcfeafd4a78bbd19_44.png)

If you take a dot product between it and Do， again you get 0。51。



![](img/edbe8ac55858e949bcfeafd4a78bbd19_46.png)

So simply taking a dot product。😊，Is sometimes not enough to capture the attention vi because here the attention scores are exactly the same between it and ball and it and dog。

Ideally， what I wanted was attention score between it and ball should have been bigger higher than it and dog。

 right， but that's not the case here。😊。

![](img/edbe8ac55858e949bcfeafd4a78bbd19_48.png)

That's because we are directly using the input em bes。😊。



![](img/edbe8ac55858e949bcfeafd4a78bbd19_50.png)

In the dot product。So this brought us to our idea， which we discussed in the last lecture that instead of using the embeddings directly。



![](img/edbe8ac55858e949bcfeafd4a78bbd19_52.png)

We still need to use dot product。😡，Because the core idea of dot product is still valid。

 because if you take dot products between two vectors and if those vectors are pointing in similar direction of the semantic space。

 then it is a valid idea because if the dot product is big。

 that means those vectors are pointing in the same direction which means they should probably pay attention more attention to each other。

So that idea is valid， but the problem here is we are directly taking the dot product of the input em day。

😊，So what we discussed in the last lecture was instead of using the input embedding directly。

 use transformed input embedding。

![](img/edbe8ac55858e949bcfeafd4a78bbd19_54.png)

![](img/edbe8ac55858e949bcfeafd4a78bbd19_55.png)

And use some matrices to perform this transformation。



![](img/edbe8ac55858e949bcfeafd4a78bbd19_57.png)

So these matrices had some names， so we introduced three matrices。



![](img/edbe8ac55858e949bcfeafd4a78bbd19_59.png)

Query matrix W Q， key matrix W K and value matrix W V。



![](img/edbe8ac55858e949bcfeafd4a78bbd19_61.png)

Now in this example， what we are showing is the query currently is it because we are looking at how much attention should it pay to dog and ball。

😊。

![](img/edbe8ac55858e949bcfeafd4a78bbd19_63.png)

So it being a query， it is transformed using the query matrix。And this is a weight matrix。

 it's a trainable matrix so in the last lecture we implemented self attention using trainable weights。

 but before that we had implemented self attention in a simplified manner without trainable weights。

😊，And now if you convert it。Into a transformed query space using the W matrix you get this vector 0。

5。5。1 it is the same as the previous it vector because in this simple example I have used an identity matrix as the WQ matrix。



![](img/edbe8ac55858e949bcfeafd4a78bbd19_65.png)

![](img/edbe8ac55858e949bcfeafd4a78bbd19_66.png)

Now， this WK matrix is used to transform my tokens into the key space。

And key space is also three dimensional here in this example。

And I transform dog by multiplying it with WK， I transform ball by multiplying it with WK as well。

 and now these are the transformed vectors of dog and ball in the key space。



![](img/edbe8ac55858e949bcfeafd4a78bbd19_68.png)

Now I can calculate attention score between transform it， which is this made vector and transform do。

 which is this vector resulting in 0。56 as the attention score。

 I can also calculate attention score between transform it and transform ball by taking the dot product between this vector and this vector resulting in 0。

96。

![](img/edbe8ac55858e949bcfeafd4a78bbd19_70.png)

![](img/edbe8ac55858e949bcfeafd4a78bbd19_71.png)

![](img/edbe8ac55858e949bcfeafd4a78bbd19_72.png)

So you see conceptually I hope you understand now how a transformation can actually make your attention score much more meaningful or much more useful because here now it is paying more attention to ball than to dog because attention score is clearly showing that so this is the reason why we introduce the concept of transformations so embeddings are transformeded into query key value space。



![](img/edbe8ac55858e949bcfeafd4a78bbd19_74.png)

Now to generalize this idea， we took an example， so let's say the sentence is the dog chased the ball and let's say we are representing each vector in the input embedding in a three dimensional space。

 so this three three dimensional vector corresponds to the this to dog chased the ball so this is a5 by3 matrix because you have five tokens and each token is three dimensions。



![](img/edbe8ac55858e949bcfeafd4a78bbd19_76.png)

![](img/edbe8ac55858e949bcfeafd4a78bbd19_77.png)

![](img/edbe8ac55858e949bcfeafd4a78bbd19_78.png)

Then we transform this 5 by 3 matrix。

![](img/edbe8ac55858e949bcfeafd4a78bbd19_80.png)

Or we transform these three dimensional vectors into two dimensional vectors so in the example that we took in the last lecture we said that the query key value space will be two dimensional。

 although in reality it will be different in GPT by the end of the multi head attention attentions the dimensionality does not change。

 but here we assume it to be changing。

![](img/edbe8ac55858e949bcfeafd4a78bbd19_82.png)

![](img/edbe8ac55858e949bcfeafd4a78bbd19_83.png)

![](img/edbe8ac55858e949bcfeafd4a78bbd19_84.png)
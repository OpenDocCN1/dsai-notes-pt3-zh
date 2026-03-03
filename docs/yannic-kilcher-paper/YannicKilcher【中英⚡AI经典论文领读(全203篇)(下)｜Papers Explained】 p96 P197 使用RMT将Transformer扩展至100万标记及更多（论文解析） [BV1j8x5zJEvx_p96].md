# YannicKilcher【中英⚡AI经典论文领读(全203篇)(下)｜Papers Explained】 p96 P197 使用RMT将Transformer扩展至100万标记及更多（论文解析） [BV1j8x5zJEvx_p96]

Hello， today， I wanted to give a quick look at this paper。

 scaling transformer to 1 million tokens and beyond with RMt by Iar Bullulaov。

 Yurikuatov and Mikhail S Bef。 This paper has a big promise。

 namely scaling transformer inference to a humongous 1 million， even 2 million tokens。

 and in the first page plot right here， they have some tasks that they want the transformer to do。

 for example， there is a memorized task， there is a detect memorized task。

 And there is even a reasoning task。 And as you can see right here， we have input size in tokens。

 and they go up to 2 million and you can pretty much see that the transformer holds up performing these tasks across all of those token sizes。

 Now， there are a few a few caveats to this。 Most， the issue is a little bit。



![](img/2b0d9153ffb5633d887845dcada1e348_1.png)

![](img/2b0d9153ffb5633d887845dcada1e348_2.png)

![](img/2b0d9153ffb5633d887845dcada1e348_3.png)

Just in the marketing of the paper， the paper itself is actually pretty good and pretty okay。

 In fact， it's a follow up to an earlier paper on this RMT model right here。

We're going to look at that briefly， but the paper is essentially a small extension to that other paper。

 namely that other paper did the same thing for autoregressive。

 So for causally masked decoder style transformers and this one。

 the paper even says it's not a paper it's a technical report simply applies the same thing to encoder transformers such as Bt and it actually turns out that this variant right here is simpler so conceptually youd actually read and do this paper right here first and then do the decoder only paper because that you know you have to handle the causal masking we're going to dive into a little bit of this。

 but just to take expectations down a tiny bit this is not this is not the way to go and scale transformer to ginormous inputs in the way that you think this is very。



![](img/2b0d9153ffb5633d887845dcada1e348_5.png)

![](img/2b0d9153ffb5633d887845dcada1e348_6.png)

![](img/2b0d9153ffb5633d887845dcada1e348_7.png)

Well get。 We'll get into it。 So there is a。

![](img/2b0d9153ffb5633d887845dcada1e348_9.png)

There is a diagram right here that shows about how this is going to be achieved。 Naly。

 we're going to we're going to have text like blah， blah， blah， blah。

 blah really long sequence of text that doesn't fit into a transformer。

 Transformers suffer from quadratic scaling their attention mechanism requires huge amounts of memory。

 that scales quadraically with input length。 So if you have a segment like this。

 And if you want your transformer to consume twice as much tokens。

 then you need four times as much memory， four times as many tokens 16 times the amount of memory。

 you quickly run out of memory。 So that's why this paper or this method considers chunking the text into like into chunks into sequences or what they call segments and then processing each segment with a transformer and then somehow connecting these segments together over inference。

 This is obviously not the first time we are seeing something like this also。



![](img/2b0d9153ffb5633d887845dcada1e348_11.png)

They themselves say so。 There have been previous attempts。

 such as transformer X L and various other things way， way back in the day in like 2020。

2019 already that did an approach like this。 newer approaches to extending the sequence length of transformers are。

 for example， things like longform big bird and big bird and so on， No， big bird。

 not big B that do consider the whole sequence， but they do something like they say， okay。

 if we process this token right here， we only do local full attention。

 And they're going to do some kind of a sparse attention to the segments that are sort of outside of our local segment。

 And then some special token attention to maybe like the very first token in the sequence because that might be more important or something like this。

 So everyone's been sort of helping themselves with getting around this quadratic attention。



![](img/2b0d9153ffb5633d887845dcada1e348_13.png)

![](img/2b0d9153ffb5633d887845dcada1e348_14.png)

![](img/2b0d9153ffb5633d887845dcada1e348_15.png)

![](img/2b0d9153ffb5633d887845dcada1e348_16.png)

Again， this paper considers chunking the text into multiple segments。

 So they process each segment with a transformer。 And here， think of Bt。

 Think of a task where you need to input an entire sequence and then classify that entire sequence。

 In fact， we can go look at the tasks they consider right now。 The easiest is a memory。

 memorize task。 So the memorized task consists of text， right， There is text， text X， X， X， X text。

 somewhere in the text。 there is a fact。 The fact might be something like this。

 Daniel went back to the hallway。 And then at the very end of that sequence。 There is a question。

 So all in between， they just fill in text。 that's just noise。

 that's just there to confuse the model is just random text。 to grab something from Wikipedia。

 just inserted here。

![](img/2b0d9153ffb5633d887845dcada1e348_18.png)

![](img/2b0d9153ffb5633d887845dcada1e348_19.png)

![](img/2b0d9153ffb5633d887845dcada1e348_20.png)

![](img/2b0d9153ffb5633d887845dcada1e348_21.png)

![](img/2b0d9153ffb5633d887845dcada1e348_22.png)

![](img/2b0d9153ffb5633d887845dcada1e348_23.png)

So at the very end， there is a question， where is Daniel and the model is supposed to answer hallway。

 either by classification or by pointing into some vocabulary。

 there are various ways to implement that。 but you can do it with a transformer like Bt。

 this is in essence， a sequence classification task into like a preset vocabulary。

 So if this here was smaller than， let's say， 512 tokens。

 then you could just feed it into Bt and have Bt train and answer the thing。 However。

 if this is longer than the birdt context size， then you need to go to a few tricks。

 So the memorized tasks considers obviously， text that is longer than just one segment for the purposes of this paper。

 There's also the detect and memorize a task which is slightly harder。 So in the memorized task。

 you're guaranteed that the fact is always。

![](img/2b0d9153ffb5633d887845dcada1e348_25.png)

![](img/2b0d9153ffb5633d887845dcada1e348_26.png)

![](img/2b0d9153ffb5633d887845dcada1e348_27.png)

In the first segment and in the detect and memorized task， the fact could be anywhere。

 so you also have to detect where that fact is in any of these sequences that you need to remember and then at the end answer。

By the way， remember here is is only technically done in this。 you could also。



![](img/2b0d9153ffb5633d887845dcada1e348_29.png)

Like a longformer or something like this would not use memory。

 but they would simply have or rely on some sort of attention from the question to the place where the fact was written。

 So that's how a normal transformer would do it。 This paper right here will write something into memory。

 and then consider that memory in the last segment right here。



![](img/2b0d9153ffb5633d887845dcada1e348_31.png)

There is a reasoning task where it's even slightly more complicated， so there will be one fact。

 there will be another fact somewhere in the sequence。

 And you need to consider both facts in order to answer the question at the end。

 They do have examples right here， but I think the examples is is kind of wrong。

 So fact1 would be the hallway is east of the bathroom。

 factact2 is the bedroom is west of the bathroom。 And the question is what is the bathroom east of。



![](img/2b0d9153ffb5633d887845dcada1e348_33.png)

![](img/2b0d9153ffb5633d887845dcada1e348_34.png)

And the answer is bedroom。 But I think like just looking at this， I only need fact 2 to answer that。

 I don't even need fact1。 So maybe this is just kind of a wonky example that they've tried to give right here。

 I， I don't see how fact1 is relevant here but I trust that the actual data set。

 this two way relation B A BI task actually has two way relationship data points。



![](img/2b0d9153ffb5633d887845dcada1e348_36.png)

![](img/2b0d9153ffb5633d887845dcada1e348_37.png)

![](img/2b0d9153ffb5633d887845dcada1e348_38.png)

![](img/2b0d9153ffb5633d887845dcada1e348_39.png)

Okay， now that we know what we're dealing with， let's look at how this model does it。



![](img/2b0d9153ffb5633d887845dcada1e348_41.png)

What we need to do is， at least in， in this sense， as I said。

 we need to have a way to carry information over from one segment to the next segment to the next segment and so on。

 And they implement that by forms of these memory tokens right here。



![](img/2b0d9153ffb5633d887845dcada1e348_43.png)

So in a regular transformer， you simply input your text segment as tokens。

 so there's going to be token， token， token， token， token， token， and you train that using causal。

 not sorry in Bt， you train that using mask language modeling or something like this what they do here is they add a series。

 a fixed amount of memory tokens， let's say there are eight memory tokens here and。The output。

 obviously， is going to be， again， the number， the number of tokens right here。 Now。

 whether you train those or not， that's up to。 I think they start with a pre trained birdt and。They。

 they don't do the masked language modeling during training of this。 So they only fine tune the task。

 but you still， it still output those tokens， and you'd also output 8 new or 4， let's say 4。

4 new memory tokens。 So four memory tokens go in。4 memory tokens。 get out。 Now。

 these aren't the same tokens， but you just。Dedicate slots and say these are the memory tokens of the input。

 and these are the memory tokens of the output。 and you take the memory tokens of the output and you feed them back into the input right here。

 And again， there is transformer layers and you feed there are output tokens。 and you take them。

 So this is how you can store information。 Let's say there is an important fact right here in the text。

 The transformer by means of attention mechanism， transforming things across their layer。

 could use that to store that fact somehow into these memory tokens。



![](img/2b0d9153ffb5633d887845dcada1e348_45.png)
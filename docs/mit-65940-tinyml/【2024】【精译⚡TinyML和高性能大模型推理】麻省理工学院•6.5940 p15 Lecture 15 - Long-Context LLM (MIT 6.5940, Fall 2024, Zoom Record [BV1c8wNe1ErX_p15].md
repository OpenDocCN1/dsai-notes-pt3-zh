# 【2024】【精译⚡TinyML和高性能大模型推理】麻省理工学院•6.5940 p15 Lecture 15 - Long-Context LLM (MIT 6.5940, Fall 2024, Zoom Record [BV1c8wNe1ErX_p15]

Hey good afternoon everyone let's get started so today we are going to talk about long context large language model for efficient so long context is pretty interesting where you want to understand pretty long documents and also you want to understand there long videos。

 multimod models。So in order to save the memory， we will learn a lot of techniques to reduce the memory consumption。

 to make it run faster for both the training and inference for long context， large language model。

So this is the agenda for today， where will first cover a recap of the context of extension methods like using rope and the introduced L Lauraura technique for training。

We're also going to talk about inference evaluations for long content and OM。

 like the loss in the middle phenomenon， needle in the haystack， long bench。

We also talk about efficient attention mechanism for long context inference。

 including the streaming IOM dual attention and query a very sparseity。And finally， if we have time。

 we'll talk about SSM's state space models， so let's start with a recap of the rotary positional embedding。

So rotary positional embedding is a popular implementation for relative positional embedding。

 so each token not only have its own embedding vector but also has the positional embedding we've learned in the previous lecture the rope rope basically chops the input into two segments and pair and so that we can have Xy pair between the first element and d over two element and that becomes a Xy in the2D dimension and then we can rotated by m data M is is related to its position data is pretty pretty large number such that you can distinguish many numbers before you rotated by2 pi and then we can see on the right hand side when we are doing the tension between Q and pay it becomes the multiplication of the magnitude。

And subtraction of M minus n of their angles。 Okay。

 so the phase angle of the inner product of two complex vectors is actually the phase difference between the two complex vectors and minus n。

 So the result is only related to the relative position and minus n。

What if you won't want to extend the contacts window？So previously。This is the original laina。

 you can handle the contrast length up to 2K What if you want to extend it to 4K and we should not just continue extrapolate。

This is the same range， but instead we should double the frequency。

From every here we have this distance we have two dots now we have four dots in the same distance。

 so basically we are dividing beta by two so that we can still use the same range to represent the 4 4K range。

So IOMs usually need to be fine tuned after extending the context life。

 but fine tuning under long context is pretty expensive， so how do we make it more efficient？

So we introduce a technique but long Laurara。Just use a single GPU to fine you a about 70 billion parameter model under long context。



![](img/98f73413e13a6cb4d410a79dd43ab296_1.png)

For example， this is a book， Harry Potter below is the section of the book。



![](img/98f73413e13a6cb4d410a79dd43ab296_3.png)

You give all the content right here， now the paper the book ends。

 please tell me what high level idea the author want to indicate in this book altogether we have about 30 k tokens if you feed it with Baive。



![](img/98f73413e13a6cb4d410a79dd43ab296_5.png)

![](img/98f73413e13a6cb4d410a79dd43ab296_6.png)

The original Lama2， which has 4K context left， which is much smaller than the 30K。



![](img/98f73413e13a6cb4d410a79dd43ab296_8.png)

Tokens， it will expect very poor result。

![](img/98f73413e13a6cb4d410a79dd43ab296_10.png)

Another work。How the long Lama they used 128 TU V3， that's a lot， lot of compute。

 which is usually unaffordable。We'll introduce a technique called L Lauraura In fan tuning。

换q name为70 billion parameter two to 32 k，32 k contact last using only one node one node a eight card one node a100 GPPU。



![](img/98f73413e13a6cb4d410a79dd43ab296_12.png)

So let's see how that works。So under long context， what is the bottleneck。

The attention is the bottleneck right since transformers has two components。

 one is the attention that models the information across tokens。

 the other is the f that apply nonlinear linearity on the individual tokens。

Which is the bottleneck and the long context。The attention， right。

 the attention is the bottleneck because the attentions computation complexity grows grows projectally with the token life。

So when the content lung is pretty large， attention becomes the problem。

So how do we simplify the attention mechanism previously we have to run the entire the bottom triangle for the causal mask but in here we find it enough for us to just to group this kind of sparse block sparse attention only within this group of four tokens。

These four tokens only attend to each other within this room。Similarly。

 these four tokens only attend to each other within the group， but not beyond the group。

If we just do such block sparse， diagonal， block sparse attention。That's problematic because。

 these two groups will never talk to each other。So how do we solve that problem？

We can actually shift。The tokens now shift the attention mask。By half， right。

 so therefore these four tokens becomes two plus these four tokens are these four tokens。

So half of the head will use this sparssity pattern。Half of the hat， we use this parsity pattern。

 so what happens if we put them together？We will see these two groups， the red group。

 and the blue group group， they will talk to each other through the intersection right here。

 so things were shifted by half。So now all the tokens can effectively talk to each other if you stack multiple layers。

 if you stack just one layer， this red and this blue can talk。还有菜。And you can stack two layers。

 this red and talk to this blue and talk to this red so such。

InSuch information mingling can actually propagate as you stack multiple layers。

So that's using this shift sparse attention to simplify the attention mechanism。开是。Except to。

Because this is due to the shift。Here's the shift。The blue part。

There is a small triangle here and the rest is shifted to here。

That is a square because the part of triangle is right here， right here， and here。

Did you see a two by two bundleangle here on the top， It's overlaid。Another two白 two here。T go here。

And that's where everything have here。So the total area stays the same。Yeah。

So that's shifted the sparse attention。And the second technique we find super helpful is to enhance the Laurara。

 we talk about Laurara in the previous lecture， we should also find to not only the layer branch。

 but also the input em bedding and also the normalization layer。

We've visited normalization later many times， for example， in smooth plant and AWQ we basically。

Md those scaling factors into into the normalization layer into the bias and also the scaling factor of the normalization layer。

 so here we are also tuning the normalization layer， not only tuning the lower branch。

 the lower rank branch， but also the normalization layer the norm before multi highide attention to norm before the feet forward and also the input embedding layer。

The fire here indicates that we are cuning back here。

So we avoided tuning this bulkchi fator and also the multihyeration layer。To save the computation。

多个好请喺情都比下咯。对这。So here we have multiple groups。So half of the hat is like this。

 half of the hat is like this， each hat is two individual。This is just what had。

This is one particular hat is like this， one particular hat is like this。What have。

this is not communicating between hass， this is communicating between tokens。

So these four tokens and the second four tokens cannot communicate if you only have this vity pattern。

This is within the hat， just a single hat， the first floor token and the second floor token。嗯。

This is the other this is the other pattern， which is default the from the third to the。

To the sixthO right。They are coming from the same2 VO projection， right， so this is one two four。

This is 26。嗯。So this is put in more detail， how do we implement the spars shift to the patient okay so well be first。

grouped by divided by two right half of the had and versus the other half of the had in this example we have four we have four heads and here we have eight tokens。

We have eight tokens and we have four hats， we first split it by half okay half of the hat versus the other half and then we shift half of the head。

You can see the one， two， three， four， five， six，7， eight， you can eight， one， two， three， four。

 five， six，7 okay。And then we group it。Here， every two tokens are group together will only do local attention within the group。

And then the other half of the head。We do shifted attention like this。So this is during training。

 we run this shift as farrs as attention。And at inference time we ran the full attention。

So let's see how does that perform， we are saving a lot of computation doesn it hurt the accuracy。

So this is exactly the perplex， the lower， the better。

So the blue one needs full attention will long lower up and pretty much match the complexity of the full attention versus just using the Laura when the content gets longer。

 the complexity will explode， showing that Laura is not enough。And what about a tweaking hour？

The full attention can train up to 32 to after that they will be out of memory。

Using Laura can definitely shorten the training training hours and can extend between 32 to actually 6464。

However， you can see the complexity of flura is pretty high。But along lower rise right here。

 all the way to 64 64 k to Queens。And remain the lowest in the training time。

Here we did some observations starting to see。Whetherather it's helpful to remain only half of the remain P1 and P2 here means。

Attion high using pattern one啊all no shift。And add in tool， I'll shift， right？

We don't shift versus everything shift does not performed as good as divided by two groups。

And cross the tension hat。Other sparseity technique。Tation block， spae。

Im trying as far as across the head doesn't perform my school compared with。The eyes as to attention。

And in particular， the lowest。Pplexity is achieved when we are testing with full attention and training with a shifted sparse attention but a test with the full attention。

And then let's see， how does Ni Laurara work。But we also tune the input embedding and also tune the normalization that you。

 used two are very cheap to tune。For example， the normalization layer has very few parameterss。

We have very limited additional cost， normalization layer， 0。004%， embedding 2%。

But compared with Fu F Chuning even using the Laurara。As you increase the rank。

The prop still remains pretty high， like three points higher than the full fine tuning。

If we add normalization tuing， normalization tuning， it becomes a little better but at one point。

And at both normalization， embe tuning， it becomes pretty much matching the original full fine tuning complexity。

And here we are using very low rank， just eight。Compared with I using LauraRA， if you use 256。

 still doesn't work， but here we just use a rank of eight plus normalization emdding fine tuning。

It can work as well as full fine tool。So let's try it on a few scenarios。

 so this is the past key retrual task。What is past retrieval， so this is a very long document。

And we insert a pass key， one，2，3，62， remember it， one，2，3，62 in the pass key。

And then we have a lot of ir related text， the grass is green， the stars is blue。

 the sun in yellow here， here we go。They repeated several times。

 and then finally we asked what is the past key， the past key is。

And try to see if we can correctly output this one，2， three，6， two as the result。

So using the original Lama 27 B， which has 4K context life。The past skill retrieval accuracy。

Jobs very quickly， almost zero after 4K content enough。But after using L Lauraura。

 we can extend it into 32 to 32K。And if we extend。The positional coding we can all the way go beyond 40k very effectively。

To extend the context off in the past few retrieval task。Okay， so let's see。

 how do we evaluate the performance of long contact I M， So let's first introduce。

The popular lost in the middle phenomena。So the loss in the middle phenomenon is saying that the accuracy is pretty high in the beginning。

 and in the end， but the accuracy in the middle is pretty low。So very high accuracy。

 when the relevant information appears at the start or the end of a context。

But very low accuracy when the relative information is in the middle of the text。key insight。

 insight is that。A very fluent long contact response doesn't imply you can remember the stuff may I it's highly possible the language modeling。

Perplexity is pretty good， but you're forgetting the things in the middle。Therefore。

 perplexity is not enough， we need more rigorous evaluation。To understand。

The capacity and performance of lung contact or。So we'll introduce two benchmarks。

 one is needle in the haystack， the other is the long bench。So以 needle in the haystack。

Is a pressure testing for large language models under the long term text。



![](img/98f73413e13a6cb4d410a79dd43ab296_14.png)

How does it work， so we have two axises， one leaves the context loss。From1 k 10 k，2 k here to 128 k。

And the Y axis is where do we place？The needle in the document。Okay， so this is。

Start of the document this is 25% in the middle of 50%。This is 75%。

This is in the bottom in the end of the document， where do we replace the needle？

And we can see if the screen is showing that you have 100% accuracy to retrieve that needle in the hisstack。

Yellow means you have 50% accuracy。My ra means also have0% of accuracy。

And we can observe when the context length is pretty short， like 1 k 10k， 28k。

 everything is green right you can retrieve very accurately in the beginning。

 in the middle and also in the end， right。However， as the contexts document gets longer。The accuracy。

Its not is becoming worse， starting from like 73 k。The very beginning accuracy is still pretty good。

 like 100% right here， right here， but in the middle， like 25% to 30%。

You have zero% accuracy of retieving your pass key。In the later in the later part of the document。

 the accuracy returns to 100% again okay， so that's the loss in the middle problem begins to appear。

It gets even worse when the context gets longer， like 128 k， even at about 75%。

 you get only 65% of accuracy of retrieving that task key。



![](img/98f73413e13a6cb4d410a79dd43ab296_16.png)

So in short， this needle in the haystack。哎。Basically inserting the information we call it the needle okay at a different depth of a long context document of a long document。

 like we call it the hayt。

![](img/98f73413e13a6cb4d410a79dd43ab296_18.png)

This is a smaller haystack only 1 k， this is a larger haystack， 128 k。



![](img/98f73413e13a6cb4d410a79dd43ab296_20.png)

A similar example of needle could be something like the best thing in San Francisco is eating a sandwich and seeking the。



![](img/98f73413e13a6cb4d410a79dd43ab296_22.png)

Dororis park on a sunny day， and then we asked the model at the end of the document at the end of the haystack to recall the information which is the needle。

What is the best thing to do with in San Francisco。

 and I should answer to eat a sandwich and sitting a dollars par on a sunny day to find this needle in this long document in his hasystack？



![](img/98f73413e13a6cb4d410a79dd43ab296_24.png)

Another benchmark is called the Long Ben。To evaluate the lung context capability more comprehensively。

The needle in the haystack is a still artificial。Synthetic benchmark right。

 but this is more real world a real word that does for example。

 include different tasks like question answering， summarization， future learning。



![](img/98f73413e13a6cb4d410a79dd43ab296_26.png)

The English and Chinese。

![](img/98f73413e13a6cb4d410a79dd43ab296_28.png)

And support contacts up to 13 k tokens， which is still not quite long。

With automated evaluation metrics。

![](img/98f73413e13a6cb4d410a79dd43ab296_30.png)

And it can consists of not only synthetic data， but also code data， single document Q A。

 multi document Q A summarization， few short， few short questions。



![](img/98f73413e13a6cb4d410a79dd43ab296_32.png)

And the key finding is that。Tecs like the scaled position embedding。

Can you improve the lung complex understanding。The techniques like context， compression。

 retrieval and help， but not as effective。I models inherently designed for lung contacts。

Given those benchmarks， let's see how do we improve the inference of long contact larger language models？

I's first recap the concept of KBC， which we learned in the previous lecture。

To keep cash grow linearly as the number of tokens increase。



![](img/98f73413e13a6cb4d410a79dd43ab296_34.png)

So it's a multiplying the mini batch size， the number of layers。

Numb of K has the dimension of the inding the lungs of the sentence K and V to elements and the precision。

 Okay， so it's two and half megabyte。

![](img/98f73413e13a6cb4d410a79dd43ab296_36.png)

![](img/98f73413e13a6cb4d410a79dd43ab296_37.png)

For each token the 70 billion parameter model， where the batch size is one sequencechd lung is5 12 is one me by。

About size of 16 sequence on the 4K thats 160 gigabyte by 2 100 GPU。



![](img/98f73413e13a6cb4d410a79dd43ab296_39.png)

![](img/98f73413e13a6cb4d410a79dd43ab296_40.png)

And this Kb H size will grow linearly with the batch size。

 sometimes even easily outform easily surpass the model size okay。



![](img/98f73413e13a6cb4d410a79dd43ab296_42.png)

So we'll introduce three techniques to solve this problem of large KV cache size。



![](img/98f73413e13a6cb4d410a79dd43ab296_44.png)

Well the first technique is streaming OM and attention is sync。

 second technique is dual attention and the third technique is quest area very pricey。



![](img/98f73413e13a6cb4d410a79dd43ab296_46.png)

So let's talk about streaming IOM for long generation in streaming applications。

So we need large language models in streaming applications such as multi round dialogues。

 where you want to continuously interact with a chatbot non stop。

But this is very challenging because long conversation require extensive memory consumption during the decoding stage。

For example， using the transformers， using the original transformer， the memory。

 the memory will grow linearly with respect to the number of tokens。



![](img/98f73413e13a6cb4d410a79dd43ab296_48.png)

![](img/98f73413e13a6cb4d410a79dd43ab296_49.png)

![](img/98f73413e13a6cb4d410a79dd43ab296_50.png)

So the y x axis it here is input the sequence stop。

 and the y axis is the perplexity versus the memory， okay。So the memory will grow linearly。

 but the propplexity will stay good in the orange curve。And Q4K。

 which is the Lamau when and Lamau is trained after4K the complexity。



![](img/98f73413e13a6cb4d410a79dd43ab296_52.png)

F it no longer works。

![](img/98f73413e13a6cb4d410a79dd43ab296_54.png)

Another work using the window attention doesn't solve the problem either。

 it solves the problem where the memory can stay constant using the window attention。

 but the complexity will explode as in the green curve。

 it will explode as soon as the first token in the window is evicted。



![](img/98f73413e13a6cb4d410a79dd43ab296_56.png)

![](img/98f73413e13a6cb4d410a79dd43ab296_57.png)

So our T Guangshui developed a technique for the streaming LOM that can handle this problem Okay。

 so without streaming IOM。

![](img/98f73413e13a6cb4d410a79dd43ab296_59.png)

After a while， the model performance will break， but with streaming alarm on the right。

 you can continuously interact with the chatbot nine stop。Finally。

 the mainstream streaming online will get out of memory as the conversation gets up。

So how do we prevent either model performance breaks？And also prevent。The model to run out of memory。

So let's visit a few techniques。For example， if you want to keep a constant memory。

A natural thinking is rather than using all the keep everything in the KV cache。

 can we just remain the local tokens in the KV cache and use a window attention。

 only keep the most recent tokens。Only keep the most recent in this example。

 the most recent four tokens in the KB cache。So here we have our cached tokens。



![](img/98f73413e13a6cb4d410a79dd43ab296_61.png)

But you can imagine the perplex will be very poor。

![](img/98f73413e13a6cb4d410a79dd43ab296_63.png)

It will become a reporter pro as soon as the first token in the KB cash is evicted when are tax launch。

Protex slump， surpass other the cash suck。

![](img/98f73413e13a6cb4d410a79dd43ab296_65.png)

So here we actually see two failures， one is one using a window attention in orange。

When the input length is longer than the kidney has size where the first token is evicted。

 the perplex will explode the orange the second failure case is the dense attention in the blue part when the input length exceeds 4K。

 which is a pre traininging life。

![](img/98f73413e13a6cb4d410a79dd43ab296_67.png)

Which is the pre traininging valve， the complexity will also explode。What about other techniques。

 like dance tension。

![](img/98f73413e13a6cb4d410a79dd43ab296_69.png)

Of course， the efficiency is poor and require O square complexity。

For the efficiency perspective and the perplex will also explode as the size will exceed the training content now。

 we talk about window tension， although the memory is good， but the perplexity is pretty poor。



![](img/98f73413e13a6cb4d410a79dd43ab296_71.png)

![](img/98f73413e13a6cb4d410a79dd43ab296_72.png)

We can also using a sliding window with recompation。

The complexityity stays pretty good since we are just get rid of the KV cache and recompute every time but the compute is all Tl square L is the length of the recomputed tokens。

And it's quite unaffordable。 T is the total number of cash tokens。



![](img/98f73413e13a6cb4d410a79dd43ab296_74.png)

So we observed an interesting phenomenon called Tjn Think phenomenon， where starting from Mayor2。

 the first token is very heavily attended。So this is the tension map。

 the first token is on red similarly for the other layers and other head。

 the first token is on red is very heavily attended。Why is that the case？

Because we are using the soft maps and make sure for different tokens。

 the attention score needs to sum up to one。EvenEven if some of the tokens does not need to attend to anything。

 they still need to sum up to one， so they need to dump the attention score to some of the tokens。

On the first hookken is globally visible due to the auto regressive nature of。The geneative model。

 right， so the model decided to dump those redundant token attention score into the first token。

 which is right here， The first token received very heavy attention score。Very interestingly。

 we observed this phenomenon like three years ago， but in the 2021。

 the Spartum project sparse pension project， but we were not able to explain it that at that time。



![](img/98f73413e13a6cb4d410a79dd43ab296_76.png)

![](img/98f73413e13a6cb4d410a79dd43ab296_77.png)

For example， in this sentence， he is a very famous researcher in the computer architecture area and published many papers。



![](img/98f73413e13a6cb4d410a79dd43ab296_79.png)

But we find it。Attend very heavily to the first local right here。



![](img/98f73413e13a6cb4d410a79dd43ab296_81.png)

That's not。

![](img/98f73413e13a6cb4d410a79dd43ab296_83.png)

Just a singles case that's actually appeared in GB2 in 2021。

This is several other examples using G2 for language monoing like Du Fu was at the great poet of the Tang dynasty。

 etc， we find many tokens can be safely pruned but Fu was a grid can be safely pruned。

 but do the first token can never be pruned， which was very interesting。



![](img/98f73413e13a6cb4d410a79dd43ab296_85.png)

And later we find the first hookken is the attention sink， which should not be proved。

So this is the rationale behind the tension scenes where the softm operation basically like everything sum up to one。

 so you need to dump those redundant stuff in the first token because it is globally like this sentence where it's globally visible to all the subsequent tokens because of the autoregressive modeling。

And we naturally ask the question。The important， the first token is very important。

 we call it attention sink。Is it due to their position or is due to their semantics？

So here we did an experiment。The window size here is 1k。啊。

If you have zero attention sink token complexity will explode to our告。If we have four attention。

 think tokens fast 1020。Window， the perplex is getting normal， but if you insert four line breaks。

Blind bricks， they have no semantic meaning。Was a window of 1020，1020。

 the prop still remains pretty low， okay。So we find adding initial four slash N with line bricks and also recover the perplexity。

 which is super interesting。Which is showing it is the position that matters， okay。

 not the semantics。So what should we do given the tension sinks？



![](img/98f73413e13a6cb4d410a79dd43ab296_87.png)

We should preserve the key and the value of attention sink topics。

 never elic them from the K cache just I always have these yellow attention sink in the k cache。

And then we keep a sliding window for the later tokens， four five，67。

56786789 using such a window to carry cache。

![](img/98f73413e13a6cb4d410a79dd43ab296_89.png)

One thing we need to pay attention to is the position impding okay。

 we should use the positions in the cache rather than in the original text。



![](img/98f73413e13a6cb4d410a79dd43ab296_91.png)

This is the position the original text，1，0，1，2，3，4，5，6，7，8，9， okay。So this is the。

Position in the cache， so from three， we directly go to four rather than go to six。



![](img/98f73413e13a6cb4d410a79dd43ab296_93.png)

So that's something we need to take care when we arere implementing that。We talk about page的 tension。

啊， so so how should we implement streaming OM in page的弹讯。

I should we just always pin the first KV page。In the during the page attention。

 right since each page is roughly 16 3264 tokens。The simple implementation could be quite simple。

 we just always pin the first page in the K page。So let's see the comparer and performance。

But dense attention， which is in blue， it will fail。

 the complexity will explode beyond the training retrain attention window size。

 like 4K for nano models。But window attention， which is in orange， it will explode after。

The input exceeds the cache size when the first token， which is the sync token is evicted。Well。

 assuming me I am， how you read shows very stable performance。I'm very close the。

Sliding window with recomp baseline。And here we tested it all up to 4K。

4 medium total still didn't show any failure。It might be even longer but we didn't test it。

Efficiency wise， we compare with the only working version which is recomputation without givingB cache。

 actually we find as the lungs get even longer the speed up。



![](img/98f73413e13a6cb4d410a79dd43ab296_95.png)

It's getting larger。 and， the more。You generate the more you save。And here is comparing the memory。

 so streaming OM has consistently lower memory and the faster speed。



![](img/98f73413e13a6cb4d410a79dd43ab296_97.png)

Here we alate how many attention things do we need， why do we need four attention things？



![](img/98f73413e13a6cb4d410a79dd43ab296_99.png)

So we tried zero， of course。It doesn't work， the complexity is to be one，2。

 four find for example number 27 from 11 to 10 to 9。

 four is a sweet spot after increasing the number number of things to eight it doesn't have much。

 so four is a very practical number of attaching things。



![](img/98f73413e13a6cb4d410a79dd43ab296_101.png)

嗯。是。应该。Is this so。Yes， yes， that's very related， actually that's the next slide。

What if we apply a dedicated learnable token to the beginning of a sentence。

 no matter if it's a language or is image， we apply a dedicated learnable token to introduce an actual learnable token at the start of all the true new samples and I see how how that works。



![](img/98f73413e13a6cb4d410a79dd43ab296_103.png)

Actually using this learnable sink， okay？Compared with the vanilla model， just using a single token。

 the vanilla model has 18。49 perplex versus the verable thing has 18。01 okay。

Its performed quite good compared with using the vanilla without a dedicated attention sink and we no longer need five or four sinks here we just need one learnable sink so when you are training the model。

 you can insert is a attention sink。

![](img/98f73413e13a6cb4d410a79dd43ab296_105.png)

And let's see for the vision model。People also find these think tokens like right here， right here。

 these colorful dots。These attention sink emerge in low semantic background pixels。

So for the bird this insect think in the middle， but in the background。

 low semantic background pixels， we observe a lot of attention things。And similarly。

 for the bird model， the bidirectional。ABt model attention sink are thosepar separator tools at the end of all the sentences but in the end right here is very red。

So VIT and bird model， those encoder models also have attention six。

But streaming does it equal to long context， for example we。He's designed this experiment。

Have a query， have a register for line zero is something for line 10 for line 20， et cetera。

 and then we ask the register count line 0 is we try to retrieve with 8806。

And then we keep adding new contents and try to look back ask the content。

And we find actually when the cache configuration is。

Like the cash has 2044 plus four sync tokens will earn the token business。

This is the distance between the queryrry and the token and the needle so when the token distance like 2300 exceed 204。

The actual不 zero。I don't know with the cash4K by the humans。4。6 k right here。

 the accuracy will also drop to zero because you are the content is eed from the cableV cache by no way you can retrieve it。

So let's see how do we solve this issue， Let's take a five minute break then we are talk we are going to talk about due attention and query a very sparsity to solve this issue。

啊。Let's continue with deal attention for long context large language model so due means two right we have two kinds of attention hass。

 one is the retrieval head， one is the striping head and let's see how do we exploit these two kinds of head to improve the efficiency of long contact large language model。

So the problem here we want to again want to solve this long context problem。

 we want to understand long documents， long images， long videos， for example。

 one input image 224 by 224， nowadays we can convert it to 256 tokens using clip or SL。

U using that for one hour long video sample at one frames per second that equal to roughly1 million tokens。

 so we need to handle efficiently handle those long context LOM to handle long videos。

 higher resolution images and long documents。However。

 with only a taking gig bit of memory nowadays this La 38B decoding can handle up to 500 k tokens beyond that like 600 k they will get out of memory so this is latency。

 this is a memory beyond。Beyond the 500 k， the memory is more than 80 gigabyte。

But this new attention mechanism can handle here all the way to 1 million tokens。

 actually we tested all the way to three million tokens。

 you can combine that with head cash quantization。And also it gets very significant speed up and I see how dual attention works。

被款。So the challenge we are trying to solve is one is the memory bottleneck。

 one is the decoding latency so storing all the KV stats states across all the hass will consume massive amount of memory right so like 137 gigyte for one million contacts in number3 8B。



![](img/98f73413e13a6cb4d410a79dd43ab296_107.png)

The other is the decoding latency。Which grows linearly with the sequence length。

And some of the existing KB cash compression technique。

Like H to O streamping now I'm toldma will damage the lung contact capability。

Like we see in the last slide。So to solve that problem。The dual attention。

 accelerate both the prefiing and the decoding， reduce the KBh size and preserve the long context performance。

So on the left is the full attention on the right is the dual attention， okay。

 almost half the GPU memory， 78 gigabyte versus 49 gigabyte。



![](img/98f73413e13a6cb4d410a79dd43ab296_109.png)

![](img/98f73413e13a6cb4d410a79dd43ab296_110.png)

And the total time is also halved for the preient stage from。4000 seconds to 2000 seconds。

And here is' at the decoding stage Okay， so each token。

With full attention require 864 milliseconds now is halved as well。

 almost2 x speed up for both the encoding stage and also the decocoding stage。



![](img/98f73413e13a6cb4d410a79dd43ab296_112.png)

And we can fix up to 3。3 million tokens in the context。

 that's roughly a three hour video sample at one frames per second so we cant understand the whole movie。



![](img/98f73413e13a6cb4d410a79dd43ab296_114.png)

![](img/98f73413e13a6cb4d410a79dd43ab296_115.png)

And let's see how that works。 let's first observe the attention map and see what are we actually attending to。

So there are roughly two kinds of the hass okay so the sentence here is the best fruit is orange。

 what is the best fruit orange okay so the first kind of had。

The attention is we pay attention anywhere for example， we have 3。1 2。94。

7 these three dots near best fruits and orange Okay so we call them retrieval head so you can capture。

The information between the generated token to all any of the previous tokens versus the other kinds of head only attend to itself。

 the local tokens versus the first token you can see it's very similar to the streaming armss pattern where only the local tokens and the first token is attended。

Similarly for other similar token like this， none of the things in the middle is attended versus for the striping head。

 you can densely attend to anything。A in the middle。

And then what if you try to prune some of the some of the？Pass okay， so if we try to prove。

Onlyway which if you try to prove the retrieval had， the accuracy will drop very。

 very quickly at least job like if yourun 20% the accuracy goes to nothing。

But if you prove those streaming had like this， this is the streaming head。

 the accuracy will stay pretty much unchanged。And if you improve randomly， that's something between。

In between。So the insight。Is that not all the attention had need to do full attention。

 attention to everything okay， but we can categorize all the heads into two groups。

 one is the retriebutval head， which is the original dance attention frame focus on important tokens from earlier tokens in the sequence basically anything can attend to anything。

The other kind is the streaming ad， which only focus on the recent tokens and the attention scene tokens。

 okay？It only did a very small ca cache， beside size equal to the number of the attention sinks。

 which is no roughly before and also the recent tokens。Which is constant。

 no matter how long your conversation goes， the window of the attention of the streaming head stays the same。

So the solution of give attention basically applied the full KB cache to the attention head and use a very lightweighted constant size cache for the streaming hass。

 okay so this is the retrieval has KB cache which grows linearly with the sentence length token length versus the streaming head only the sink in yellow and the most recent tokens。

 which is constant size of the KB cache。And let's see how do we train？

TheA法 so that we can determine whether a head belongs to attention had streaming head or the。没吹有海。

Okay， and we expect the algorithm should be very simple， right。

 such that we can train it using just a few GPO hours。Hopefully just one GPU， right？

So here the algorithm is very simple， we train using both full attention and streaming streaming attention。

 but mininggle them together with the learnable parameter， which is alpha， okay。

So assign a trainable gate to each headd。And then the gate。

 the gate of alpha will blend the full attention and also the streaming attention。

 allowing the model to learn which heads are necessary should be the full attention versus it could be a streaming attention。

So here we get alpha尔 times full tension plus y minus阿 times the streaming tension。

This is the full attention the difference between full attention and streaming attention is the mask。

 Full attention using the uses the causal math。 streaming attention uses this lada shape mask。

And then we try to distill them by minimizing the difference between using the full。

 everything use the full attention versus the mixture of this combined version using steel attention and we regularize them by making those alpha small and try to add these losses together with re laws and regularization loss。

So how many parameters do we need to train？So for example， for Lama 27b， we have only 32 layers。

 32 head， we need one alpha for each layer for each head。

 so altogether there's only 1k gate values thats need to be trained。

And that can be completed just in a few hours in One node，8 GPUs， Ava，8 Ava 100 GPUs。

And how do we train that we design a task so right here the traininging example is a lot of long paragraph followed by remember the sentence of words is the first pass key pass key to the mod。

Limazulu golf Pa say something random as the first task key。

 and then we have the second fourth on the tenth pass key right here， we want to。

Retrie what is the first to the 10th past and add loss to Li Mazru golf Papa， etc ceter。

And here it show。32 layers， 32 hats， we have 3 1000 altogether 32 by 32 gates。

 what is the value of the gates if the gates is blue it's very small we can prove them away and that is riing head if it is red showing a needs to be pretty large and they need to be the full attention hat or we call it in trivialval hat。

So what about at inference time， you can set a threshold if alpha is greater than a threshold。

 it is characterized as full attention， you need to do the full attention mass。

Versus if the RF is smaller than the threshold， you can keep it as a streaming head。

 okay streaming head the attention map is lambda shaped only recent and sync token。

 the Kb cache size is constant。So what about accelerating decoding versus the prefieding so this is accelerating the decoding part。

 we have two kinds of KV cache， one is the retrieval head where we need to store the KV for all the tokens。

 the other is the streaming head where we only store the yellow attention sink and the most recent tokens。

 therefore it consists of only constant memory。And when we are doing the computing。

 we split them into retrieval and streaming head。An output the book has are concateninated for the final projection。

 who can view the old projection。So this is the decocoum part。

 what about you doing the pre feedingeding stage， so in the pre feedingeding stage we implemented a chunk pre feedingeding。

To split the sequence into fifth length chance， okay， so it's the first chunk， second chunk。

 third chunk， fourth chance okay。So what is time complexity without using your attention？

We have to calculate the area right here in the triangle， which is L square， right， but now with。

The attention of the sink total sink。At streaming has。

 we need only constant all time scale time complexity。

Because here we are keeping the most recent token， which is blue plus red。

 which is constant size of six in this case。So time complexity is reduced from OL square to OK。

What about the binary complexity that's the size in the the length of the Kv patch previously is L grows linear with the number of tokens now is' fixed is k。

 only the first attach sink plus most recent token。

So time complexity is the area of this triangle and the memory complexity is the size of。

The X dimension。So that's where the saving is coming from。

And let's see in practice how much of the tension has could be categorized as streaming high？

The more the better or the lower the better。The more streaming has， the more we say。

 right so we hope the percentage of streaming has to be as high as possible。

So the conclusion here is roughly 40%， 50%， like half half of the KB cash。

 half of the hass is categorized as a streaming hat。

 so actually half of them you can have roughly a negligible KB cash size because theyre constant and then recent token when the total size is long the KB cache size for the streaming h is pretty low。

What about the acres， so this is the needle in the haystack， this is a long bench。Mely the hisystack。

For。This is Lama 2。 This is Lama 3 on the top top and bottom or baseline methods。

Like full attention can be green everywhere， but H2O fails， streaming OM fails， Toba fails。

 fast jam fails， but deal attention can perform very well so even 25% of the hass are this retrieval had showing that you're pruning away three quarters of the hass to be streaming ahead because9 two is MHA。

Versus number3 is GQA， you can pull weight half right and pull away half。

And here is showing the accuracy of the long bench when the sparsity is 50%， catch start is only 50%。

 the retina line still maintains the same as the baseline。

And similarly for short context benchmarks like MTP， MMLU， M bench， under 50% heavy cash budget。

 accuracy stays quite well on these benchmarks。And let's see。

 what is the speed out and memory saving？It can provide about blackx memory reaction for MH， 1。

6 x for GQA model， very y higher for MHA and lower for GQA。

Because for GQA you have less number of highs for the K and V right you are sharing a lot of highs to share the same K and V so the number of H is smaller。

 and it's harder to prune since you have to have exactly multiple highs are sharing the same KB had。

So previously using the baseline method， you run auto ofs memory roughly at 700 k contest loss。

 but now you can go all the way after what meeting。500 k is's like a half an hour video。

 one meeting you can now understand one hour video。

So this is the precuial memory and latency improvement。

This is the decoloding memory and weency improvement。So for the pre feedingeding it's about 1。

7 x latency reduction for MHA and 1。6 x for TQA model。Memory saving is about more than2 x versus 1。

5 x for different benchmarks。So natural thinking is what about if we combine that with KB cash quantization。

 Okay， so deal attention is， you can think of it as p and sparsity。

 you can remove lots of the attention scores。If we combine that with KV cash quantization。

 it can work super well， so by。

![](img/98f73413e13a6cb4d410a79dd43ab296_117.png)

Quantizing the weight to4 bit KV T in the value to4 bitit， we can fit 1。

8 million tokens in a single A 100 GPU。

![](img/98f73413e13a6cb4d410a79dd43ab296_119.png)

![](img/98f73413e13a6cb4d410a79dd43ab296_120.png)

Okay， if we combine that with fourB heavy cash quantization。

 which we talked about previously using Q serve4 bit heavyC we can exceed we can further boost it to 3。

3 meeting topics， that's like a three hour long video， which is pretty cool。



![](img/98f73413e13a6cb4d410a79dd43ab296_122.png)

Okay， so that wraps up with dual attention for long contact large language model inference。

 which can accelerate both the prefiing stage and also the decoding stage using two kinds of KB cache。

 one is the streaming head， one is the retrieval head。So let's talk about another technique。

Let's talk about Que， very very sparsely to accelerate long context， large language model。

So three years ago we find sponsivity appears naturally in large language model， for example。

 in the sentence， bet the video game is a lot more fun than the film and so these are the keys some of the tokens receive a lot of attention like video game is heavily attended but some of the tokens like I the across different tokens they are not very heavily attended so the cumulative。



![](img/98f73413e13a6cb4d410a79dd43ab296_124.png)

ACmulative importance for is pretty low， and so we can safely remove these tokens。



![](img/98f73413e13a6cb4d410a79dd43ab296_126.png)

Which is showing that the KB cash has a lot of redund。

 we don't need to keep all the tokens in the KB cache。So sparsity appears in KVC。

But previous efforts。Have some limitation， for example。

 compared with a dense attention they keep all the contextual tokens。

 which is pretty memorable and intensive， you have to grow the KB cache linearly with the contact site。

Some query oftic sparsity like fixed patent sparsity like streaming OM， like H2O。

 once a token is evicted from the P cache， it can never come back if it is gone， then it's gone？

So we keep the token based on past information if this token is not important。

Here it will never be important in the future， similarly for this token once it' proved based on the previous information when future tokens comes。

 it will never recover so although it solves the memory issue。But the accuracy is pretty low。

But query aware scarrocity basically says。The sparsity pattern should be be should be dependent on which token you are currently decoding。

 so an eted token can still be attended by future tokens。For example， this token， the second token。

 and at this time step， it is evicted， but on the next time step it can recover。

So it can save both the memory and also people are high accuracy so that's the idea of query aware sprsity so the sparsity of the KV cache the sprsity pattern of the KV cache should be dependent on the new query token which you are decoding。

So let's see example where why query where sparsity is crucial。



![](img/98f73413e13a6cb4d410a79dd43ab296_128.png)

你的 sentence isA is B，C is DA is。Upon this moment。A is B， CD， token B is not critical at this moment。

You see the score associated with token B， very blue as of this moment。

But as you go continue to go deeper， A is。B suddenly becomes very important because the result should be B。

 you should decode the next token to decode is B， so although previously at this moment B should be evicted based on the cumulative attention score。

But at this moment。

![](img/98f73413e13a6cb4d410a79dd43ab296_130.png)

BA是B。Reside in the KB catch you can output it okay so which shows the criticality of the dynamic pruning is very important it's highly dependent on the input query of vector  Q rather than static。

So what Que does is using this query a very sparsity in mechanism。

So we keep everything in the KB cache。So we don't save the memory capacity， but we save the memory。

Data movement， so we only fetch those KV pages if it is important。

 otherwise we keep it in the memory， but we don't fetch it。So how do we do that？

When the new query comes right here。This is one by D and D is that you be mention in this case is8。

So we have many exciting pages at each page we may have like 16 tokens。

16 tokens actually is four in this case， but actually maybe be 16 or 68 over 64 in this dimension。

 this dimension is a hidden dimension8 in this case two colors indicates K and V okay first page。

 second page end page the sequence gets longer you have more pages。

So we try to compute which page in the KD cache is crucial。

 if it's not crucial we should throw away some of the KD pages and how do we prune it？

A golden model would be you just multiply the query with each key and see which one is promising。But。

That testing is just too computation heavy right you already did all the computation even if you clonerune it doesn't saving much。

 right？So a smarter idea is to find some representative key and the value key， actually。

Across this entire is four these four tokens actually this example actually is 16 across these four tokens we find elementmin Y is m t and aton Y is max key so the large dot product that only happen if this query is dot product with this mean key for this max so this is the a Y product with min t this is the elementmin Y product with max key and then we find channel find the max between min and max right here so the red one is the largest item and we sum sum it up。

S it up， so rather than doing a do product with every entry like 16 entries。

 we only do product with two entries， the me and the max， item me itemize Mac。

And finally we sum it up as the number to represent the importance of this whole page so this page is large this is large this page is small then we can runrun away this page it still reside in the memory but we don't fetch it from the memory so reduce a lot of data movement。

So this is we put it， how we put it in code。When we are inserting a new token in the K cache。

 we first find。The mean key or the max key okay finding the mean and max。

 when we are performing the self attention when the query comes。

 the query will be modified by dot product with the mean and max and then find the max between them to see whether this page is important。

Okay， let's see how that performs。So this is。10K versus 100 k pass keytrial。This is a long track。

 This is a Ya Lama。 The first first part was the second part。



![](img/98f73413e13a6cb4d410a79dd43ab296_132.png)

We can see if the class can achieve almost perfect accuracy with a page cache size of 60 all the way to 64 when 512 is 100%。

It still remains quite good despite these baseline models like H2 or2wa streamOM completely fails so only 1% accuracy for the cardiovascular retrieval。

 this is temporary this is hydro pain。All the way to 64 and when it comes to 32， that's too small。

 that's too small， it still drops to 65。And for 100 k or longer pass re low originally you need 100 k。

 but now we give it only 4 k4 over 100 that's very small budget。you have 100%，2 case，2100%，1 case。

 slightly dropped696%， although baseline almost go to 1%。

And with 236% that's to 256 tokens that so low get 88% askingkin accuracy。



![](img/98f73413e13a6cb4d410a79dd43ab296_134.png)

So this is 4K all for 100 k that's like roughly 1% which is 1 k over 100 k， that's roughly 1%。

 you still get 96% of accuracy。

![](img/98f73413e13a6cb4d410a79dd43ab296_136.png)

![](img/98f73413e13a6cb4d410a79dd43ab296_137.png)

So this is the language modeling result comparing several methods like COA is very high。

 full attention is in green， bias is in red， it tools in。



![](img/98f73413e13a6cb4d410a79dd43ab296_139.png)

Blue so steam as longer， the propplexity remains low。



![](img/98f73413e13a6cb4d410a79dd43ab296_141.png)

![](img/98f73413e13a6cb4d410a79dd43ab296_142.png)

Very closely match the performance of the four cash model。So this is a result on the long bench。

Whi is a 32 k long chat and we give it only 2 k tokens out of 32K so a budget of 2K tokens can achieve comparable performance as the model with full giving cash。

Similarly， right here， we have only 2K K cash budget，2 K cash budget。And more results。

What about the inff？You we don't save the memory， but we save the data movement。

If the KD page is not promising， we don't load it from the GPPU memory so it can accelerate since datael movement is expensive。

 both energy wise and also latency wise。So this is four different sequence of us。



![](img/98f73413e13a6cb4d410a79dd43ab296_144.png)

So this 8K with a 16 k with 32 k。And the budget is the same with 2K budget。

 and we can imagine the longer the sequence length given the same budget the larger the improvement is from 1。

7 to all the way up to44x。

![](img/98f73413e13a6cb4d410a79dd43ab296_146.png)

![](img/98f73413e13a6cb4d410a79dd43ab296_147.png)

Latency reduction compared with the full cache， this is in the logs， this is in the linear scale。



![](img/98f73413e13a6cb4d410a79dd43ab296_149.png)

And the latency contains two parts， one is criticality estimation and then top K filtering。

 and then the approximate attention。

![](img/98f73413e13a6cb4d410a79dd43ab296_151.png)

So actually the criticality estimation consumes a major overhead。

 which can be alleviated by sharing the criticalityity across multiple tokens。So like Q1。

 Q2 Q3 can share the criticality with Q1 okay so in that way you can save the criticality estimation to emortize the critical estimation。

 or you can you reuse the criticality estimation in layer one。

 reuse it for layer two and three and maybe do it again in layer four etca， two and bit。



![](img/98f73413e13a6cb4d410a79dd43ab296_153.png)

The proportion of this light blue part。

![](img/98f73413e13a6cb4d410a79dd43ab296_155.png)

So this is the end end end to end latency about 2。2 x when a sequence now is 3 and token budget is 2k。

And this is showing the FP60 weight versus showing that this is compatible with four four bit weight。

So this is more results for efficiency comparison。Bs need nearly full KV cash to achieve lossless performance。

 and the quest can use a much smaller KV cash。

![](img/98f73413e13a6cb4d410a79dd43ab296_157.png)

So this is the average context length， which is the potential latency。



![](img/98f73413e13a6cb4d410a79dd43ab296_159.png)

Potial agency request is showing at the lowest across different benchmarks and require the lowest。



![](img/98f73413e13a6cb4d410a79dd43ab296_161.png)

Contacts loss budget compared with baselinetime methods like full attention over and bus。



![](img/98f73413e13a6cb4d410a79dd43ab296_163.png)

All right， so in summary， we talk about quest， very aware sparsity to filter out which KV page is crucial。

So there's a lot of redundancy in the KB cache so we can use the query where minor to dynamic like determine which one can be skipped。

Next， I'm going to quickly talk about beyond the transformers。

 what are the some of the un transformformer architecture that is efficient。

 starting from state space models。So in the attention， roughly， you have two tasks。

 one is to compute。

![](img/98f73413e13a6cb4d410a79dd43ab296_165.png)

The information between the tokens and then the other is the transformation within a token so the state state space model。

They can handle the sequence communication。As other author， as this multi hand attention mechanism。

So it's very similar to RNA， except that there's no linear right here。喂。😊。

So there are three matrices， one is a matrix which controls the state transition from T minus1 to HT and the B matrix basically a map the input to the hidden state on C maps is this hidden state to the output。



![](img/98f73413e13a6cb4d410a79dd43ab296_167.png)

So just using this naive state space model， you can write。

 expand this equation such that you can be presented by a convolution， it's very simple to implement。

And a new work， the memberba which introduced the selective state space model so rather than without any selectivity。

 different tokens have the same importance with selectivity it can allocate a different importance to different tokens like I want to order a hamburger hamburger is given a lot of importance and that is achieved by。

Ting the ABC and make them input dependent。 Okay， so these ABC matrices are also the function of the input X。

So that creates a problem previously， since you have no the function and ABC is constant。

 you can expand H1， H2， hH3 recursively and actually implement that in convolution， very easy。Okay。

 so linear occurrence can be implemented your global coal。However， this said activity。😊。

TheABC will change depend on the input， so it can no longer be implemented by convol。

So how do we solve this problem of slow training issues？Luckily。

 the parallel scan is one of the implementation we canll be calling borrow。

Similar to computing the prefix。Like four， four plus one is five， four plus one plus five is 10。

 four plus1 plus5 plus three 13， and so this is the prefix sum， calculate it than the prefix sum。

It's a very classic algorithm that can be implemented efficientlyly by parallel toddler using the parallel scan algorithm。

 calculate the first tool。First one， two， three and four and one， two。

 three and four in the parallel manner， so we can do that similarly for computing the hidden states。

 remember， okay compare to compute zero and one， two and three， zero， one， two and three all。

Paralyze them。Using the computing space rather than serialize and serialize the mean。

And later there are several hybrid models combining the transformer layer versus the Mba layer。

 even the my MOE layer， so by stacking them together， so you have several manba layers。

 several manba MOE layer， so some of the effort becomes mixture of experts to talk about that。

Some of them is using transformer， some of them is used an the MOE version of a transformer。

 and you can do architecture search to stack different components。Actually。

 this model can fit a single 180 gigabyte of GPU to support 26 tokens and the advantage of this member or state based model is that you have a fixed amount of KB cash rather than linear growing Kkc。

All right， with that here's a summary of today's lecture， we talk about long context。

 large language model to handle long documents， high resolution images and also long videos we talk about long Lauraura to fine tune efficiently long context models。



![](img/98f73413e13a6cb4d410a79dd43ab296_169.png)

And also introduce several benchmarks like you live in the Haystack。

We talk about streaming ourM due attention and quest to exploit the sparsity in the KD cache finally beyond the transformers。

 we briefly introduced the state's database model with constant KDC size。



![](img/98f73413e13a6cb4d410a79dd43ab296_171.png)

![](img/98f73413e13a6cb4d410a79dd43ab296_172.png)
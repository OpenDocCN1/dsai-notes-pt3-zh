# 【Hhu Dusseldorf】表征学习 ｜ Representation Learning Msc Course Ss2023 p20 P20_W12.1_蛋白质中的表示学习_第1-2部分 -BV1RPZwB6EJZ_p20-

Okay， happy to see more people coming in， today is my last lecture for the semester and we'll talk about the connection and how the advancements of representation learning and selfupervised learning translate to biological sequences。

😊，Of course， we need to focus on something， so we'll start on proteins because most of the research is happening on the protein domain so far。

So let's start from a little motivation， I sent a couple of videos over to see what is a protein and stuff like that who will not go very deep on analyzing what is a protein because what we really want to do is we take the sequences and we do some representation learning is what we do in the course。

🤧So a small overview like why do we even care about that？诶。

So this is a really nice illustration from the David Beck has like the biggest lab on making research regarding generating novel proteins that are nonexisting。

So the gray square indicates。How little do we know even from nature and all these generations of evolution？

But we still， they're still。Like enormous search space to look for new proteins and new solutions。

And。On the other side， is like some numbers from some video on YouTube that emphasizes the fact that many。

 many。On the biopharmainestry， there is a huge investment on research on designing novel drugs and accelerating drug discovery。

And。This could lead to different drugs or vaccines coming up based on research on this。

And this would be like。The idea of adopting representation learning for such a new field will massively accelerate how fast we can。

Narrow down all these basic possible solutions based on。The more theres a policy to be。

But before anything， we just need to take a small re up and focus on the attention because it will be the core part we will analyze today。

So the transformer。You should always think that。The three of。

The three dimensions we have a three dimensional ten all the time。

So we always have independent if it's a vision transformer or if it's applied in natural language or proteins。

 we always have three dimensions on input to bad size。

And we call the sequence so the number of tokens， we see what is the number of tokens for us today。

And the deep models I mentioned。And the app follows exactly the same。

So no matter how many tokens we have in the， we get one out representation for each one of those tokens。

We will ignore the fact that we had this classification and staff offs。

This will already include it in this end。So the core attention operation， the attention。

 the self attention or in general attention is defined as you can see on this。

By first applying this matrix splication between linear projections of the input。

So we have QK and V which are queries here is in black。Quries， keys and values， so these are all。

 as you can see on the top。Three inner projections of the input。

And in case of gross attention as it on the image on the right。The query， the queue。

He's another representation。And the keys and values always come from the same input。

But Q can also be something completely different， as you can already see from the map。So these。

This is the attention。MapSo for one head and one layer， this would be an L by L matrix。

So this attention map will always be an L by N matrix， which means that without any post processing。

 it already captures pairwise relationships。So we have a sequence of added tolkens。

And the internal representation of the model already gives us like a pairwise relationship between how all these elements are connected to each other。

 which justifies its quadratic complexity。Inside you of much operation。

This matter duplication and for those， just a small recall this。

This division small with this factor is to scale down instabilities that arise from this large matrix smification。

 so I have a nice illustration here。So you can imagine that us。Here we have two。

 you can imagine we have different abedding of tokens。 so as this dimension of Q。

 so this d model dimension as it grows larger and rather， this dot product。

It becomescomes extremely large。Which makes applying a soft Max on talk makes it a bit make this gradient saturate。

 we have analyzed again。Throughout the course。So this is a really nice illustration。

And this is like the attention matrix and all the individual。

So each row shows us how the different keys attend to this specific query。

 and the second thing you need to know is that，You need to be conscious about this that all these for all day to turn out to Tos with queries and keys。

It's happening in parallel， so already this message multiplication。

Comps all this pairwise relationships in one。Computation one， one of mathematical operation。

So it's already。Seeing how all the possible queries map to all the different keys。

And in the case of cross attention。Querries and keys come from different。Inputs。

So in language translation， the query is the decoding the language we want to translate our text。

And keys are the reference language， so translating from English to German and vice versa。

And in the case of Muti had attention。For one layer， if we have 10 heads。

 we have 10 of those matrices。Is that care So for a transformer of。10 layers。

And 10 heads at each layer。 How many。Attention maps can we extract for one input。

If you have a transformer， you have 10 heads。And it's 10 layers and this layer has 10 heads。

So how many of those L by end。Attention maps。We get from the whole model， can anybody guess？啱。

1 hundred0。Because each layer gives us 10 and we have 10 layers， so1 by 101 half。

Another thing that is really， really important for today's lecture is the fact that this weights。

 so these attention map， which I have it here。It's that these weights are computed on the fly or as like otherwise called literary fast weight Can anybody imagine why we call them like fast weight white？

How they are different from， okay， you can already guess from the illustration。Why。

 why I have colored。The attention with different colors， while the。Convolution and full convolution。

 full connected layers with black， like what is the difference， why we call them fast？For example。

 conclusions， the waves are shared。Yes， you can already see this is like the character。😊。

But this just makes it local， but you can also make the attention。Local。

 but they still consider fast waste。Was that I'm not share。

sequenceEx so for its individual input sequence。These you get completely different weight。

 so they are changing on the fly， so even though the QK and V， the two， the W actually。That youQ。

WK and W B。Are the weights， the linear projections， the attention weights。Science for each sequence。

 so you get a completely different image for each sequence。

 and this is not happening when you have fully connected layers or convolutions where these weights。

😊，Just are slowly changing with creative descent at its iteration， but once you train this model。

You have the exact same weight。So this is a really nice advantage of having。

That I want to emphasize today， so for its input， you have a completely different different pair wise relationships that you attend。

And。This happens。L for L for M layers and8 heads， this is like M times8s。

 so because you have not just one attention map， you have for 10 layers， we set 10 heads per layer。

 we have 100 attention maps。So you can imagine how many of this pairguwise relationship we have。

Of course， in the first， let's say layer you have。If you have like if the tokens are wordss。

 you have pairwise relationships between wars， and in the second layer you have pairwise relationships of pairs of words and so on and so on。

 and you get to build more abstract representations。

So let's take a look at what these attention maps look like in natural language specifically for language translation。

And one small detour is that this。This idea of fast weights and attending to all the elements of the sequence was already popular and quite effective from 2014。

From this team about language translation， and here you can see in this square this example of these。

Non diagonal weights， as indicated by the heat map， so the larger the weight on the attention map。

 the more white the heat map becomes。So here you see this notion of order swapping that you need to translate from one language to the other。

So this is from French to English and you see the adjective and the。

And then noun you may need to swap the order。So we're still staying natural language and we can already see it。

We will do a lot of those heat marks， so don't confuse the L byL attention matrix。

With this visualization so here。For its head on the x axis and different layers。

 we will produce a heat map that corresponds to different things。 so here we measure。呃。

The confidence。 So that the。The maximum attention that it's had at its layer。The way， yes。

 the attention that it's assigned to the next talking on the sequence or the previous one doesn't matter like a way of reference。

And then we take the mean over the whole test set， so that's why it's called mean max weight。

 attention weight， so everything since you have the soft much。

 everything is from zero to1 all the time。And you can already identify some patterns。So以 there嗯。

You can already identify that some heads even in natural language translation。

 so this is still supervised training， which we try to translate from one language to the other and we see that some heads become extremely confident and as we will see today。

Confidence is usually a very good thing in when you want to generate like。When you want to。

 when you have a vocabulary of。V elements。And you are very confident about your decision。

 this usually means。That the model has let has。诶。Materialize some sort of understanding for the domain you train on。

So there is this work from some group in 2019 where they found a lot of。

 they tried to assign different roles to different heads。Learn for neuroma translation。

And they identified。Some hazard just attend to their neighbor， so just one6。话 you from the main咁样。

Which are not really important， but the most important is one is the syntactic heads。We呃。

Tend to assign most of the ways。诶。Into the。Into different relationship between language。

So between noun and verb or verb and。Or adjective a noun， so these are called synact heads。

 but that they are empirically observed。And then there are some really。

 really rare and specialized heads。😊，And you see that this is changing， as we said。

 these are fast weights， so these weights are produced for this individual。诶。inputput sequences。

And this specialized。Or her。Talers give their attention to something that is。Really rare。

 So this word。It was really rare in terms of how frequent you can see this world and you see that already some head。

诶。Some heads focus their attention。Yeah。And in their analysis。

 they found that all these the specialized heads， so this type of heads is the one that you should look for。

 and they do the heavy lifting while there are many， many heads that don't even have like a role。

 which are more or less uniformly spreading their attention can be just pruned if you want to create like a very fast moment。

So I will just talk a little bit about our sequences， which will be proteins during this lecture。

 but this applies to all different biological sequences。

So the base unit are the four different nucleotides that can be found in our DNA or RNA。

And then by considering all of the possible triplelets。

You get only 20 of those triplets are valid combinations that can be found in humans， at least。

So by taking triple plates of nucleotide bases， we have the so called amino acids。

Whi for the purpose of this lecture would be the tokens or the elements or otherwise called the residues of the sequence you will see based on different literature。

诶。Different way to all them but in practice this would be just instead of words or parts projection in vision here we have amino acid and this is like our basic。

Unique that we will work with。嗯。And we will consider。诶。3 different levels that you can。

Work with proteins。So primary structure is when you there are some。

Ways in biology where you can do the so called sequencing。

 so you see all these amino acids one by one in the with different。Biological techniques。

With look something like this。 here。 we have two chain of。诶阿面大。诶And。

What we really want to see is how these are。Our fault。

And what is the outcome of the for which is the structures that they create。

 so they tend to create some patterns。For example， like these one。

 we can see this this is called betas and it's called alpha helices。

So this is called the secondary structureor and when you。

Which are kind of patterns of our local lives and can be identified and then you have the overall3ist which is called tertiary structure。

So during this talk， we would use the word interchangeably between amino acid token residues is a more biological。

 it just only included for completeness or elements。诶嗯。The vocabulary。

 which is natural language would be how many words you have in your data set， like 10，000 or 20。

000 wordst， it would be the 20 amino acids where the ones that you can possibly have。

And for proteins。If we have DNA or RNA data， we will have just four elements。

 which would be this A UCCZ these four elements， so we have a vocabulary of four elements here。

 we have a vocabulary of 20 elements and its also called alphabet or lexicon in the literature。

Then we will focus on。Three different things。So a very。

 very important thing about proteins is how different proteins or proteins with。

Antibodies or different other molecules interact with each other。A specific。

 a very specific part on the 3D。Stture on the protein that is responsible for connecting to proteins。

Or a protein with another molecule。And this is called the binding side。So this is the part。

The 3D part that。We really care about because if the binding site has a problem due to some mutation。

 then the overall function。Of the protein becomes useless。🤧And in general， there is a very， very。

 very strong connection in nature between the structure and the function of。

All the molecules like antibodies， proteins， it doesn't really matter， but let's stay on proteins。诶。

In general， nature highly correlates the structure， even on the human body。

 the structure of your lungs。Inestines are really correlates with the function。So。

The binding side can make a protein bind to another micro or macromolecule。

And this will cause conformal change， which means that the protein will change its sake of the 3D space。

 which will result in a different。方式。So for example。

 you can think that people try to find like molecules。

like pills or drag or boxess that bind in different ways on pro and try to see if the reaction would be the desired one。

In a more machine learning side， we will have an L by L matrix。

So there's something completely different binding size is just a part that we really want to focus on。

On the mas learningic side， the target， as we say， we have two types。Okay， three types of targets。

So in any case。It will be an L by L market。So the simplest case。Okay。

 let's say the most advanced case would be to have the exact distance in armsstrs between all the different pair。

And you can imagine that see。Since the distance is symmetric by definition， but we only need。

To have like the upper triangular or lower triangular to get this distance because this matrix。

In terms of physics， needs to besymmetricary。So here in the most ideal case。

 we would be able to predict that these stands in armsstrs。

Betweenen different pairs and this would give us the exact structure of the protein in the 3D space。

 because if you know all the distances，There is a mapping。呃，There。

With some advanced mathematics that you can go from these L by L matrix to the exact3D structure。

But since this is a bit hard to predict because here you can see that the distances can have like many。

 many values。One thing we do is that the first simpl is to go from distances to distoograms。

 so we beam from some ranges。We will see， for example， from two armsstroms。

Or two and a half a me to 20 or 30 depends on the application。呃 to。

Stay from 2 to 20 and then eats all the proteins that have like one armsngtro difference are grouped together。

So two， three， four and here。We create， we group together。

 we bind together all the proteins that have a distance between。Two and three armsstroms。

 and this converts。This very， very difficult problem where you have to predict the exact distance into a classification problem and you have as many classes as being。

So， this would kind of。We would be able to formulate like a segmentation task where you have this pixel and you have to predict all the different。

Plus。Is this clear？O。And then even an even more simplest case is to say that。Okay。

 I just want to create a binary matrix in the simplest case。

Where everything that is below a threshold， usually this threshold is between seven and eight angstroms is considered to be a contact。

 so we consider that two mo2 amino acids are in contact if their distance is lower than eight angstroms and no contact if they are more than eight angstroms apart from the 3D space and then you can get binary held by yield market。

So， this would be。The are three possible targets， let's say， as a machine learning problem。

 we will always have a sequence and we have these three possible targets independent。

How much you want to。To cut how much you want to。Find like how much can we possibly predict how much fatalelity we can have on the predicted distances？

And this substitution matrix will see something you can get from bioinformatics based on different analytical methods you can get like an L by L matrix for different proteins。

 and we will see the connection between the attention maps。So now we go back to the transformers。

 so we have the transformers， we have the input amino acids， and we want to see what's happening。

During pre training。So now we ignore all the。Targets。

 so these contact maps and distant maps that are。Much， much more costly to。瓜ir。

And we stay just on the sequence alone， we consider that we only have the sequence available。

What are the two possible approaches we have seen in the course？For doing。

Self supervised pre traininging， so we have seen the bird approach and the a bit。In smaller depth。

 we have seen this GT geneerrative pretraining approach。And one one over the other。

So let's say we have six。Input amino acids。And we have a transformer。And in the end。

 we get six output representations for those amino acids。So in the case of。嗯。Let' says begin。

Its generallyerative training。We provide all the sequence and the as the input。But the transformer。

Has the so called mask attention。Does anybody remember what is this mask attention doing actually？

Yes。😊，Yes， so here if you're in position I。And you have the output eye。It can only see。One side。

 as we say， like only the previous tokens， if we consider these directions。诶。This are talking。

Will be the result of only the previous ones。And。Similarly。

 this talking will only be the outcome of those ones。Is it clear？

In the case of so this is with mass attention。诶。In the case of bear。I0。

We have the so called transformer encoder and we don't have any masking inside the attention model。

 but instead we mask the input sequence。So usually 15% in natural language and as you will say。

 as well in proteins。We must。50% of the sequence。And then we take the outcome presentation。呃。

That sees all the sides， so right and left side， that's what these be。T for。In the parallel。

 this be transport bi directionional， which means that this token can attend to all the tokens on the right and left side。

While here， these tokens can only attend to the tokens。The tokens that exist on the right side。

And so far， the biggest models in natural language adopt this paradigm。While in biology， so far。

 things may change。But this is the dominant type of pretraining。And here you predict。

The value with cross enpiage， it's like classification task in the end。And we have。

As many classes as the vocabulary is so 20， I mean acids 20， the vocabulary is 20。Any questions？Yes。

先。As in language for。ますけ。Was it just possible。I think in here we just must。But。There are different。

Bt like approaches。But I haven't seen this idea where you can provide like random stuff。

I think you just around must 15%。Any other questions regarding these two types and why we？Okay。

 I haven't explained why。But。First the。This is the dominant type in。

In biological sequences and crawling specifically。And。

We don't want to lose by excluding some parts if we have like this biological sequence of amino acids。

Because we have no idea。Eximentally。校诶。What is the most important。I in acid to predict。

The this specific one， we don't know if。Looking backwards is a good approach so far， at least。

 so we want to include all the possibilities。Inputs because the interaction between amino acids is highly nonlinear and highly global。

So even for the binding side which I said that is like a very specific region on the 3D space。

 even if you mutate， so if you change somehow either with different perturbs。

 some parts that are completely relevant on the sequence that could even correspond to let's say the other side。

 like the anti symmetrical side of the 3D structure of the proate。

 it can even affect the binding side， so they are very， very highly global interaction。All right。

 so we have a so called protein language models who use PLms in。

Where do you have this bird like pretraining？And we will focus on that during the lecture。

 so we only have an encoder， normal attention， then cross central pillows。So ideally。

 given that we have enough data。The model would be able to understand the interactions and the underlying principle based on evolution that led to this type of sequence to occur naturally。

And another thing is that proteins do not need any。Input adjustment。Like vision， for example。

 in vision， we say that we take these non overlapping taxes。

 but this is not the case during biological sequences。

Because proteins can be naturally represented as sequences， we don't have to dev about tricks。

And specifically sets because we set transformers。Process the input sequence as sets。

Wwhich is something that happens naturally in proteins。

 in contrast to even natural language where there' is a stronger notion of order and even on vision where you have to or audio where you need to define as some patch and then project them。

So the fundamental question is。Just by relying on the sequencing。So all these plenty different。

アの acid。What and then doing this bird like pretraining， how much can you learn。

 what are the representations that one is able to learn and capture？

So this is the first large scalet be like pret model， which is called ESM。诶。Primarily from。

Facebook AI， I think， the trend model。And they find these properties similar to what we saw in the last lecture。

 how Dino creates this clusters throughout training。

 even though it's not trained with any type of label。

Here you can see some properties of different amino acids and how they are clustered in a low dimensional projection based on their weight and their tile。

诶。So you can already see some。Connection here， you can see negative rechar。

 positivechar is height of。Hydrophobic， aromatic and so on。

So these clusters even emerge only from the sequence alone， and this is applied。

 I don't know if you remember， only in the output。So you only usually take one of the tokens。

 this classification token， which is like one of the tokens。You make this projection。So端末 data。Okay。

 we have only sequences。诶 in诶。咪要。Bio deep learning， we don't only care about the proteins。

Because we have 250 million proteins， which is。You probably think that it's a lot。

 but compared to rational language， they are very few， not very few， but an order of magnitude。

Smaller， at least。But we also care because proteins have a really varying length。

So we really care about how many tokens we have， so we have 86 billion amino acids on those sequences。

And。It's really a big practical consideration and limitation how to process。Effectively。

 sequences that have such a wide range of lengths， so a protein can have maybe a length of 50 amino acids。

 but even go to 2000。So you can imagine that padding zero padding a sequence。

From 20 or 30 elements to 2，000 elements is not the optimal way to dealing with those data。

We talk about days the end。But in any case， we see even from the first large scale model that some really desirable properties emerge。

 so the model is able to capture based on the representation of some biological properties that are what we care about and generalize across a wide range of daing tasks。

I will not cover it because it gets two application specific。

And already we will see the it codes and codes information。

Without ever being trained with any type of supervision or secondary structure or tertiary structure。

 it it already captures some of those。Underly information。

Here's another visualization again from the output of the transformer。So， you can already。

City between an untrained a train transformer， how much？诶。The different。thinkHereYeah。

 we have different days。诶。And different colors are called to similar groups called orthopo。

Or fellow groups。And I've highlighted some。Cllasts that you can already identify from a two dimensional projection。

And。And it's always desirable to see like tight clusters so ideally。You would see。

Like an idea behavior， if you have like。1 classes would have to be like you have like tight clusters and very distant from each other。

Have we done TSE visualization on these largely clicked models on the previous exercise。

 if you take a click and you do this type of TSE visualization， you will see almost a textbook。

Exponential textbook。Behavior of anideS me。Behavior if you take for psychopher10。

So this would be the ideal behavior， all the Z groups would be grouped together and very far from each other with clear boundaries。

And。But you can already see some properties related to themer。

So to encode the secondary structure without going two months into details。

 they just add a linear layer on top based on the existing representation。

 so it's like a frozen like no gradients are passed through the。The bad model。And。

Why do you have an idea why they just want to see only with a linear layer how much of the secondary structure is encoded compared to what we do in vision？

Do you remember how we evaluate the pretrainings division vision？We have some pre training。

 and then we want to evaluate these representations。Yes， we can do your name or we can do。Okay。

 so this corresponds to some sort of linear probing。

Do you remember why we favor Ken nearest neighbors or linear probing over fine the whole network？

If we want to compare between different pretrainings and architecture。あ対。Was it's done the fifth。

If we are trying like different representations with different models， we try to。

Measure the differences between the representations。ベト。Yes。

 so it's a more fair compile because we keep the different representations fixed。

So all the linear projection can only see， let's say。

 can only score as well as the existing representation。

It cannot create a more abstract or more complex representation。

And you can already see some linear behavior between the free training laws。

croros C cross entropy remember where is e letter from and this is the secondary structure prediction。

 I think these are eight beams， but they classified what we said about distances they just classified between eight different beams。

But you can already see。But the better the model gets on。The pre training tasks。 so this bird。

Like pretraining is crossenttropy， it automatically gets better。

And I think the different colorss represent different models。So， then。I think one or two years ago。

They scaled up this bird re traininging。Again， no particular change on the transformer。

 no particular change on the data， just playing a bit with some hyperparameters and training strategies and training schedules。

And they would be able to scale protein language models to 15 billion parameters。

And they see that even more desired properties emerge。So here we have these add by end metrics。

But this time， it's not symmetric matrix。The lower right side is the ground truth。

So these heat maps of blues indicate the contact。So what binds to what， so its position I'd say。

 indicates that these two residues or amino acids are connected。And the upper left side。

Sos the predictions of the model without any supervision， just by taking the average。

Just by taking the average over the attention maps。

So we just compute all the attention maps for this sequence and then take the average and we can already see this。

This is the information regarding the contact map to be already readily available for the model without any。

Task specific fine you on this task。So this is really surprising and that's why many people have switcheds and focused their research on biology and proteins and RNAs and all this。

Theta， of course， as we have discussed， and you should always think in terms of representation learning。

 you should always think about the scheme。So we have these。Huge data sets。

 but we also need a lot of compute and bigger models。

And they also validate that of keeping the data speak， they played with different。

Number of parameters as indicated for the heat map。And this is the evaluation for contact prediction。

This is another。We don't care so much about。So you can see that the more the parameter。

The more the triangle parameters with the model， the better it gets。

 given that the data and the computer fixed。So in large case。

 you get the desired properties of learning underlying information regarding secondary tertiary structure。

And in this newest model of 15 billion parameters。They also saw over to another。

Type of model which will hold up next week， that's called alcohol。

That we don't need additional external information。

 we just take the sequencing as it comes from the reading the data。

 we don't need to find similar sequences on the database。That you will see in the next lecture。And。

They after they train the model， they use it for inference to。

Existing protein sequences that they have been collected from nature， but we don't really know。

To which organs they belong to， this is what they call natural metagenomic protein map。So they。

They took like a huge database of。617 million sequences。

 this just data that were sequenced that we had no idea about their structure。

And they perform in for us。🤧And。As you can recall from natural language， we care。Not just about。

Predicing the three with some module on of the language model that we would not cover。

But we don't care about just the model predicting something because this is sort of a generative task。

 but we care about its confidence from predicting something。

So if you ever work with big protein language model or big natural language model。

 or in general generative models， to perform this type of inference that generate all the tokens one by one。

This is called Port Regressive where you take the output of your prediction and then。诶。

So in this scenario， you would only provide the first one。

 then you get a prediction and then you feed two ones。

 this is the so called auto aggressivegress inferential prediction。

So when we want to evaluate language models or protein language models equivalently。

 we care about their confidence and there is a metric for that if you want to look on the literature。

 it's called perplexity。Which basically quantifies the confidence of the model and penalizes the model that provides。

For some tokens， low scores a model。That would output a trained model that would output the uniform distribution would have a very high。

pererplexsity so it would be pen alive， while a good model will have very high confidence and ideally it will have like a complexity one。

And you see that。
# 【麻省理工】高效机器学习 MIT 6.5940 EfficientML 2024 年秋季 p16 P16 Lecture 9 - Knowledge Distillation -BV1o7jzzwEST_p16-

All right， good afternoon everyone let's get it started。

 so today we are going to talk about efficient amount of AIlect9 knowledge distillation。

 so this is a new。😊，After we have talked about pruning， quantitization， neuroarch research。

s another technique about knowledge distation。So make sure you have done finished homework one and already working on back two and just a reminder。

 So today we will learn about knowledge dissillation， which is a thoughtful technique。当人。刚才这审。

We'll talk about what is knowledge dist， what is teacher model， what is a student model。

 and also how do you match the logistics， or the weights for the activations or the gradients。

 whatever， how to match teacher and student。We also talk about self but online deation and also dis for different tasks。

And finally， we' going to talk about another technique， natural augmentation。O。けのさげ。

So what's the limitation motivation here？Again， we have limited other resources across different platforms in the cloud。

 GPUs are super expensive and the memory capacity is also limited 8 gigte 100 gig up 120。可，被告办你再是吧。

Not to mention the mobile devices are microcontrolls who have。

A couple hundred0 kilobytes of memory versus tos of giggabytes of memory。

So compare with the neural network GPUs， we can run ResNe， we can run VIT， tiny ML。

 we can run Mnet movement every too tiny。So the question is how do we train？很你忙。

That can fit very little memory budget。我依为。Or even match the accuracy of those modules。

So that's what Kenya now， and even for the cloud use case， even for the cloud AI， these days。

 large language models are getting super big， super big。And we want to reduce the serving cost。

 therefore even on the cloud， knowledge disitation makes a lot of sense when can we dis steal a 70 billion parameter model to a 7 billion printer。

So we can save tonight the memory traffic for weeks。So that's the question we want to answer。

 have we use a larger model to guide a smaller model， so we have a larger model。

 a teacher model on the left， we have a smaller model， student model on the right。

Now even training these models。求。Different accuracy。82% versus only 52%， right？How the question is。

 can we help the training of tiny models with the help of these larger models？

So this image is the illustration of。Knledge de。First of all， we share the same input。

 the same input is fat。To both larger teacher network。And student I。

The teacher network usually is usually larger like Lama to 70 B。

And the student model is really smaller。Not my tool of like 70。

And then given the input they both produced some prediction targets。1 logic two。

Well we are trained in the student networks。We usually have some locks， either classification loss。

 maybe this is the most popular。So what is new here？You also add a new loss called distillation loss。

Distination log between teachers lodgings and student logings。

So what we are trying to do here is trying to match the logics of the teacher and the student。

ItTime to match that he carried with。That still。So that's a new loss term we added here。

AndWhat's the intuition added this loss？So if you look deeper into the prediction。

 given the same input image， say a cat。The teacher来。The two logics， one were the class cat。

One for the truck stock。The cat is $5 white， meaning back。It is a cat。Strong ideas is is a impact。

And if we normalize them you after soft Max， the probability is 98%。Versus 1。7%。

Okay so the teacher model is strongly。Versus the student network。The logic is three and two。

If you do the softline， the probability is 73%。Versus 26%， okay the classification is still correct。

 so we don't have any loss。Coming from the cross entropy， cross entropy box。

 entropy box is zero because the prediction is correct。It's a cat。

But you can tell their output from the teacher versus the exhibit， they are also quite different。的确人。

啊，所以说。 so you have a higher probability whereas the student model is lesser 27%。パ速ィ。Okay。

 so here we are trying to match。啊。Prediction probabilities between the teacher。

That's the missing part from the cross central here。

So how did we derive this probability so that is through the softm function。

That's a review of the softm。Explement。Deived by the4 five。ISPS one。

Andm assuming they can calculate added。Versus the student model is less confident。

So our goal is to bump up the probability for the cat。

And bo down the probability for the dog to match that of the teacher。So how do we know that。

 but first， learn this concept temperature？Hemperature。So we was ultimate。If the temperature is one。

 that's our original case， if the temperature is larger， then the output distribution。

 the probability gets smoother。Rather than 98， 1。7， this is 60%， this is  40。1%。

So a larger temperature will smooth the output probability distribution。So mathematically。

 where does the t temperature T appear to appear in the denominator of the solve max？For example。

 we apply 100 of 10 previously the XP5， now it becomes the XP5 divided by 10。

 similarly here on the denominatorator is divided by 10。

So this is the formal definition of knowledge disation。

so neural networks typically use software Mac function to generate the logics。

two class probabilities， which is。For different class with a different temperature。

 the probability is EXP Z。For a particular index divided by the sum of the EXP。

And IHA ranges from  zero to a c minus y where you have C classes。

And P is the temperature which is usually set to one。

And the goal of knowledge dissation is to align the class probability distribution between the teacher and the student network。

So we are trying and slow online。This probability distribution。So what can we allow， Okay。

 What to match。What tensors can we match？So here we summarize a bunch of ideas where we can match。

Primarily the summary。We get， so let's go through them one by one， starting from the upperlogs。

Okay so we have seen this figure， not only do we have the classification logs。

 but also we try to match the loes。Between the teacher model and the student model。

Trying to match the output logics， cats and dog as the output prediction。Okay。

 so how do we match them， can either use cross entropy laws？Two distributions， one for the teacher。

 P T， one for the student， P S。We can also do the simple L2 loss。PS把P minusps。

So it's very simple just to match the output logices。What else can we match？Not only the output。

 we can also try to match the intermediate sensors。

 including the intermediate weights and also the intermediate features。Okay， so let's look at them。万。

Here we no longer have output， matching output now we are matching the intermediate tensors。

So future model layer2， this is the student models。So here we try to match the intermediate weights。

These tomatoes who try to match the weight。What is the challenge here matching the weight of the student versus the teacher？

Remember the。No人。Yes， you， so difficult is。The teacher model and student model。

 their weight dimension is different。Teacher model is really larger。

 the way cancersor has larger dimension。Student model already a smaller dimension。

So what we can do here， just like you proposed， we can do a low rack approximation right and here we also we can also do a learner projection。

就是我把王康路山 here。Com嘛。Stent smaller a to a teacher's larger app。So this is a future network。

 which is larger， wider。Still have model wishes now。Smaller。

And we try to match them by using this projection matrix。

 this blue matrix project from a smallerer channel to a larger channel。

I learned this projection matrix。And then we can match the output of an after production matrix with the teacher model。

So between the teacher wait and the student weights。Plus， a。Transformation matrix。

So here the blue part is the transformation matrix。Which is just a simple F layer to align the shape。

 the dimension。The teacher was to' do this things。OK呃。

There are also other methods like you can use low rack to match， and we are going to skip back here。

We can also match the intermediate features， not only the weights， but also the features。

 the activations。So previously we were matching the weight， now we are matching these activations。

To match to mean the future maps between the teacher novel and the student model。

The intuition is that they teacher and student network should have similar feature distribution。

 not just the very end。这是。Extreme case， not just Mer end。

 not just the output probability distribution， but also across all the layer， different places。

printer back。So we talk about weight matching， activation， matching， what is left。不点来。

So we can also try to match the gradient from a teacher and the student。That's crystal end。

The idea of different dimension。RightSo not even mention the teacher as student gradient。work？

So beyond the weight gradient， there's also the activation gradient。Jun back propagation。

The back propagation part is usually two act slower than the forward part because。

I is doubleubling the computation， one is computing the weight gradient。

 the other is computing the activation gradient。If weight gradienting it's hard to match and match。

The activation gradients。In particular， the activation gradient for the very first layer for the input。

Since teacher and student， they are sharing the same input。So this is intermediateent attention。

Nice intermediate attention back the backs propagate。The gradient all the way to the input。

 to the input image。So this is an input image。And this is the gradient when we are back propagating the gradient from output all the way to the input。

This is the gradient on the input tensor。So intention of a C deter map is defined as partial loss or partial acts。

 challenge the learning objective。And what does it mean for the airport feature map。

 So if the gradient is large。Here in the nose in the eyes in the face ofs fox。

It means that just a small perturbation or in this area。We will significantly。

 impact the final output。Meaning that this area is very important， very crucial。

For us to make a decision what it is。Indeed， it makes sense。At position IJ。

 the pension over there is defined as the gradient with respect to。That pixel。

Have people we are trying to match。す。As mad from the teacher versus。The students。

They can be easily matched because the de is the same。

The gradient dimensioning is the same as the image。

And both the teacher and student are sharing the same image so we can match them。And I see。

 given different networks。What does the gradient look like？So this is the second row is red at 34。

 30 row is red at well1， they are all the same family。Versus the first role is networking network。

 that's a different family。We can see that networks of a similar family。

 my third row and the second row。They are grs。very身份了。Well， compared with the first role。

 the gradient the is a lot。第二。These two give lot， well， these two are very similar。

So attention attention map of。Performance image and models both above 70% are indeed similar。

Le performance model this one is only 62% has quite different feature map。Therefore。

 when we are just doing the dissillation， we try to match those intermediate feature maps on EL over theX。

 trying to match the gradient with respect to the activation。Okay， any question so far。

We talk about matching the weight， matching the feature， matching the gradient。

 also matching the output。We can also match。The sparsity频开。So好 match sponsor的开。First of all。

 where does frostity come from？So usually we have a rental activation function。

 if we have rental activation function， then theres starts to be。

So we want to match the ferize after the red activation function。

Viurural is activated if it is larger than zero。It is not activated。It becomes zero。

 if it's smaller than zero， it becomes zero。So I have de that with a latch。

The teachers sparsity pathogen them versus the students sparsitypath them。We can also match。

The relation relational information， and what does that mean？Previously。

 we have been looking at each tensor。It's all potential be。规ning探 the way ten你赛。

Now we want to look at two tensors， not just one tensor。

 not just one match one tensor or two tensors。For example， this is a teacher， this is a student。

The teacher has 32 layers。The student has 14 layers。They both have three stages。

 the teacher has more residual modules per stage。Five in the preferred stage versus the student has only tool。

In the first edge。Feature has five in the second stage， studentst have only tool in the second stage。

In each stage of。The same resolution。The different stage will be the down sample by two compared with the previous stage。

So what we are doing here is that。Although they have different number of modules five versus two。

 they also have different number of channels。The teacher model may have。

Bger channel like1 he here we have smaller channel like5。512。

But the relationship between the input of this module and output of this module。

It's only dependent on the number of ten。So for example， here。We can just calculate the。

The relation between the inputs and output breaches of dimension C in times C out since we did a reduction on the spatial dimension for both the teacher and student networks。

So we can have a seeing timescale tenor here for the teacher and that of the same ten for the teacher and also for the student we are trying to match the relationship。

Between the input and output for the teacher and input output for a student given given a stage。

We can also match the relationship， not only for the different。Psers。

 but also for different wrinkles。For samples， and here we have three samples for the purpose。

Bert one， Ver two， work three，Previous， we just tried to match the distance between the teacher of B one teacher。

Of Bt wine versus the student of Btwa。Where as a teacher of her tool。if I understood effort。

So they are independent， these paperspers are independent。And now we try to match them jointly。

A1 T2 T3 from the teacher versus S1， S S3 from the student。

Have a similar relationship between each other。Here T2 is on the right of T1 as so be on the right of s1 versus in this loss。

It doesn't care whether as who is here or within a circle330 degrees， it doesn't matter。

But here it matters。The relationship matters。Comventional KD focuses on matching the features or matching the logics on just one input。

The relational Kd looks at the relation between intermediate features across Monco。

We tried an image monous。哦。For your homework， for your open ended projects。

 feel free to try this on large of language models， whether it makes sense。

To try this relation knowledge dis across multiple inputs。

 when you are compressrising my large language model or visual language model。

 maybe this method can shared some light。So this is putting it in math， so we have multiple samples。

 we calculate the out distance。Between those something。以上であります。First example， second sample。

 first sample， third sample， first sample， fifth sample。So altogether， how many terms are there？

We have n times n minus1 divided by2 since it's pair wise。

Represent when this pairwise distance of future of vectorctors。转到了。

There is is individual knowledge and dis。We just care the distance between T1 and S1 for teacher。

 as a student， T2 and S2， EA and SN。Now we not only care their them independently。

 but we care the relationship between among them。So we have to calculate given。Thanks sir everyone。

Go back to visit。The distance with all the previous input samples。 So that's the difference between。

The relation within the mono color et it。Calculated assembly for each input versus calculating the relation across different input sampless。

Okay， so that's all for the second part， what to match。Match the gradient， match the weight。

 match the activation， match the logics， match across different input samples。So for that part。

 we have one teacher and one student。require two models。What's the problem for that？

Bespec when the scale is larger。You have to first train a very big model， very giant model。

 you' have to first have a teacher before you can have a student。A training this teacher。

Could be very expensive。Like2ma， 70 billion prime anma is pretty cost。

Then if we don't have the teacher。How do we apply knowledge dis to begin？

So that what we try to answer in the third part of the lecture。Self。And online installation。

Just like self learning。We don't have a teacher。You just learn by yourself or learn together with your classmates。

And for the previous installation， we have to train it once and first have finish the whole training process get a high performance。

High performance teacher model。And then start to start。Dation process for the student model。

 but now we just want to do it only once。Just with only once。Online isolation。

You distill while you learn。哎そがす。opening the motivation for the third part itself。

 and online distribution。And I see how that works。Starting with。Self destination。

So teacher model that we mentioned is usually larger than the student model and that is fixed。

We have a large fixed teacher model and a small student model。

The fifth one page of a fixed large teacher model。あ。

Had some pieces advantage since we have to training it， which is very expensive。train。

And does it have to be the case we have a fixed large model in KD？Actually， not necessarily。

It can be of the same size， doesn't have to be a fixed size， fixed， large size。

So this project called board again， network。And it is decor training stage。

Using both the classification objective and also the disstillation objective。

So what is interesting here is that the teacher student model science。

 the architecture is exactly the same。C market。Same model size， not bigger teachers。

 small student the same size。So what about。First， train70 using only the classificationification across en。

I a second step。We use the presententroppy laws to treat the student。also， try to match。

The logics from the teacher from the previous staff versus the student from the next。

And on and so on， each time each staff。We match， we try to train into it cross entity laws。

The decision logs with the previous staff。We use the previous site。

Here as a teacher to guide the next step。And as a result， the student I1， S2， S， S1。

 S SK is getting better and better。When the training finishes in the last step。

Seeings these architectures。好的生月。On some the prediction。Together。

We can assemble this output together， together a final output。To example。

 this output to get in better performance。So that's the interesting part where a teacher and student they are of the same size。

We can also do online dis。He online dis is saying that。We have two networks。It can be the same法。

Not necessarily teacher is larger than a student。感じでせ。And they are traineded from scratch。

Rather than we first trained the teacher model， after that trained， we do the decision。

Now we don't have a teacher， we don't have a， everybody is just starting from scratch。

Just like in the classroom， only you and your neighbor， your classmate。Can you sit together。

Nt one is a teacher of network2 when we are training network2。

 andN two is a teacher of network one so we are training network one。

So they are acting as the teacher of each other。Which is the interest part。

So just like you have two models， they are often very exactly the same size。What you do here is add。

The laws， not only the cross entry laws。Student， T or teacher。You have to cross central laws。

Why is the ground truth label？And then you have the KL divergence。The KD laws， knowledge disill laws。

呃，吹。Second a model as a teacher， first model as a student。When you're training a teacher。

 you not only have these cross entrytropy laws， but we use the student model as a teacher。

And the teacher model is a student， so learning from each other。

So the interesting part is that it's not necessary to portray this teacher and the student。Okay。

 his teacher。The teacher can be initialized twin from scratch together with the student。

And student can be the same size as a teacher， you not necessarily need to have a larger teacher。

Whi is interesting class。So here when we are training。P oneP two也个提制，我要出点P twoPY也个机制。

The people calling人。没有说门。We can see here on Cypha 10， Cypha 100 data set。

 the deep neutral learning can improve both the student and the teacher modules。 Okay。

 so the BML in the middle row is showing。The performance。啊 should there's always。Compar with。

Deent of training。And we can also have a combined approach。Comed approach。

To combine the online installationill and also combine the self installationill。So here。

 the title is be your only Teacher。We don't have a separate teacher。

We don't have to train a teacher from scratch。Finish， have a proion teacher model to guide。

The student model， we can from scratch。Po deserv。So we， we are using the deeper layers output。

As this teacher。To distseill the information for shallow layers。

So the teacher and the student no longer comes from two different models， one large model。

 one small model。But they're coming from the same model at different places。

Those deeper layers output'll put will be the teacher for the shallow layer。

So that's the beauty of this product。You don't have to maintain two copies of the weight。

You just have one copy of the waste。Otherwise， you'll have to double the GPPU memory。

 which is expensive。You老用的 have one copy辩。And the teacher is very simple。 They just deeper layer。

deeperer to supervise those shallow reors。And the intuition is that the labels at a later stage are more reliable。

The author use them to supervise the predictions for the previous stages。No teacher。 You。

 you is your own teacher。But just the shallow layer using the deeper layer to supervise the shallower。

And let's see how that works。So the first rule is a baseline。属。

Use the predictions from the intermediate classifiers。Sometimes actually I performform the baseline。

Which is quite interesting。And this efficiency can be improved。

Because we don't have to wait until we've posted the last stage， or maybe we can exit early。

When the company isn't high enough。Okay， so that's all for the first three part。

Well take a break before we talk about dissillation for different tasks and talk about natural augmentation。

All right， welcome back， so let's continue to talk about knowledge dist。

 now we want to apply knowledge dist to different tasks to solve real world problems。

So let's start with object detection。So what is object detection。

 try to find the bonding box for different objects， you not only want to give the class what it is。

 but also tell me is where is the object given the bonding box。For the location。

So we can see the presentation headline is more complicated here， but still include the basic。

Components， including the matching， trying to match the feature， trying to match the feature map。

Here we can use a one by one convolution to match the shape， just like we discussed before。

 the teacher model versus the student model they may have different dimensions。

 so we use this one by one convolution to match the dimension so that we may subtract the tensor of the same sizes。

What is still here。 We use awaited awaited。P log P here to differentiate the background versus the foreground right。

 So the cross entropy laws previously we have is just a P teacher lot P student。 Okay。

 what is new here， we added。Cl condition here to have different weight for the foreground and for the background。

 for the background， we can allow some difference for the foreground。

 we really want it to be accurate。the background can allow some certain amount of mismatch。

That's why we have a weight here to differentiate the foreground versus the background classes。

The next part， we also want to predict a bond box okay is' not just the class， but it's a location。

X1 by one， x2 by2， and then those colors。我方情况。So what's new here you can see is if branch。

So why is the world truth， Rs is the prediction from the student。

I tryry to minimize this difference between the student versus the ground truth。Versus here， if the。

 the error from the student is smart than the teacher， then we apply this loss。Otherwise。

 if the teacher is not as good as the student， it doesn't make sense to be a teacher， right。

 So at that time， we assume。It nation allows to be0。So this is very interesting。

 We add an M term which is a buffer， okay， so make sure the student。

 the loss from the student error from the student is larger than the teacher。

 The teacher is having a smaller error compared with。The student was in threshold as a teacher。

Otherwise we just。Put the loss， the disstillation loss to be zero。

Make sure the quality of the student。It's within a threshold of the teacher。

So there is another way to guide the boundunty box prediction it used to be a regression problem because the Xy location for the object is continuous。

 we can also convert it into a classification problem。

Let's brainstorm how do we convert that into a classification problem？We can chunk。

The Y axis and X axis into several bins。So here are have six things on the y dimension， I 3 equal56。

We can also chunk divide the x axis。To six pins， so now we have 36。OurBs。And if predicted。

Predicted X y location and fall into the correct bin then that's the correct prediction okay so that's converting the continuous value into a discrete value once it's a discrete value。

 we can use the cross Etropy loss to cast it into a classification problem like here we have。

36 classes right， for x we have six classes， one， two， three， four five， six。

And here the ground truth will be the second class。And so that we can use。

The same cross entropy loss。啊 to。Supervis。This detection problem for these grid locations。

 now we try to match。The distribution。Of the past。So the class is basically the location。

 location beam， right， the location beam。Y says it is B1 in2，3，4，5，6 is a classification problem。

How about sematic segmentation。 So segmentation is a new task。 We try to find。

To give a label for each pixel， pixel wise prediction， pixel wise prediction。Again。

 we can have the same feature limitation mutation similar to classification and detection。

What is new here， we at a discriminatory network。To provide them with a Sarah of the loss。

The student is trained to fuel the discriminator network。

So we have a real inviting from the teacher teacher model give a real inviting the student that gave a。

The fact代。And here we try to fool the discriminator cannot distinguish between the real em versus the thick em。

And we can also try to encourage both the teacher and the student。

 the student to grow to be as accurate as the teacher such that the discriminator cannot tell this。

F that this is from the student， they are thinking these two are as good as each other and they cannot distinguish them from each other。

 then the output given by the student should be very close to the teacher。

So that's the adudversarial loss。As the dis。We can also use these distillation loss to compress gun models and use knowledge dissillation for gun model in this work we did a couple of years ago。

 four years ago， actually， called gun compression。So we have two models here。

 we have the teacher model here。Student model first， we can of apply to these division models。

These each for me a future relaxed。You can see the teacher have larger number of channels。

 the student have smaller amount of channels here we use a led by one con to match the channel dimension。

Com match太 dimension。We have this。Reconstruction mo， reconstruction mos。

 make sure you do the peaks wise if you get the peak wise。Ber the pictureized difference was。

truth is one truth。And finally， the third term。不干了师。Cful condition， condition干 laws。

We want to make sure the teacher and the student are close enough so that I can fool the discriminator telling that these two are basically both them are real。

And the training alternative。We add these three laws terms all to supervise them。

So that a small student model can perform as good as the large teacher model。

So here we have a panel after compression using gun compression。On the top is the original cyclegan。

 which turns a horse。做zebra啊哎。Unfortunately， it runs very slowly。We deployedt Senaviia， GPU。

 a very small mobile GPU。啊系你就先。slow。Fs。He's taking a 56 Giops only running at 12 frames per second。

 FD is 615。But also got compression。Fs reduced to only 3。5 gigs。

S times lower flos and the frames per second increased to 40。And FID also increased 253。

I I had decrease。Originally。情话。Here is another demo， interactive demo edges to shoes。

 you just draw these edges。And then we want to convert it into shoes。 now we want to。

He erase the logo， which was try to change from Adas to a Mac shoe and see how that works Origin it was pretty slower。

This is running on， he was smaller dress model。这是哪个。Previous's running only 1。6。Fends per second。

And you can see the Juliallion is very difficult。Because it's not interactive。

 it runs too slowly on this edge device。Since the print reading is so low。

 it can only sparsely sample a few。Sles。Fraday looks like a Mac shoe。我 are我的 we。

Apply gun compression。R a smaller model。But your race becomes much smoothr。

Pen is dental prevention or have at basement。不知。Now we can run in 3。9 difference per second。ますね。

Same hardware。The speed up is about 2。5 x， which is quite good。

Everything deploy mobilepoium is just a nano GPU， so you have a bunch of them if you're interested in this project。

 feel free to talk to us。L knew a few attached to mobile GPPUs。O。So we talk about vision tasks。

 dissation for image detection， image segmentation for image generation， let's now talk about KB。

 knowledge deedation for natural language。So in natural language we be covered by later。

 the attention is a very important building well。效个。

Projection for the P attention and the output projection， feet forward。How of later later norms。

So what we can try to match is not only the feature math。only future man， but also the attention man。

Which is a hold square。So this is the trollum matching the pension map， what does it look like。

Ass a teacher。The first rule， the attention map is always square， it's just open n by N。

那么 token times那么 token。This is the students with attention transfer versus without attention。

What a pension transferative pension？I seen the nervous as a do。These were very similar。What you。

And so in addition to feature imitation。The transformer architecture give us another opportunity to travel match the attention match。

knowledgenowledge dis for large language model and also visual language models so Ky and dis can work together showing this work。

It to obtain much smaller lock。So here is the cost of train a model measuring trading tokens。

AndFor3 A here they use53。There J 7 media 2。5 tokens。

And here we can reduce the number of total mat training buildings by。While maintaining the accuracy。

CompPaired。From scratch to the from3 AB。下个。The fold time is cheaper。Not9%， better accuracy on MLU。S。

And here is how the whole process works。So it contains on the outlineline side， it contains a。

Ptriing data mix versus thephatic data mix。T以 both。系。Ptriium model versus an instructor model。

 and this is instructor cu， which is the without instruction cu in using the logic coming from Lama 38D。

Also number3，7。You do a model with is。啊，完毕。And one be model。At the least。In tuning data comes from。

You have a synthetic generate some prompt and passes through with Lama3 and 400 B tract。

So to get some synthetic data。Cancate that with some collective fine data altogether and explain this piece。

Okay so that's the overall pipeline and how do we select the student model。

 we select actually this work select the student model using the pruning technique。

We talked about previously using the。To rank those important title。公司。

The work where Min Chong applied knowledge decision， retreating after proving the model。

 okay the student model is a approved version of the teacher model。So initial， we have a traintrain。

Mulatorators。And then miniron basically going to estimate the importance of embedding34， high34。

So and then its go to random them according to the importance。

AndCing away those like important panel， focus。反正你 feel it。Use this as a student。

The original LOM has a teacher to be st though。And here it a batch of a of different tens。Bgging。

 MLP， et cetera。A decision not only matches oppologs。

 but also is trying to match those intermediate features。Okay。

 so we talk about theses with different tasks for both region tasks。Also， pay pass。And finally。

 Is talk about natural augmentation。Another piece of work related or thought。

So we try to improve the accuracy， the quality of a small model that the。centralral topic of lecture。

 How do we improve the accuracy of small model。Data augmentation is very widely used in training to avoid over。

For example， we have a limited amount of data。We want to augment it such that we can。

 as if we have a larger amount of data。Somema amount of data versus is larger amount。

The typical way of doing data augmentation for vision tasks， including cut off is not for cut。

Part of the image。And human can still tell this is a dog。And also we can mix up。

た opinion he mentioned。A cat and a do， a cat given a label 10， the first one is cat and second do。

The cat has labeled 10， dog has label 01， we can mix them up half and half。So peak wise at the model。

The logic would be 0。5 and 0。5。Originally we have only two images， now we have a third image。

 so that's mix up。Also there's a work called alldo where。Two things。And we continue to。

Even Congressors， we have a lot of different policies， both spatially and those in Congress。不要是考虑。

We can also use。Also， I now to automatically find the best automation policy。

Apart from data augmentation， another way to provide overview。Using drop out。 So during training。

 we randomly select a few。牛s。F with the mouse。For drop the mouth。

Although people can do spatial job out。Randomly remove a few channels。And also drop block。

 remove a field block。The court's graularity。As a result。These techniques like job out。

 like data augmentation， can greatly improve this large neural networks performance。

Here is the performance of Re 5 as14 gig max。And this image that top on accuracycro。

 this is the baseline。About seven to 6。5。After weekss up， almost 78。after an Al al。冇 than7 seven。

By using term log more than 7， eight， and so forth these large models。

Drop out and data augmentation really helps because large models tend to overfe。

So drop out and data augment prevents overfeing。However， for tiny models。

 we did the same experiments。Unfortunately， both job hop and data implementation are actually hurt。

The more we add， the more techniques we add， the less accuracy。So I had mix out。系你哦。

I didn't often all get hurt。Primi when it helps most not parts。And we suspect back。

The timing model lacks the capacity， doesn't suffer from the overfiating issue。

 but suffer from the underfiating issue。 We don't have enough capacity to learn so much knowledge。啊。

或者看恋来说。So contrary to image augmentation， now we think about having to network augmentation。

To augment the model to get some extra supervision during training or the timing model。

And we still want to deploy a small tiny model。I here。Rather than what channels。

But during the learning process， we find some redundancy helps。

If you can sometimes have four channels， sometimes three channels， not just these two channels。

 it is helpful。For example， once you get stuck in the local minimum， some actual dimension。

 some actual degree of freedom can help you get away from the local minimum。And indeed。

 network augmentation for the hanging model， this is more than equal hanging with only 23 mini maxs here we have four gigab maxs so two orders of magnitude are difference after adding that on the accuracy economy improved。

So how that works。So this is the vanilla training， we have a very small model with only two neurons。

 in this case， three layers， two neurons。And then we build an automated model。

 all of this original model， very similar to the one forward article。So here we start with。什么矛东。

And been。Expanded in different dimensions， we can use。Child dementia we can use the FA dimensionia。

We do an element to the model。AndSimilar， that principle can of quite similarly to large language models by increasing the number of tasks or increasing the number of channels。

 etcter。Build an augment model， we need to estimateimate the base model with the automated weights。

W base， they actually are actually share with the red park。

And then we get a gradient both from the G base， gradient base versus the gradient from the augment polygaate model。

And we are going to挨 the mark altogether。So this is the phase supervis。

This is all the zero rate supervision， it add an extra supervision to the base model。

A different staff we can sample different size of the network。

 sometimes we can sample a larger model， sometimes you can sample a smaller model。

What doesn't change is the inner part。All share the same ways with the original small。

And as a result， we can see the learning curve for both here in the training， here is the a。

Its called validation。That all improve the accuracy both in the premium time and also the validation time。

 and both on the training and also the validation。或者太你猫。But for the large model。

 it actually is even help but a grid。So for the training， it need to help， but for the validation。

 it need to help， meaning that the large model already has a pretty big capacity。

 doesn't suffer from。Underfa by overating， what they should do is to augment the beta。

 not augment the model。Which is actually echoing with our previous assumption。

These large models are always picking and small models underpin。

Here we are showing natural augmentation is actually a throughout knowledge dissillation。

How far in the baseline is this knowledge dis rev。And this is macro augmentation plus knowledge dis working together。

And also for transfer learning， we compare two scenarios， one is small in。

And then another one is just training longer， twin for4 x longer。Sometimes。That accuracy hurt。い会。

He was a natural all patient。It provides a better transfer for learning performance。

 than knowledge to utilization， and also the full extreme scale。

So we also try to apply natural augment to object detection。So not only classification。

 but also other time。ウさ？X access is a number of maps。W it says is the plus VOC。

 accuracy there's the co accuracy？So for the same model， we can improve efforts。Equally。

 when we can reduce the Mac if we want to achieve the same amount model。

So this is the limitation here is that I only explore these visual paths。そ。This work was found dirty。

202 cool， actually submit 2021 before this tragedy came。

 so it might be very interesting to try such ideas that's orientation to train those small。

 large numbers。Welcome to talk to me if you're interested that。Allright。

 so let's have a summary of today's lecture。 We shipped into a new chapter about small modelpart from pruning quantization。

 Now we are talking about knowledge dissolation。 We need a teacher and a student。

We can match several components， we can match the final output。

 we can match the intermediate feature map， we can match the intermediate weight。

 we can also match the intermediate gradient。Not necessarily， we need a teacher mode。

 you can also do self distillation and online disstillation so that we can train only once and distill during this training process。

Such knowledge as disation can work for many different times。Not just classification。

 but also we talk about how to apply that to detection， to segmentation， to guns。

To the better language process。And also we talk about natural augmentation fundamental techniques to improve the accuracy by augmenting the model。

So in the next lecture， we'll introduce the MC net。

 which is algorithms system some co design fortanya now so that we can deploy the microconters。

That's all today this's lecture。
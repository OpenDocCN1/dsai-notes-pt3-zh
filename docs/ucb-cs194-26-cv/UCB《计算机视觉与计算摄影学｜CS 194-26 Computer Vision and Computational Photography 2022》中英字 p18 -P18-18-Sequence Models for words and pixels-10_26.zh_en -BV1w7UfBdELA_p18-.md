# UCB《计算机视觉与计算摄影学｜CS 194-26 Computer Vision and Computational Photography 2022》中英字 p18 -P18-18-Sequence Models for words and pixels-10_26.zh_en -BV1w7UfBdELA_p18-

All right， folks。Today。We are going to talk about。Some data driven magic。and。Talk about。

Sequence modeling。That will end up getting us。Pretty neat results。In text， as well as in pixels。

Let's see how far we get。 So what I showed in the beginning， this is Michelle Guria。

 a famous director whos。It's all done by hand。 This， this kind of textured video。

 And this is called the amateur。 It's， it's， it's by this Dutch guy who basically doesn't know how to play any instrument and。

He spliced together a video that makes him play the piano and the drums。Just by reusing the data。

 And I think this is going to be the story for today， the using of the data。 Okay。

 so let's start from the beginning。Let's， let's do some。Weather forecasting。

 this should be something that should be familiar to you from linear algebra。 Okay， so how。

 how do we do weather forecasting， okay。Let's say we want to predict the weather for tomorrow。

 given that we know the weather for today and that the weather for tomorrow can have only three states。

 sunny， cloudy or rainy， right， kind of Berkeley weather， okay。So。Here is the。

 the dumb weather channel algorithm， okay。What we can do is we can collect a whole bunch of data。

 We're gonna be data driven because， you know， data science all the age， we' are going to compute。

A whole bunch of probabilities of。Given the data today。What is going to be the data tomorrow。

 So day today is sunny。 So we are going to basically look at every time it's sunny。 What was the day。

 What was the weather tomorrow Okay， and then we are going to basically count all the frequencies of occurrence。

 Okay， so we compute percentages for each state。 so。😡，Riny tomorrow， given sunny yesterday。

 sunny to today， given sunny yesterday， et cetera， eta， okay。Once we have all of that data。

Then we could just underroll。These probabilities。To do the prediction。 And this is basically。

 this is called markov shape。 Okay， so you can make this graph。You have three states。

 Saudi Arabia and， and cloudy。And then your， your。Transition probabilities。

 How likely are you to jump from one state to another。 are these frequencies， How frequently。Is。

 is it rainy tomorrow if it's sunny today， Well， if it's， if it's sunny today。

 there is only 20% chance its going to be rainy tomorrow。你该。More likely。

 you know how it is in Berkeley。 If it's sunny today， it's probably going to be sunny tomorrow。你可。

So this is our very simple mark chain。We can write this down as a transition probability matrix。

Right， you have three states， Sun Uran， cloudy。And you basically just write down。

 take all these transition probabilities， put them in a matrix form。

And you have a transition probability matrix。Okay， so far so good。Okay。

 let's see if you remember your linear algebra。 Let's say I start with today， which is。Sunny。

 so let's say that I have a vector， one hot vector， which is going to be。You know，1，0，0。

 Sunny is one。 cloudy is 0， rainy is 0。So far是 good。

And I want to multiply it by the transition probability。What am I going to get。Once I multiply my。

Current vector by this transition probability matrix。I'm going to get a vector， right。

 vector times the matrix is is still a vector。 What is that vector going to tell me。

Trability for what。问。😡，Tomorrow， right， for tomorrow， exactly。So I take whatever state I have now。

 I multiply it by this matrix。 I'll get the state for tomorrow。What about day after tomorrow。Again。

 right， Okay， what if I multiply by the matrix a really， really long time。 What am I going to get。😡。

How do I get it。啊。😮，这我。Eigen， it is the eigenvector。 In fact， the the the。The。

 the eigenvector associated with eigenvalue of one is going to be where。

 where this thing converges to。 Very good。 Okay， you guys are all good。Okay， now。啊。

This is a little bit you know， easy， pe， right？Let's see if we can make it a little bit better。If I。

 if I also know what was the weather today and yesterday。

How can I make this do a little bit better if I know。Instead of just the weather today。

 the weather or today and yesterday， how can I improve this。No。

 we still want to predict weather for tomorrow。So right now， we' are predicting whether for tomorrow。

 just from today。But it feels like if I knew the weather to， for yesterday and today。

I should do better， right， Because if we are like in this long， you know， dry spell。Then it's like。

 okay， it was sunny yesterday。 It was sunny today。 It's more likely it's going to be sunny tomorrow as opposed to if it's like tipsy de。

 right， So you should be getting better， better information if you know。

Two days of weather instead of what， yes。So how do I update。

 Because this model just looks at today's web。 It only has one information for today。

 What if I wanted。For today and yesterday。Yes。第二。😡，How many states。Well， it's， it's， you know。

 sunnyny， Sun and sunny， sunny is the really one state， right， So I think， I think it should be 6。

 right， But yeah， so you can basically。Make the states。

En code two days worth rather than one day's worth， rainy， sunny， or rainy， rainy， sunny， or rainy。

 et cea， et cetera。 So everything's the same。 Just you have more states。

The transition probability is bigger。But now you， you should be able to do better because you you have more information。

 You're conditioning on more information。Makes sense， so first so good。Coming back to you guys。

 hopefully。Okay。No。Let's do the same for text。 Okay， in fact。

If you think that your Android or Apple phone was the first one to do that， No， no， no， no， no。

 Claude Shannon in 1948 was the first one to come up with this idea。

Of basically modeling English language。As a mark of change， okay。So， the idea is。You。

 you take a whole， you take a big book。You again， just like in the weather case。

 you compute probabilities of the next letter given the current letter or the next word given the current word。

 Okay， so you build a whole bunch of these probability tables。😡，And then。

What you do is you start with a letter or you start with a word， or start with a couple of letters。

And then you see what is the most likely letter award that is following that。

And it just spit that out。 Then you shift。And they do it again and again and again。

 And you basically， under all this。This， this mark of change。 So let's， let's try to do this。

 Let's say that we have a context of two， two letters。 So kind of like yesterday and today。

 But now we have， sorry， two words。 Now we have。A state has two words。 We need， okay。So。

What is a likely thing that would follow we need。Food is good。

 but it's probably not the most probilist proable one， yeah。Yeah， some like。啊。😮，iveive me an example。

And the， yeah， those are probably going to be the most likely。So we need to another one， right？

 I mean， you sample from it。 So you have to be the most probable， just a proable one。Right。

 we need to。 Okay， now we shift our context。 We forget the we It's gone。 Now， need to。Now。

 what what's likely。Some verb， right。Give me a ver。Eat， sleep。 Look at this。 I'm I am good。

 I have a good model of undergraduates。Me to。Need to， to eat。 Now we， we lost this。

 Now it's just to eat to eat what。 Well， if this is like a， you know。

 French revolutionary history book， then to eat cake， Of course， right， There you go。 We synthesized。

A。E we sampled an English sounding text。This was done back in the 70s。 They did a little in。

 in Bell Labs。 They did a little program。 They called it Mark V Shaney， you know， Mark of Chain， but。

 you know。Like a guy。 And then。They would post。E， you know， emails on these， you know， old school。

 old school like Tider web， you know， text Tinder websites of the day All singles。

 they would post this presumably from this Mark Micheney and was just that。 And， and， and。

 and some people thought it was a real person。 Like， you know。

 I spent an interesting evening recently with a grain of salt。 So notice。How。You know， overall。

 it doesn't make any sense， but locally。Luckiocally， statistics are correct。😡，嗯，可以。So。

 this is our first。Very basic language model。唔该。So let's， let's do it for， for， for。

For something like the Nobel Prize winner， Bob Dllard。

Let's start with with take the first lines of his song。Every early one morning， the sun was shining。

 I was lying in bed， wondering if she has changed it all if her hair was still red， okay。We can。

Put this together。Take this data and make， again， a。A markov chain out of it。By。

Finding all the things that were the same。Collapsing them into a single node。

Are there things that are the same collapsing them to the same good no， okay？嗯那。You can， again， have。

You can put probabilities。 You can have transition probabilities between all those states， okay。

And now， just like in the weather case。You can start sampling from it。 Okay。

 and if you sample the right way。You're going to get。Actually， the data that you started with。Okay。

So this is one path through the graph。But， of course， you know。

 you can have another path of the graphic。 orre kind of randomly walking based on the probabilities。

 You know， the sun was still red。 Okay， that's pretty good。Her hair was shining， not bad。

The sun was lying in bed。 not so good。But， you know， it still kind of gets you。I was shining。

 and I was shining。 and I was still red， okay。所以跟 C。It's doing okay sometimes。

 and then sometimes it's not。Now， this should be very familiar to you。Right。

 you're using this kind of thing everyday。 What is it。Preitive texting， right。It's exactly that。

 predictive texting is basically just doing a markov chain。应该。Now。Again。As we said before。啊。It's。

 it's not。It's not。You know， if， if just one word of context is clearly not enough。

This probability of the， you know， of the current word， given the previous word。

It's trivial to extend it into。Multiple awards。Right， so this is， this is。Two words of context。

 trigram。And you can see now that this becoming much better。 Earl one morning， one morning。

 the morning， the sun， right， et cetera。 So we can see that extending the context。

Gets us better and better， better。O。So， this was something that was。Very exciting to us， Vis people。

And so， back in 2000。People thought， oh， you know， we can do this。For， for pixels， not just words。

 We can， In fact， we can do it for videos。OK。😊，And this is a very influential paper video textures。

And the argument is， you know， still images are okay， but not as cool as video clips。

 but the problem with video clips is that they， they run out the end。

So what we want is we want kindnova a never ending video clip。Call video texture， right。

 It's basically kind of capturing a texture type of motion。And trying to。Bduce it。This way。

Who can guess what they did？ I think now that I told you basically all this setup。

 you should be able to guess what what they did。 It's very simple。有。Okay， yeah， exactly。

 you basically。Okay， so this is what they want to do。 blah， blah， blah。哦，sorry。Allright。Every time。

 there is a。Every time there is a video。没。对对。😔，So basically， what they do is they turn a video。

Into a graph。Inter mark of chain。 And they just jump around。In this graph。O。看完。不ally。嗯。😮，Videos。

You would think that after 20 years。They would figure out， really。Really。Restar the program。

 close the program。 Re the program。 with do restart yes。All right。All right， okay， let's hope。

 That's hope。 okay。You know what， maybe I will。啊。There we go。Let's see if I can。There we go。

 All right。应该。So you can see that it's basically。It's， it's， it's sampling。

 taking a video and sampling it。As a mark of change。

 So sometimes you just go through the video forward that just a kind of a normal way to go through the video。

 And sometimes you jump back or you can jump forward。

So you turn just like we turn a piece of text into a graph here， they're turning a video。

Into a graph。And now you just basically sample your way around this video。

And you can have this flame burned forever。And it can also burn forever， you know。

 in infinitely many different ways。 Well， not here because this is a stored video， but in principle。

 Does that make sense。Yes。Okay， so what's the one thing。That we need to make sure。Is working。 Well。

 we need to produce。The correct probabilities。Right， we need to produce probabilities。

Such that the transition probability from a current frame to the next frame looks good。 Okay。

 so what they did is they basically each set pub， you know， computed。A， a transition matrix。

All the frames on x， all the frames on y。And。You basically， you can look at。

From any given frame to any given frame。How similar are they， if they are very similar。

 Basically in L two distance sense， If they're similar。

 theyre probably it's easy to jump from one to the other。 So it's going to be high。

 If they are different， it's going to be low， not good， not gonna look good。 Make sense。

So that's why diagonal is all white。 Why is diagonal all white。啊。😮，Well， yeah。

 because nearby frames are obviously going to be very similar。But if it was just the diagonal。

 you know， we wouldn't be able to do anything。 But the cool thing is that there's all these off diagonal things。

 right， This is our hopes for jumping around， basically saying， oh， look。

 the video is self similar in different ways so you can， you can jump around。OK。

So that's what basically were going to be doing。We're going to be doing a Markov chain。

 The only trick。Is to remember。That when you jump。You don't want to jump to the same frame the same the frame that is as similar to you as possible。

Because there is also kind of a notion of motion going ahead。

 So you don't want to jump to a word that is just like your word。

 You want to be jumping to the word That's just like。The following word， right？

 So let's say that this is your original video do to do， to do， you're going your frame I。

 And then there's I press1。 And you're just watching the video， playing the video forward。

 Everything's fine， right。And then you want to say， okay， let's。

 let's see if I can also jump from here。 Can I jump from I somewhere well。I want to jump。To a frame。

That' is going to be very close， not to me， but very close to I plus one。Does that make sense？

So that way， normally， I would just go ahead with my video。 Everything's fine。

 here I can jump from I to J。 And if J is looks very similar to I plus1， nobody is going to notice。

Make sense。So you want this distance to be low， and then you can jump。

 And that's how were going to set your probabilities。Yes。😡，Every frame。 Every frame。Okay。

 so first good。O。Now， you turn them into probabilities。 How do you turn things into。

 How do you turn distances into probabilities， This is the dirty secret that that they wouldn't tell you in Evans Hall。

E to the negative blah turns anything into fake probability， okay。There is a little bit of a。

 know sigma that you need to adjust。 and the sigma basically tells you。

 you know how eager you are to jump。 So you， you know in high sigma。

 you you're not really jumping much and low sigma， you're jumping more okay。Okay， we do this。

We said it go， maybe， yeah， let's turn it off。 Sorry， don't Don't go asleep。 This is like。

 this is the coolest， you know， lecture of the semester。 So don't you go asleep。Not。

 something is not quite right。So what went wrong here， yes。有。😡，So why is that。And。

 and how can we fix it。有。啊。Larger context， just like in the what we talked about with text。

 this is just not enough context。 In fact， you can think about it in terms of， of position。

 velocity and acceleration。 We are basically just capturing position。With one frame。We， you know。

 we can get an acceleration with two frame。 we can get velocity with full frame and relation with three frames。

 right。So， we could just basically capture。These other measures， or we could just give more frames。

 right， So， in fact， if we had three frames。We should be able to disentangle whether the pendulum is going to the right or it's going to the left。

😡，Make sense。Okay， no problem。 Just make our context bigger。Instead of looking at just one。Frame。😡。

We're going look at a whole little neighborhood。Kind of like an engram。

And all of these guys need to be， need to be similar for me to jump。Make sense。Very simple。 I know。

 this is， this is so simple。 Everybody loved it because it was so simple。 look at this。

 fixes all our problems。O。Now， there is one little tiny problem。

 What happens if we get to the end of the video and once we get to the end of the area where we're kind of stuck right？

 So they did a little bit of a， you know， old school RL Q learning to basically update the probabil is to kind of to compute into the future。

 So your cost is not just the cost of a transition。

 but the cost of all the other transitions after that。 and I'm not going to go into it。

 you can read the paper。 and it basically makes it so that。

You have to jump out at the last opportunity to jump out。So that you never get into the debt， okay。

And then you can do things forever。So， far so good。O， there we go。 look at that。Okay。And so， you can。

You know， this was before Harry Potter and like alive portraits。 they were thinking， oh， you know。

 you can use this for your Facebook profile。 Nobody， nobody， nobody bought it， though。

 but kind of looks creepy， but， you know。呃。You can also do this for multiple motions by basically splitting it into。

Inter。In the two separate video textures。Is it going to do it。Yeah。

 basically they are just having two separate video textures and theyre modeling them separately。

 What what I really liked is is conditional generation。 Okay。

 so here they they they they filmed the dude running and then they just ran optical flow。

 Remember optical flow。 So they just ran optical flow and they computed。The average flow field。

 average flow field vector。For the entire frame。 and that。

Kind of gave them information about whether the dude is running run fast or running slow， okay。

And so， now that you have。And they basically assign the score to every frame， fast versus slow。

And now what you can have is you can have a little knob at runtime as you're generating frames。

 you can say， just sample from the slow frames。😡，Just sample from the fast frames。

Or have a little knob and just change how fast or slow I'm running。This is a really cool thing。

 It's a real time， online way。😊，To control your generation。By just changing the。

 the probabilities of which frames you want to sample。Very cool， very simple。 Make sense。第二次。1。😡，No。

 no， not， not， not not theyre basically they what they're labeling with is like the average average optical flow vector for that frame。

So it goes from like guess 0 to whatever the the maximum thing is。 And they just lay it out。

 And then， and this is basically just， you know， moving between them。Any other questions？Okay。

 it gets even cooler， though。 Check this out。They say， okay。You know。

 we can kind of do the same thing that they're doing in video games。

Where they basically have control over your characters， but for real characters。

So what they did is they they went to the pet store。 They got a fish。 They got a fish bowlwl。

They filmed。The fish for like， five minutes。Don't don't need that much。 maybe 10。They。

 the background subtracted the fish from the background。

 and then they wrote a little tiny code to basically detect。Where the the fish was heading。

 the direction of motion of the fish。 Okay， I think also using optical flow， okay。And now。

You're running your texture synthesis。Your your your video texture。

And then you have your extra conditioning。 and your extra conditioning is your little control term。

Which basically says。You are going to pay a cost。If youre。Vctor。To where the fish is heading。

The angle between the vector where the fish is heading。And the direction to the mouse pointer。Okay。

 so if the the fish is heading towards the mouse。This is going to be 0。And then they just， again。

 just ran this。And look at this。20 years ago， people， look at this。This is so cool。 And。

 and notice how like it doesn't just go straight up。 It's actually being natural， right， It's。

 it kind of swims in a natural way。All it's doing is just resling data that has seen before。

 just in different ways。It's all about reusing the data it has already seen。In different ways。

Questions。Okay， so， you know。It's pretty works pretty well。

It does not work well when you have too many things going all at the same time。 So like， you know。

 grass glowing in the way and its just not going to work because there's too many interactions。

 There's too many things going independently。 And so these methods are not going to work well for。

 for that kind of data， okay。OK。😡，So I kind of changed the order a little bit。

 But the reason for that video texture paper。Was that the year before。I had my first paper。

Part of my PhD on texture synthesis。你开。Where we use the very， similar trick。

But to synthesize texture。 So I want this to be a bigger texture。

But I don't want this because people are very good at at noticing， you know， the seams。

I want something like this。Okay， so how do I go from that to that。Well。

 it's basically the same trick。The same mark of chain trick。Except。Instead of doing it in， in， in。

 in one D， if instead of a context being。One dimensional sequence。Now， my context is going to be。

A little patch。In fact， it's going to be about half a patch because only half a pitch patch is。

 is filled out。 So basically， whenever I am to generate a pixel like this pixel P。

I'm going to look at all the pixels that have been generated before。

And find out what is the most probable。Caller for Pix P。Given that context， right， So again。

 we're assuming a mark of property and we compute a probability of P， given the neighborhood of P。嗯。

可以。The only problem now。Is that， you know， with with language， you have like two bigrams， trigrams。

 Quagrams， you know， a few words。 So okay， here the neighborhood is like if your patches， you know。

10 by 10， you have like 5050 pixels of context。Right。

Setting up probability tables condition on like 50 pixels， every pixel， RGB 0，2，55。 That's huge。

 absolutely invisible。So。😡，How， what is one way to。To fix this problem。

Without building all this probability tables。Let's see if anyone can。Can guess it。啊。

You couldn't do patch at the time。 but， but you're still， it's still， it's still too big to。To big。

 to build probabilityability tables。You know， I get a PhD for this。

 Surely undergrads 20 years later should do。是的一嗯。You could do that， but well。It's still， still， you。

 you're saving yourself like three dimensions。 You're still， you're still at hundreds of dimensions。

有。Tell me more。Okay， it's actually much simpler。 What we can do。 Remember。

 we have the original input image。What we can do is at runtime when we're in the situation that we don't know which pixel to fill in for P。

We just take the context around P。And just go directly into our input image。 slide it around。

Striide one， just slide it all around and find the closest match。😡，Or， you know。

 a few closest matches and just randomly sample from them。那这。😡，Right。

 this is equivalent to actually this is something that Shannon has also suggested instead of building probability tables for your books。

What you can do is given that you have your， you know。Your trigram。

Open a book at a random page and start reading until you find those that those three words in that book and just take the fourth word。

Okay， that's basically just doing this at a run time instead of pre computingut。O。

Li little bit slow and was definitely slow 20 years ago， but。It you。

 And then you do it basically one pixel at a time。Right。But。😡。

Kind of surprisingly effective with one parameter， which is the your context， your， your。

 your kind of。Your， your， your， your contextual window， right？ So if your contextual window is small。

 you know， you basically get O， there is some。Some white snakes on the black background。

If you make it a little bit bigger， say， oh， there are circles。If we get it a little bit bigger。

 all of the the circles don't like each other。And finally， you know， you get kind of this pattern。O。

So this is kind of how。As we change the。Size of the window。And here are some examples。

Here are some more examples。I really like this because this is kind of like a homage to Shannon。

 So now we take a picture of text。And then we want to synthesize picture of more text。

 And then if your window is too small， you know， you get the alphabet soup。

 But if your window is big enough and you're sitting back and right in the back。

 it kind of looks like text。Prety cool。And because we are doing it one piece at a time。

 can we can do whole filling。We can even do out painting。嗯K。Okay， so that。

Motivated my friend Aaron Hertzman a couple of years later to say， okay， you know what， I can。

 I can actually do kind of image to image translation with this。In fact， I can do。

Kind of the visual version of analogies。 Remember， analog from the SATs。

 A as to as prime as B as to what。Well， you can use this texture synthesis technique。To， to create。

To kind of， to kind of use this analogy， okay。So。Here is the idea。

What we are gonna to do is we are gonna say， okay。I'm going to。You need to figure fill in B prime。I。

 I， I'm going to look at what， what B looks like at that point。

I'm going to then look up something similar to B。In a。Take that。

 look up what a prime looks like from a。And then just oh。考标文。Copy over from a prime to B prime， so。

Look up， search， look up， copy， little circle。And that's it， and。And it， yeah， there we go。

And it just kind of worked for a bunch of different things。Could do blurs。Edge detection。

Some art filters。Colorization。And like， paid by numbers。Again，20 years ago。Just this， this fall。

 we had a little follow up on this work2 years later。Where we， we kind of revisited this problem。

But with an even simpler technique。The technique is。Okayay， we say okay， you know。这是拿机。

And we want to do it for， basically， you know。Whole bunch of different tasks。And what， what。

 what we did is basically just。Put these four images into a single image。

 Just concatenate them into a single image with this， you know， wide divider between them。

Can just basically do whole fillinging。Useer， you know， one of those deep fulfilling models。

 image to image translation， kind of fulfillfiling。And it magically， if it has seen enough data。

It magically produces a good output。And so it can do， you know， segmentation or whatever。

 segmentation with quotes。And it can do other things like this。 Okay， so now it's even simpler。你该。OK。

😡，说发生个。😡，Okay， now。Now， we are going to any questions on this before we。Questions here。要。啊哈。法。对的。

Exactly， exactly。 So that was that is the kind of， that is what we were trying to address the fact that。

It couldn't。It couldn't deal with something that it didn't really see before。

 it didn't see something very similar。So it turns out with the current wholefil models。Like Me。

 for example。They are able to overcome this。And so now you can actually do it， you know。

Find analogies for things that that it really hasn't seen exactly the same thing before。要要。这是这要。

So for the image analogy， just one。For actually， for this thing。It also seeing just one。

This is basically just seeing this thing， but。The painting model has been trained on the gazillion images。

Right， so this is where the smarts are。 the smarts are。In， in。

 in having a huge amount of data that you have seen before。是啥一。嗯，哼。This one， right。60万。要。

So you're comparing this patch in B to all the patches in A。 That's right。So when if。

 if A and B look very different， it's not going to work。Yes， absolutely。

 This only works if A and B are pretty similar for image analogies， yes。呀。Okay。

 so I think one trick here， you know， back in those days， people use a lot of tricks。

 I think one trick here， first of all， the patch is very small， maybe like 3 by 3。 Second。

 I think it was only done in gray scale。So I think in gray scale。

 in a three by three patches in gray scale， it's probably you can find enough similar things。

And all you're learning is basically just to blur。 Get rid of five frequency。

 So it doesn't seem to be that hard。对。Questions。Alright。O。

So this is basically all kind of old school things。But now we're going to make a jump。

And really supercharge our good als and mark of chain with ns。 Okay。

 but I wanted to remember that it's still very much。The story is exactly the same。

 It's a mark of chain。With angrams。But。Let's say that。 we want to。Use the Shannon trick。

To generate text。For， for Bob Dylan's song， okay。So let's say that we wanted to see if we could spit out this red at the end of the second stanza。

唔开。Now。It's important for it to know that it's still red that it refers to hair， okay。That's good。

But because it's a poem。It also need to rhme。Okay， and so even though if you're doing N gra。

 you know， some trigram quartergram。Hair is definitely going to be in context。Bed is all the way。方而位。

So it's， it's not going to be in context。So you， or you need to have a context that's really。

 really huge， right。So you now we need to have a context that's like。13 words long。

 just to get your rhymes。嗯可以。So here we have the same problem we did with texture synthesis。

Where our probability tables。Are becoming too unwieldy。啊，可以。They， they are becoming too big。O。

We need to do something better。We want to have a big context for our Mark chain。

But we just don't have enough power to encode such a big context。 So what can we do， Any ideas。

So we can try doing the same trick I did at 99。Which is don't build those probability tables。

 Just have a big book and just search。😡，In the book。富儿。For a text similar to that text。

 And then I'll have the right answer。Right。What are the pros and cones here。呀。Yes。

 you're only going to get the same line and you're only going to get the same line if， you know。

 if you are already， if you're already Bob D， you already published this。If you're。

 if you're doing something new that hasn't been in the。In your example set。

It's just not going to find a good match。And then， you know。And that's why in the texture synthesis。

 we were using textures。 And the nice thing about texture is the texture， as we talked before。

Texture is like a big data in miniature。 It just， we know that it repeats。But， you know。

 Bob Dylan would have got the Nobel prize if somebody else have written stuff before him。

 that was exactly the same。 right， That's the whole point。You do something new。Okay。

 so that doesn't seem to work yet。Very good， very good idea， exactly。It might be。

That we don't need the whole context。Maybe there's just a few things。That are important。O。So。

 that's why。好玩。2。OK。That's why。We can。We can say okay。If I want to spit out red。What I want。

Is I want to give some？Okay， you know what， I'm gonna， I guess I need to， I need to tell。

To tell you this story first， sorry。OK。So the first thing were going to do。Before。

 before finding the right words is where。Basically。

 it's going to start to give up on trying to model this whole thing as a big。

For build a table and think of an approximation。 How can we approximate this thing。

With something smaller， right。And。You know， in the field of approximations。

 we know we we can do Fourria serious。Taylor serious。

Or the new wal chain thing you can do in neural networks， right。

 neural networks is basically just a giant， universal appromator。You give it any function。

And with enough parameters， and enough。Enough back passes。It just approximated， right。

 That's the magical thing about neural networks。 It just， it's able to approximate anything。😊，收。😡。

Let's see if it can approximate basically that ginormous。Context or problem。

 This probability distribution of given the context。Predict the the next word， okay。

So how do we approximate this？Okay， so let's say that we want to produce a neural network。That。

 given this context。Spits out the next wordd， red。O。

So what are we going to do is now we have to have。 we are， we need to have our string， our sequence。

We pipe it to a neural network。And it did sound the war red。So it's basically the same kind of thing。

 except instead of a lookup table。 now it's a neural network。 So far so good。O。Now。

 with the neural network， things are going to get a little bit ugly because neural networks。

 they take numbers， not words。Right so， you know， we could just enumerate all the words in the English dictionary by a number。

But what's， what's what's the problem with this。啊。Well， you just， I mean， just， you know。

 you just enumerate them like。Like in， an imagenet， you know。Car is number one。 buses number two。

 you know， and then you have a one hot vector of  one in 1000。And what's， okay。

 so there's going to be a lot。It's going to be very long。

Anything else that's problematic about a here。Yeah， but， you know， I mean。

 English language is maybe like 100000。 If you change all the endings， maybe it's going to be like。

 I don't know a million， but， you know， a million is maybe not that bad， not that bad。II any。

 any more fundamental problem， yeah。Exactly， exactly。 remember， neural networks。 they are really。

 you know， they， they are not discrete。 They're continuous things。So they really want。

Similar data points to be close to each other。And here。You know， able and about。

They should not be close to each other， right。They are， they are even different， you know。

 terms there are different parts of part of part of speech， right。So instead。

 we need to somehow represent。Wors。In some sort of a feature space where similar words are close to each other。

And different words are far from each other。So how do you do that。

So one way to do this is this old idea of work to V。You give me a word。

 I give you a vector representing that word。And it's one of the early papers on self supervised learning。

 basically， which says， take a big piece of text。Take a little chunk of this text。

And for any given word。Train a little network to predict。

Other words that are going to be near it in this little chunk。 right。

 So this is a completely useless task。Except that remember when we talked about that the very the later layers of a neural network。

They give a representation。 That's actually very useful。And so when you do this task。

 the last layer of this representation。Gives a number to every word。

And the cool thing is that related words。Are going to have the related numbers。Because。

They are going to have similar context。And so， now。You can lay them out， and now related words。

Like synonyms。Are going to be close to each other because they can， they predict similar contexts。

Okay， so it's kind of like。You know。You are related to people who， if you have similar friends。

 that's the idea of word to Vck。Okay， so now we have a way to go from words。

To vectors where the vectors actually are。Meaningful and similar awards have similar vectors。So far。

 so good。Yes。Okay， so now。We have。A way to encode every word here with some number， some vector。O。

And now， narrow network needs to kind of get take all of those。

Vectctorors from all the input words and produce vector corresponding to red。So， far so good。OK。O。

 once again。If we try to do this kind of in a brain dead way， just brute force it。一问。

Ginormous neural networks are going to have problems because this is still a very。

 very large context。So a lot of context。 And you basically need to find all of。All the pairs of。

All the combinations of all of these words。And it's just going to be a lot of parameters。 Now。

 you basically， you can do it if you have enough time and you have huge amounts of data。唔该。But。😡。

It's going to be very， very hard。So we need to do a little one more approximation。

And this is the approximation that we already talked about。So remember。

 if we want to predict the word here。What do we want， We want。To be kind of like N Gram like。

 you know， mark of chain， Shan and trick hair was still something， right。

 So basically it needs to flow。 It needs to have the right texture properties， the right。

Mark of chainin story， right。But。😡，It also， we wanted to， to rhyme with bed。Right。The rest。

 maybe we don't really care that much。 We really want to be kind of locally。

 look good and also get us the ride。Does that make sense。So， basically。What we can do。

Is we can figure out。Which words in the context we really need to pay attention to。

Which is the words right before the word。And the word at the end of the last last stanza to get us the rhyme。

你该。And this is。This is called Di， an attention layer。The attention layer is telling you。

Out of this whole big context， which， which things do I need to attend to。

 Which things are really important。O。And once I have that， now I can have another network。

That actually takes that context。And doess the prediction。嗯该。And also， by the way， the， the。

 the attention doesn't need to be binary。 It doesn't have to be 1 or 0。 It could be， you know。

 it could be some probabilities as well。Okay， but it still kind of reduces your search space enormously。

Does that make sense？O。So when people talk about attention layers， this is what they mean。

 They really just mean。In a mark of trade。My context is too big。

If I reduce the context to only like a few words， it's not going to give me a long range dependencies like rhyme。

Or like closing parentheses or something like this。 So what I need is I need to have a big context。

 but I don't need to take everything within that context。

 Maybe I need to pay attention to the open parenthe。 Maybe I need to pay attention to the rhyme。

 I also need to pay attention to what happens right before。 but in the middle maybe not so important。

😡，Coass， yes。Exactly， that's the question now。Yeah， how how do we train this thing， right， yeah。It's。

 it's similar。 It is kind of。It is， It is similar。 but here the idea is that we're going to learn them。

 We're not going to hack them。 We're going to learn them if we're going to。The。

 the computer is going to figure itself out。What is going to be important。Other questions。要。

The only difference。Is that the mark of chainin says。I need to use the last four wordss。

Whereas here you're basically allowing yourself to skip to skip some words in your context。

 So your cortex is very big。 So think about it as a markov chain with a really ginormous context。

 But some of the words in that context， you're going to ignore。😡，Also， for， for different words。

 you're going to ignore different words。 So this context is kind of。Case by case， dependent。

 It's not like you're always gonna skip， skip the middle。 You know， for the next word。

 maybe it's gonna do something different。So if I just case by case basis for every wordd。

The context is going to。 their attention is going to change slightly。Or not slightly， actually。

 a lot。Does that make sense。Okay， other questions。Yes。I think the more the better， yeah。Yeah， yeah。

 You want， the more the better。 And then hopefully that the attention is going to pair it out to something more reasonable。

 yes。要。阿斌。You are still saving computation because remember， this。

 the next word predictor is going to be some kind of a。approximation neural network。

 So if something has a very small probability。The appmator is， is going to have an easier time。

 you know， dealing with it。 So even if it's not binary， you're still， you're still saving some。

You know， entropy， entropy is being saved。Right，Because remember， this is also this is still。

 this is still a network that's still doing an approximation。So if if it was just。

 if it was just a lookup， I would agree with you。's not， it's not really saving。

 But because it's an appmator， it's still saving us stuff。1。So， yeah。

 so how do we train the attention layer， right。A little bit。 It is like kicking the problem back。

 So let's， let's get， let's get to that。 So how do we train the attention layer。

So there is one way to do it。First， you hire a whole bunch of， you know， poetry undergrads。And。

 and get them to annotate all the rhymes and all the。

 all the lyrics and all the other things that's important。Not feasible， right。

So what they do instead。Is that they basically do。Kind of a end to end training。你K。

So they basically train both that tension layer。And the， and the next。

 in the next word prediction layer at the same time， because， you know the， the right answer。

 The right answer is this thing needs to speedit out threadread。

 That's the answer that we are looking for， right， And you get it from， from the data from text。

Right。So now the idea is。For red， for this to spit out red， what does the attention layer need to do。

Right， so， for example， let's say that initially， it spits out brown。Right。

 it's been sound brown because， you know。Maybe。You know。Hair has changed at all。

 Maybe hair usually is brown。 So it thinks that brown is probably a good， good， good， good。

 good good answer， right。But then we know that the actual answer is not brown， but red。

 The back prop is going to say， no， no， no， no。Downgrade these things。This has changed not at all。

 ignore that。 Instead， pay attention to bed， because that will give you the rhyme。O。And that way。

 you're going to be training the whole thing。 And that my dear friends is what's called a transformer。

你开。It's basically a way。就。Have。To represent a very complex。Transformation。

By first attending to some parts of it， and then。And then using that part to make a prediction。应该。

Now， this is really just one transformer layer。Okay， okay， let。

 let's actually do a little bit more details， so。What is it actually doing。

 It's actually doing a linear combination。So what their attention is actually giving you is this linear combination of weights。

For， for the different words。And you're combining them together。 And this gives you the。

 the context for the word still， okay。And then you do this for basically all the other words。

In your input。So you have you get this context vector for every single word in your input。😡。

And then that is what， what the predictor is going to take。Together with the word itself。To give the。

这个在。The answer， right， And then because it's a sequence， we do it。You know， one word at a time。

 So we say。First word。It predicts the next word。为。You know， we take that next word。 We。

 We put it in the second position。Run through it again。 That's our our third award。

 We transferred the third award。Et cetera， et cetera，1，1，1。I'm sorry Yeah， one word at a time。

We make a prediction like this， okay。And now we can do crazy stuff。For example。

 we can see this 16 president was。Any remember。Look at that。 Very good。

 Abraham used to be the next word。Right。I mean， that's kind of crazy。Like。

 you need to know a lot of stuff to， to be able to answer this question， right。收。

We need a lot of parameters to represent this。So what usually happens with transformers。

Is that you actually do this。You每个人的 hierarchy。You have not just。

One little attention plus prediction。 but you stack them together。With more and more。

parameters in more and more context。So it can really remember a lot of very fancyman things。

 And so basically， what happens is， you know， things like G3， for example， have like 96 layers。

 you know， or even more other systems。And so what happens is that。The lowest levels。

 they are basically just giving you the syntax。 They are basically essentially very similar to。

 to Shannon's mark of shape。 It's， it's basically just doing the， the simple， you know。

Word texture kind of thing。 You just need something that sounds good together， right。

 But as you go up this chain。Eventually， you get to high level knowledge and semantics。

 And who is the 16th president and all that stuff。Okay， but。

You basically stack this information together。And the nice thing is that you train at all。

From this self supervised task of you know， predicting the next word。

 So you don't need to label anything。Right， from that one label of what the next word。

Everything just gets assigned。Questions。OK。So how much data to train this ginormous thing。Okay。

 a lot。 I hear a lot。 Any other ideas。Qudratic， anything else。How all of it。Just all the data。

 I mean， look， text is， there' is finite amount of text on the Internet。

And it's really not that much， really， you know。Just all of it。 right。

 This is what the modern models language models do。 They just train in all the text on the Internet。

😡，Now， if you just do it， you know。In a straight in a straightforward way， it will take you。

 you know，355 years。But the nice thing is that though these transformers are very paralyizzable。

And so if you paralyze everything， it seems like it could， you know。

 as as as little as a mouth to just train on all the data on the Internet。

All all the text state on the Internet。我们可以。And then you can， you know。

 and then it knows a whole bunch of stuff because it has seen a lot of stuff。

 just like we've seen in this kind of data driven stories。You know， if you have seen a lot of stuff。

 you know a lot。 You know that the quote from a wonderful movie Groundhog Day， Bill Murray says。

 you know， maybe God is not omnipotent。 Maybe God has just been around for too long， Right。

 So this is the kind of thing， right， You have so much data that you essentially。

 you don't need to think that much。 You just have a whole bunch of answers。

To the questions that that that are being posed to you and the times when you actually do need to think。

 you realize that you， you're not so good。So。Even though it's all very impressive。

You're still very much in that video I showed at the beginning of dude。You know。

 pretending to play the piano and the drums， right。

 you're just reurgitating stuff that you have seen before。O。

 you're still using this kind of texture idea。 And if you're actually trying to do something new。

1个的费用。唔开。Okay， you can do， you can do haiks。You can， you know， you can do a translation。

It's not going to do anything when you actually need to think。But so this is。

 these are slides from wonderful Steve S。 and I will show I'll post a video where he has a kind of beautiful like five minute video of this。

 And he actually decided he's going to ask it for a chocolate guacamole pancakes。😊。

And they produced a recipe。 And it's kind of cool， you know， and。嗯， no。And he actually made them。

And he claims they were pretty good。So there is Steve sides。 I'll put the links in the， in the video。

All right。O。In the last 11 minutes。We are going to then finally get to， you know。

 the topic for the course， pixels。O。So if we can produce words。And we have seen how we can， you know。

 substitute words to pixels。Let's see if we can use big language models to produce。

 produce pictures for us， well， you know。We跟。We can do that。could do that。That's pretty cool。 But。

 you know， I want pixels。That's still pretty cool。But I want pixels。I want something like raspbers。O。

Okay， well， raspberries are， you know， that's too much。Too many pixels。

 but maybe even like a low resolution version of resps。

RightI can I can basically turn raspberries into into RGB pixel values。Right。Call them words。

RightThey're just like pictures in a book， words in a book， right。And， and then I can do this， right。

 I could basically。Get a whole bunch of pictures。Maybe not all the pictures on the Internet， but。

 you know， like， you know， a gazillion of them for all sorts of topics。Okay。And。

 and just train my transformer。To， you know， to produce。A raspberry image。 And then it will just。

Start outputting， you know， our GB values。Right。So what's the problem with this。The problem is。

That language is， is kind of compact。 you know， we humans created language， so。

There is not that many words， there are way more pixels than words。😡。

So even though those large language models are very powerful。

 they're not going to be powerful enough to， to model， you know， millions of pixels。Okay。

 so what we can do， well。为看呢。We can make the problem a little bit harder， easier。

By reducing our image。But into 32 by 32 image。Okay， so basically， we're going to。

Convert an image into 32 by 32 patch。And of， let's say，8 by 8 pixel patches。

 And every one of those pixel patches is going to be what we remember。

 we talked about visual awards like the clustered。Patches that we talked about before。So。

 then we can basically。Turned every 8 by 8 pixel patch。Into some number， intoto some visual word。

 And now we have enough。啥意思？😡，To be able to， actually。Represent。An image with maybe like 1000 words。

Right。And so now we're in a position where we can actually model our images。With the language model。

O。😊，So let's say that we want to have a language model spit out an image of squirrel reaching for a nut。

OK。😊，Well， were just。Start outputing。Visual word tokens， token numbers， right。

And then every time for every token I say， okay， what's gonna be the next token。 Well。

 if we are using the engram just like like a shannon kind of engram。

It's only going to look at the previous tokens。 It's， it's probably going to use a one。

 So that's not good。If we are going to。Use kind of like the， the。

 the my old texture synthesisth approach， where it's actually looking at a little patch。

Then it should do a little bit better because it no。 Okay， it looks like an edge。

 So it's gonna do a 6， right。But， remember。These transformers， they actually have。

 they look at all the context because their context is huge because they have attention。

 They can look at the entire context， including what is it that we wanted to generate。

 which was a squirrel。So at every point， it still remembers it's a squirrel。 And， of course。

 the attention is going to say， squirrel is important。

 Pay attention to the fact that it's a squirrel， right， so。That way。

The language model still keeps abreast of what is it that it needs to generate。

 even though it's generating， you know， pixelix after pixel or visual word after visual word。O。

So you keep generating it。 boom， boom， boom boom， boom， you generate a whole image。

Then you change from the visual world number to 8 by 8 patch。Put the patches together。

 Oh look at this。It's a kind of a blurry squirrel。How do we do， How。

 How do we make it a little bit sharper？ Well， we talked about all this unit and all this， you know。

 image image translation。 You can just train an up sampling model that takes。

Low resolution images to high resolution images。佢将。Not bad。

And the cool thing is because it's kind of probabilistic， the same。

The same prompt can give you multiple different versions。Of， of this， of， of the output， okay。

So in in fact， this is， this is a。Lesser known model called Part out of Google。

It's less well known that， than， you know， stable diffusion and and， and Dhi and all that stuff。 But。

 but I think it kind of connected well to our discussion of Shannon， yeah。Yeah。

 these are all outputs for this prompt。We don't know。那。Chances are， it has not been。There has not。

 in fact， people have tried to answer this question。 and so。It people were not able to find like。

 exact image like that。But chances are bits and pieces of the image。

 just like with all of these other kind of mark of chain type methods。You're always。

 you're not really generating anything truly new。 You're just taking bits and pieces。From。

From your prior experience and putting them together。下午。Yes， this， you know。

 this quarrel phase and this not。 they have been seen before。But this competition。Probably not。

And in fact， you can， you can really try to make things。You楼。

That are really very likely not have been before， right， Gore reaching for a not underwater。You know。

 maybe the， the， in the prehistoric times did the， you know。

 did the squirrels still going for naughts。 Yes， they were。You know， some score or not。

And it kind of gets crazy when， when basically， you get like a squirrel shaped houses and things like this。

There are a adventure of writing squirrels。网告。And apparently， you can even do latte art。With。

 Prety cool。O。Okay， so we have not talked about the things that that that got all the attention。

 Imogen and Dali。They use a different thing。 They use the idea of diffusion。

 We're going to talk about it， next time。But the cool thing is that， even though。

All these techniques are using somewhat different algorithms。The outputs are actually very similar。

Which do you should suggest。That it's less about the algorithm。And more about the data。It is really。

The， the， the killer thing here is the fact that suddenly。

 when you are able to absorb huge amounts of data。When you get a whole whole huge amount of data。

 and then you have an algorithm like the transformer with gazillions of parameters who can absorb all this data。

Suddenly， out of this。Bits and pieces of your former experience。You get something that's very cool。

Questions。Can we turn on the lights。Cos two minutes for yeah。Everybody's like stunned， yes。OK。Right。

So the word embedding is just for an input to the neural network。I mean， frankly。

 I suspect that if you had enough parameters， even ordering your words by like 1，2，3，4。

5 without word embedding would have still worked， just that you would have wasted a whole bunch of parameters just to order them around。

哎。you're right that it's for rhyming， you don't actually the similarity shouldn't be semantic。

 The similarity should be audio。That's something that when you train it on poetry。

 it should figure it out。 It should figure out。The rhyming embedding on its own。 So somewhere。

 somewhere deep in that transformer， there is another embedding。That corresponds to rhymes。

It would actually be very cool to kind of， to find out to， you know。

 and like to spinit it out and have like a rhyming dictionary。😊。

That that dangerous warmer has learned。 That would be very cool， yeah。Other questions。Yes。も対。

It's hard to look at these things， unfortunately， it's easier to look at attention layers。

 especially for visual data， because the attention layers。

 you can imagine them being like basically like like images where like pixels that are being attended to are bright and pixels that are not being attended are dark。

 So people have looked at attention layers for images。 And you know， you kind of get， you know。

 you get to see what it's looking at and it's usually looking at know the things that you would expect。

It's not very telling， though， but。
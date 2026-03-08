# 【Hhu Dusseldorf】表征学习 ｜ Representation Learning Msc Course Ss2023 p04 P04_W04_对比学习__SimCLR与基于互信息的证明 -BV1RPZwB6EJZ_p4-

Yeah。Sorry。Hi， and welcome again。ToReation learning today will be a little bit more theoretical lecture about mutual information and。

Interive。Learning， so this will be kind of a。Departure from the audio encoder and dennoing stuff from last exercises。

嗯。So。And let's get started。So one of the basic principles that we talked about in the first lecture that really a good representation to have is consistency with respect to some transformations。

So， we have our。Image X。こて anything guys。And keep from there。Computer  two transformations。X to the1。

 x to the two， so this could be a blurred version of the image or like a cutout。

We will see examples of the s。Then we want。For a good representation。We want that。你知号。拿来发就去。猫。

That the presentation space。In该。So that's what we want。And now the idea is。Basically。

 why don't we just enforce this directly？So what happens if we just do this。You take some。

Similarity measure that's high， if the two numbers vectors are the same and low。

 if they're different， could be cos and simulated， could be something different。And。We just。

Next toize this whereas we take that expectation。我哥。Those transform images。And then we。

Maximize this2。And then we basically directly enforce that two different representations have the same。

 the representation of two different transformations have the same representation。

So what would be the problem if they would just do this？Yes。not only need one representation。 Yes。

 exactly。So。It could totally collapse， We could just emit everything to one vector then the similarity is always high。

 so imvariance alone is clearly not enough because then we lose a lot of information。

 So what at the end basically we willll do。M would take。Vis。Let's call them。外湾。W I think。

I turn on my Tuesday and that。Tles of。Different images。So this one comes from the same image。

 and those are from K different images。And then we want to maximize this。But one to。Minimize。

The similarity between。呃X to one。And the representation of the Y I。现 then。

Take a mean mobile eye or something。 So this is the rough idea。

 This is not like the loss that will end up at the end， but it is。

We want to maximize representation under our transformation。

 the similarity of representation and transformations。

But want to make any other representationation difference。 So we want the contrast。

 that's why it's called Conive learning。Okay， but to the。A better and proper loss function。

We view us in the information， theoretical sense。So I already say， if we just do this。

 the problem is that we lose all information。So we want to lose some information。

 we want to lose all information that is not preserved by the transformations。

So that pixels a transformation， it picks information that's like lost by rotating or other that you want to lose。

But， we won't。To keep everything else。So。The proper are one useful method for this solution information。

So goal this。We。1 to。Maximize the mutual information between the representations。对。

Are you all somewhat familiar with commercial information？怎么跟得多啊。嗯。

So the basic definition of the user information is。If we have two random variables。X was some。

Densityq of x。And y was conden to the T of y。连理。Nutral information of X。

And y is defined as the integral of。T， X， Y times。The logm or。X Y， divide5。Q of x and P of y。イ。D外。

Which is also equal to just thequebec lightbl versions。Between the。容ch。

Tensity the joint distribution。And the product recipient。

So we know that the product distribution and the joint distribution is equal if and only if the tool。

Bars are independent。And we know the care invertans only zero of this is infinite。

So the important properties here。In information。It's always great value to zero。And。It is。Equal0。都意的。

X and y。A independent。So if。If you listen to like the information theory course you know a lot about this。

Otherwise。I might see if I can find something online。

That you can read for some more background information。

 But that's like the important part that everyone want。 So it's a mirror。Of you some information。And。

You can show the specific maxim， if you can。Compfuseute one level from the other。

 But that' not so impossible。So this is what we want to maximize。

The problem is we cannot even computer。General information in general。

 so we cannot solve this integral。So we need to find some way to approximate it before we can maximize it。

So this will be now we goal to arrive at a particular estimate information information called noise contrasted。

Asuation and see influence。Okay so before we can maximize this， we need some way to approximate this。

The next drill is。Estimate the user information which in some random variable X and Y。So at the end。

X and Y are going to be the representations of different transformations of images。

But just for this subg here， there could be any random variable。O。So嗯。This problem is symmetric。

A property of user information is it'ssymmetric。I有 X。Why it it to the misinformation of。Y and X。But嗯。

We will treat the problem as little to asymmetric at first。This has like。Historical context。So first。

 I wanted to have like where x is the input and y is the representation and they。

Have a way to compute representation from the input， but not the other way around。

But that's not someone right now。And at the end， the estimate that we get will besymmetric again。

 but。即系你咩老放佢要食。ok。咁。So， the first。Estimate that I talk about is the。Esment by。Ba爸 and。打家说。这 call。系。

DA。And here the assumption is。That this distribution is known P of。喂。G me X。But here x given Y。で not。

Or it is。You can contribute this。When we think about。

The X and y at the end will be representations of transformations or images。

These assumptions don't really make that much sense。But let's just go with the funnel。

So in classical。Paian variational methods we will replace。

This unknown function with some variation distribution。

 So if you know that the derig of the variation of encode cota is basically the same approach。

So you approximate。P of x cube y with some variation solution， Q of x cube y。Then。

He then right down the corner。So， we have news information。Thank why。

Now I'm just gonna write on the quick initiative again here。X， Y time。Lock of P of。My the five by。

And of why。And now we can extend the byq of y x minus x。And then pull everything apart basically。

And we get。Free terms， again。The first one looks like this。就。This is just an expectation right。

 so this is just the expectation over this lock on。

 so instead of integral right this is' an expectation。We have the expectation of。Lock。Q of x given y。

This is basically。レスタア。Then y X。嗯。Well， and Rose down here on should be X and Y， thank you。

Then we have。Minineus the integral， all that's right， it's an expectation again。呃。或者呃。Okay。

 minus the expectation between D X and Y。哦嗯。懂。P ofX。So， this is。This turn it on because it's。

In a denominator of the fraction， you put a minus here。And because there's no why in this term。

 instead of taking the。Expectation of P and Y you can just take the expectation of just T of X。

And if you know a little bit about information theory， then you will see。

This is exactly the differential entropy complex。😊，O。What's left？嗯。这。我食灯。Second， what the so strange。

唔讲啊。Alright， O。So。手擦开不心。P of x。And。Why divided five？P of y， of course， is just P of x。

Keep in mind to is just the definition of conditional。Provo， right。So then what's left is just。

The KL divergence。The traininging。I don't quite。Okay， what' then left is the。Interegral of。批音。

X and Y。Which we can write as。天个。Y times T off。X given Y。So this is equal to px n y， right？Ch。

The logarithm。好。T of x given y。So then can see is gone and Q of x given y。はですか。Alright。And now。

 we can。エクトワイ？And now we could basically just look at this part。

 and this is exactly the equivalent lightblar diversions between P of x cube y and P of x cube y。😊。

笑着。好感。收备好啊点记啊。SD。Expectation over a pure why of the code lightbl versions。不注音。P off。X跟 Y。And you of。

X变 y。Okay。So。This is a different way of writing。The usual information can X Y for any probability distribution Q。

So it doesn't matter actually a good approximation of the postia。But this is two nonetheless less。

Okay， so now the Ko lifeana version， of course， is always non negative。😊，Could it be just。Trropet。

你 get给你报了。这边边。In information is greater or equal。To。What was it the expectation of。Look。其。Why。

Plus differential entropy of x。And this here。Its our first estimate。TheBAS。So this is a lower bound。

 you always want to lower bound because then if you maximize this year。

 the idea is that you also will maximize mis information。But is there even a good fund。

 so can we achieve equality？Yes， we can。So。doctor就嘅q。Let's call it Q staff。Its just。嗯。第号。X and Y。

If our variation of distribution  Q is exactly equal to this。😊。

Then this correct light that Is have dropped。Is zero， and we have the quality。

So but can we actually compute this。This term differential entropy is problematic。

So it is independent of Q， but we actually remember that learning queue is only a means to end。

So the idea is we first want to maximize this objective over cu to get a good estimation of the initial information。

 and then we maximize our representation which。We change this year。

But we can't usually compute this here this integral。So it is another very good。

Estimate for our purposes。Okay， of course， the second at first it's confused。

Maximize with Q and then we maximize over the representation， but in reality of course。

 we will do growth at the same time， likely like with variations。

Any questions so far or have I completely lost you。Yes。

 I wonder if this is now or images or representation or is it like everything you want it to be。

 So at the end， basically， it could be anywhere random。Yeah。

So and if it's a distribution that's kind of like fixed， then this is a good estimate。

But for our goals， at the end， X will be the representation of image。

Or the representation of a transformation of knowledge。可以。Now。

We will introduce the unnmalized version of this。So， one problem。

Besides this annoying differentialtro terms that we。Must maximize over this distribution appeal。And。

Learning a distribution is always annoying because they somehow need to normalize it。

Because the distribution density must integrate to one。So and can always。Represented。

Probate distribution in different way， and I think I will do it。

that' because use a different blackboard。So now the idea is。He write authorration。This次有什屁如。

Losing a so calledled critic。当清。哎。X and y。I would just say。Q of x。

And why is equal to and leaveland space here， You'll see why in the second。E to the power F of。

Why divide it by？只怪 we。Y is the expectation。For to x， or to the power。X and Y。Okay。

 so F of x and y can any function。If you put it in exponential。

 it's a positive function or a yeah a positive function。And he divide by this year。

 it's so called partition function。Last so this that integrate up to one。So you can， if this。

It's known to you， I think whatever x and y is like a negative energy function。

But the basic idea is that theres some function that measures。

How related x and y are So of x and y is high， that should mean x and y elected if it's slower should mean they are not very late。

😊，我两我是有一个。Generally similar， or like optimal in our case， it should only be high if they are。

Representations from the same image that cover this image。If they channel information。So。But now。

 you can basically say。You can radically easily see that you can represent any distribution in this way。

I mean， we could block this into our。The A estimate back there。

But this doesn't actually help us much。It does move that block around。So now what we'll do。

 we will employ the trick。We为。Sca this。By P of x。This was the word underlying。Criricktic。

And this will be useful， because it will drop out。没。A the energy， as you will see。Okay。

 so let's plug this into our。The aES这。嗯。你 know。So， then we have。The mutual information on nothing。

We have the expected value of。哎。And。Hope I do want to write this。Okay， so lot of you。Q of x。

 given y is。Then they could know FO X。So look at these power cancer out。To打。locklock ofPX。Minus。不东。

Of z of y。And for now， the differential entrypy term stays the same， but of course。

The differential entropy is just。Minus。lock your x。And then expectation of what it。So。

 this is the definition。哦啲。took out with the minus definition of the。

Different the antropy that we have failed。And then this log P of x。Councers out。This lock PO X。

And then what what youre left with。It's the expectation of Q of x and y。F巴F x。minus。It's minus。

The expectation。我 pure eye off。娱乐。Of why。So here we drop the x because there's no x here。

And this now， we call。Unmobilized。BA estimate。So， why did we drop the Y from the F function。好，sorry。

Yeah， it was a mistake of my thoughts to should be okay， thank you。除嗯。There no just。

A slight problem with this but multiple actually。嗯。This inequality。Hos for any。

Probability distribution Q of X cube Y。But if we define this。This way。

 this in generally general not a probability solution。Because we skate with a peel eggs。

If we didn't scale the P of x， they would integrate to1， and this would be a probability illusion。

 but they also scale the P of x。😊，This is in general。Not an。Probilities secret anymore。But。

This is not a problem。嗯。Because靠。When we think about what this integral is， you can off。叫用 x条 y 。第X。

So by definition， this is of。P of x times。Why。机关。G X， okay。

 and let's call this part for the time being， like， I know。修车的哦。X and。

So Q tu is a proper probability situation because it integrates to one。Here， in our case。

 we don't find generally not。But what we can do is apply the cost sheet shots in。

I if you talk and then you know which otherwise。够不认す。こ刷。It's made written a her。T， I don't know。T。

And see， this is less than or equal to。The square Ro。Of the integral of T of X。

 T X times the integral of。Q tell的。キわ。So this is just the particular inequality。

Thats sometimes useful， of course， P and cube tida are both for distributions。

 so they're both integrated to one。So， this is just。喂。So。This means。

That even though Q of x given y is not a probability distribution， you can just。给个 job。嗯。With。

Number larger than one to get a broader distribution。

 and then we can basically use our inequality here。And so this too is also in lower bound。

For the mutual information。So if you wanted to do what it's like。就边灯。嗯。So。Let's say we have Q X。

X and Y， you define it as。E of x and Y divided divided。是歪。And he define。Q of。X。

Give y is P of x times Q total of x given y。Then the initial information of x and y is greater or equal to。

对。BA estimate。Of X， Y and。Lets。Look like a。修车呀。So basically this estimate if be block in Q here。😊。

And。This is then。Cter or equal to the PA estimate。Using our unmobilized function。清。

And this is then equal to our。UBA S。Using our critic。嘿。So now we still have a lower bound。

For mis information。But can this boundge become tight？So can you equality quality。And。Yes。

 this is very easy to see。So， the optimal critic is。Give by。Llock P of y given x。Plus。

 some constant thing of y some function only depends on y， but not the next。And in this case。

We actually have。被过了几被过了几天。So we can check。嗯。If app has this form。If you plug it in here。

Then this term may be exactly equal to P of x to y， which you know is the optimal。

Parariation is sufficient。O。Now comes the actual hot pot。嗯。Now first。I want to。Rewrite this slightly。

What we can do here， you can replace f of x cube y by log of E to the f of x cube y and then put this together。

So this is then two expectation of God。唔系。And then if we write out seeing of why again。

 just the definition。He get。你事啊。Provided by expectation of what's called TX prime。你有系。

So this is just a different rate to write this。And this snow。Looks。

Orfully similar to the estimate that we'll see at the end。So。Again， basically。你 push。

X and Y together the representation here of the numerator and we push the representation of all the other P。

How with the denominator。So the question is， how do we。Compfuseute this。

We could say we just replace this inner expectation by some。Empirical mean。

So we just sample the batch of data and compute this year over the batch。

And this is actually exactly what we'll do at the end。But the problem is。诶。

If you can't just replace it and hope that the inequality is still award。啊落雨攞就。

This a lot actually sorry。So but just keep this formulation in mind for now。

 so it is a different way to write the EDA。对。But， let's go back to this from。

So here we have the expectation of this log potential function。

And this is very difficult to estimate if you want to take in decent breakfast。

Because if you want to estimate with some kind of Monte Carlo estimation， we first。Needs to draw。嗯。X？

To compute the inner， to approximate the inner。Expectation。

 then apply a lock and then draw from P of line to get the。Outer expectation。

 So we cannot couldn't throw them together and just do multiro estimation。So。What we will use now is。

The simple cleanality。Which is the following。Loock of V of Y is always less than。

D the poem minus one。但。唔知话怖。And。第一个呢份工诶。次の場合完すじいい。So ifs your advice comes even。

Now of course it's equal， then you have one on left side and log of E is1， so it's equal。

And to see that this inequality actually holds。You can just imagine， like the。The graph of。L X。

So the graph log X looks kind of like this and it's concave。And。Lock off。一， of course。

There's exactly one。And then， if you imagine the。The line。Of the form E X。Its also。Now。

 you one you if the power -1。Time six。Which cuts the lower rhythm exactly at this point。

 and because of cost the lower rhythm， it's concave。The line will always be above it。

 so this wipe this points。So we can use。This approximation。那个点。And we get our next estimate。So yeah。

U the layer of X， Y。 And then if we plug in this estimate， we get。です。And this is called the。And。WJ。

Estimate。From。Gran Wayne right。For rain right。And这种。ow嗯。

This estimate has the advantage that we could actually compute this just by Monte carlo estimation。

 so just sample a bunch of Px and P of Y， but independently。

And then just compute the mean of the power F X and y。X and y。So。Yeah。Again。

 a lower amount or a lower amount， which is a lower amount not a lower amount。But the question again。

 can we achieve quality， yes？So the optimal critical here has performed。That''s why。一个书。1 plus。No。P我。

X， student Y。MP呃 divideP。So in this case。You can easily check if you integrate this。

 basically that Z of y is constant E。In this case， we have both here。

 and then this is equal to there。UBA and。Everything works out。好。And。In this case。

 it's equal to the actual news information。So we have another nice estimate， the problem is。That。

This term here has a very high。😊，VSo you would need to sample very many X and Y to actually get a proper estimate of this term。

Now， we introduce。能着サです。So， let's say。That。You define x1 as just x so we does three times basically。

And but we also introduce。Basically copies of x2 X here。 and they all。And distributed。

By the same distribution of PO X。And。X 1， X， I is supposed to be independent。Of why。拖I。该成 two。

So the idea at the end is that x1 and y are representations of this that come from a same。

And X to escape a representation of completely different images。😊，So these are independent white。

So then the fu formation of x1。吃。K and Y， so I'm。Right， this basically is the。Joing to X one。XK。

Its just equal to the new information of x。1 and y， because x2 to X K are independent of y。

Now we can block this whole thing into our NWJ estimator。And you get the fuller。So this， of course。

 is the N W estimate of the works here， of course。And if we write this out。And the optimal estimator。

 of course。各强区啲。Then， as the form。飞很乖。So here， the critic takes x different K different x values in the1 y value。

And the optimal critic has exactly the same form as spare is the same as theator。So。1ラス。然后。外见。X1，2。

 x K provided by。きよ。喂。But。By our assumption， x2 to X K are independent of y。

 So this is really just equal to。1 plus lock。疲劳。Thanks one。有人。P why。 So why。

Did we introduce x2 to XK anyway？嗯。So， of course， the。Optimum solution cannot depend on x2 to xk。

Because as is。See in the optimal case， you already in cheap quantity。

The only thing that X2 takes can swift is reducing this variance from a part。Okay。

 so now we know the optimal estimator must have some kind and must have dys formula。

It was's all so bad that our estimator now needs to take consider just two values。

 x and Y needs to take an arbitrary number of values。So we。Reri。Our estimator our critics。

Using a simpler project。So we want our printing。这 takes。K of X values。And be write it。

Ising a syn critic。That only takes。出给。And we'll do it like so， we'll just say。Apple x1 to k。

 and y is equal to。1 plus。L each to the power。Aol x1 and y divided by Z hat。好怀。可。

And the head here is the water color estimate of not part。So we had。哦。Thanks。关 two x k。HSC。Average。

合法第要。X i。And dry。Okay。Now， why does this house？Now。We can。

Pluck this formulation here into our NWJ estimator。So our and。啊。So， we have the。

Explicationation will not about just。1 x1， but x12 x。HY。好 F for。X1。就 pay and why。

Minus equal to the minus1。offff。How Z of y So what I write。X one。The XK of。黑车他。And now， we plug in。

This mess we a got this。You wrote F of x1 days K and Y。And then is that a different path there？Yes。

你那话是Yeah， yes。I thought about giving them different letters but。Yes， yes， they different functions。

So we have our function takes k different x values and our function only takes two different one different x values。

Okay。Now weve plug this all in。And unfortunately， I'm a little bit slow andm afraid， so。I were。

Skip the。Skip to the end。 Maybe I write the。And I mean， it steps。In the slides， let's see。

But what you will get？Have you hand。Is this。是否。The expectation of。过れで过来东し。P of。右にもせとせ分。P of y。

 we have an x1， So Y and X1 are connected。 The other Xs I independent。And here we have。The lock。好，第一。

F times F of x1 and y。Divided by our does Z head there？But。All right， out。1 over， the sum of。です。

你这个 power啊。F of X， I and y。 So here's X minus and y。 Here's X I and y。

And this is now almost our NCE estimate。嗯。Okay。So this is a special case of our MWJ estimate。😊。

So instead of saying we allow any function of this form。

 he saying we only allow functions that have this form。So this is still a lower bound。For嗯。

The mis formation。But can reach equality。And this time the answer is actually you no。So。

If you see e to the power Fx1 and y appears both in the numerator and in the de numerator。

So this whole thing here。It's always。蓝色一个厨房。And then if we write a K other around。

 this means the whole thing is always。Less than look k。And of course。

 the new information of x and Y can be much higher than loque。

So if we assume that representation of some images。Share， I know， have some。

500 bits of representation。Information and features interested in。If our K， which we are bestized。

 is slower than 500。You can't possibly actually estimate the most information。So what we've done。

 basically。We have reduced the variances。Of this term， but introduced the bias。

So if the case is too low， we can't possibly actually get a tight bulk。So and this now， like I said。

 all of the NCE loss。The only thing what you need to do is introduce。Instead of just one wife。

 merge my wife。So for now we basically had x1 and y， which are pair basically， so not independent。

And then， x2。テシ？And so what。嗯。But now， basically introduce。Y 2， y3 and so on。 So that x， Y y。

One are not independent， but x1 or the other ones are independent。

 and x2 and y 2 are not independent， but x2 and all the other ones that are independent。And。

Then the right is all。And to get our。N C， E， noise contrastive estimation。And this is equal。

The expected value of what is。One over case。Each of the power F X I。And why I？Divided by。でさ。系。

So here in the top， we have X I and Yi， and the bottom we have X I and Yj。And this is the N S image。

And。The thing is， if。K。Goes to infinity。I didn't say how the distributed itself。X。弯唔乖弯。读X。K and Y A。

 they all supposed to be II。From this care distribution。嗯。

This ecology actually doesn't work anymore if they are not independent but some formula not。嗯。

So if K goes to infinity。This party actually。It becomes a better and better estimator to our position function。

 right， to the expected value of this。So as Kate goes to infinity。

This actually becomes equal to the unnmalized。BA estimator。So it's not there anymore， but4。

Uooby A Manta wrote down two different formulations。In this case， it becomes unbiased。

 so the bias goes down as K goes up。So。You definitely need to know， basically。

This combination is from the slides。And you need to know that。Yes K goes to infinity。

 just becomes some。This becomes the UA estimate。So in the original proofs。

 they basically just replaced this with the expected value and said this is equal to NC but this is not actually true。

O。I think this was enough map for now and probably。For the whole semester。So。

Let's do some practical applications。系嗯。Try to write down。

Some of the toolss that I couldn't maybe do here or I to the sauce。

I'd say you definitely don't need to know。Eavi care off the proof for the。But。At least some， maybe。

Those are right down nice圾。刚。So there's an overview of the stuff we just talked about。

IMaybe add some more stuffs。诶。八蕉。St， I think， know the proof of this bound when you just dropped the hair diversions。

And。好。啊就使得噶。今わってまさい。So now we need to go to Sslam。Which。Was like the first。歌词。

Use of this contestor list for station and images。They were not the first that I've done this。

But the first that have done in a somewhat nice way。So before I tell you exactly how they did it。Yes。

 Sanraft got the performance compared to other methods。

We to one accuracy onshed back the classical evaluation for representation and images。

And he about us and they in we sinceized better than all。Almost as good as a tiny supervised money。

And some of them here like Moco actually also uses contrastive learning。

 but it do in a complicated way。Which actually is in cicus。Next week you will learn about the。

Succesors of mobile。All right。Here， we have the。Basic pipeline哦。Since your last。

 as I talked about at the beginning， we take one image X。We applied two transformations to get X， I。

 X J。We apply some representations。And then we're just not a little different than we talked about before。

We apply some other function Z， we call projectionnet to get Z。

And then we formulate our Los like where。The is。Im to assume the close until。

So this looks now very similar to info and C， so let's make some comparison here。

They call it empty extent in the paper， but nobody calls it again after that， I think。

 so temperature normal。说30比我太大。And basically， if we see zm of Z Y and J divided by tau。

This is our critic。So they restrict the critic here further。Instead of saying。

We use any function of our ver， so the representation that actually want to use at the end are called H。

 H， Y，H。Instead of saying， basically。The critic is any function。

 they say the critic is the cosine product of those projections。So， so they're basically restricted。

What they could can do further。And this is then basically equal to NCE。

 just the lock2 and is missing。So。This would be here though。Luring yes。So in this one。

 they don't on on the the bottom we a case not even is that also。No，No， no，'s actually not。So。

Proction important points。我会死。小兵第一。NCE theory。We have。Our X。X1 to xk and y1 put Y k。And in theory。

 there can be completely different things。 So X could representation of images and Y1 could representation of text。

 which we will actually learn about later in。A lecture， this then will be called。

I look at the section later in the semester wish that would be called。And。And the Noss。

 they only compute。我 the心。Of e of x i。And。Y Z， so they only the take X and y 1 x。1 and y2。

 x1 and y3 and so on。Now in Sap Park。Both X and Y。Representations of images。So， they basically have。

玩你们。これ。Let N images in this case， end images。And each image。Leads to two representations。佢食过去啊。

H1 at H2 and the next under the H 3 and H 4 and at the end we H n -1。And HM。

And instead of only doing。嗯。The contrast between H1 and H2 and H1， H4 and H1 and H6。

 which is the uneven in ones。Theyve。Do the contrast to all of them。So they also do between H1 and H3。

咁个 case先。But they don't want between H1 and H1 itself。So why this actually changes some things。

Because。嗯。H5， H3， of course， are not independent。😡，Because they have' the same image。

So this is not actually exactly in fluency， but again， just another representation。

And you can actually show that， unfortunately， for some special cases。😊，If you don't exactly like it。

 it's neither a lower nor upper bound for use information。But it still works。

So if you wanted to do product that。给自己。You only。Basically。Prouce F。哦。HI and H。

 where I is even and by J is odd but never two even one together， so then there's all proper NC。

 but they don't do this。If they would do this then would have the correct NCE。

 but then they would effectively only have like half the batch size then。坏了。

So let's quickly go over the algorithm。Like for line。It's not actually very long。So。

 we have for input。F which is our representation function。So that's what we actually want。为什报片忘出这了。

Then we have G， which our projection has。Which you basically use。猪。Comp are critical。

And then we've got a set of transformations we talk about in a second。C터차は thank goodです。

We get our end different images。For each image， we compute two transformations。Exter the。

But an even oddt index and external even index。And then we compute do the representation what we actually want。

 and then you project。And then the coine similarity between projections will be our critic。Okay。

 then for every pair， they compute the credit， so basically they compute the fourth call before F of x。

Y and Yj。P this on this loss and take the average advantage it。Then they return F and4 away G。

 so the projection hat in the theory is only used。To estimate。The mutual formation。

Which extend use to maximize image information。So the project is only like an auxiliary network。

Which don't actually care about at end。It's kind of like in a variation of what encoder。

 if you want to use it for agenrative。To a gendererative models。You only care about the。

Decoder at the end and not about the encode it justin means to actually train the encoder。

And this is。The same way here。So they don't quite see it this way in the paper。

This is basically just to help。Estimate mutual information。

And this is to maximize emission information。O。What kind of images？

Do they actually use their work kind of quos？They tested， I think， six different types or so。

We have an tendon crop and resize， just crop some square or rectangle and resize it to the original image。

We have quoation which is used already in the past。Cut out a relatively self explanatory， I think。

Then propertyper size and flip。靠着啥声音。Of course noise， a little bit blurry， or not blurry， but like。

Noise， washing blur， so just taking basically the average of my neighboring pixels。

Probably can't you see a difference on the email。嗯。Kind of distortion and yeah so。

Do you know sober fish。It's basically applying a specific kind of convolutional printer。

 like a handcraft， a convolution of printer， to detect edges。

 which like was popular back in the state when you had to do manual feature extraction。嗯。把 theOE。

A that they actually used is crop， car dissort and caution blur。Because they work the best。

 so on the exercise this week well also play off different augments to see which work and which don't。

They did a big ablation study。With all combinations of。多刚开始。So， basically。

They applied two different types of corporations。And。

Took every possible combination and the evaluate the train network on within your programminging on I chat。

So in the diagonal， they only use one type of o， so they only use crop， he didnt only use cut。喂小红。

And we quickly see that some of them are much better。And大。

Especially the crop seems to be very useful。So the combination of crop and color， especially。呃。Yes诶系。

Resside at the end。So our color and drop。This is just a difference if I did drop before of color before。

 so I don't know。Might is actually different。我老。And some of us don't work like。Loft blowers of good。

 not mey enough。He needs， especially sometimes gring。

So in one of the ways that they saw that especially。Color I drop is important that is some color。

So you see here crop is good， but the biggest jam is basically it can do crop and color。cro with开了。

Does't work so， so it's the biggest takeaway of the augmentations。So there are some color astograms。

 they took a color density for each pixel and put it in a histogram。So we have。For things here。

We have two different images。The top row corresponds to one image。

 the bottom row corresponds to another image。And how we want to read this is。

These are the color histograms of different cutouts， of different crops of the same image。

And we see they' all very similar。So if you corrupt the image at different places。

The color in theogram will basically stay the same。And this is true for most images。Of course。

If you do a crop， they only crop like the cooking grassier you will at the different color asorum。

 but on average the color asum tends to stay the same。

And there's a lot of easily learnable information in this color。

 so our representation network will only basically learn this color information。😊。

So we destroy it with color po and then the。Con answer firms are not the same anymore。

So it basically term something called shortcut learning when network just learns some easy way。

That two images are the same， but of course we don't want to just learn entire equipment。

 we can compute this ourselves。So that's why collegesort is especially。Important。

 it was a lot of unwanted information cut on the throw away。What else。Yes。What底说不服。Our info4 NC loss。

To be good these two things， you can express a critic。

So this only works if our credit here can emulate， mimic any function。And we need a large batch size。

Because otherwise， like I said， our estimate is highly biased。So they do exactly both these things。

 they use a large batch size and they use a large projection as。

 which then correspond come to an expressive protein。

So here there is a lot of the patient studies about different batch size and the X that different training epochs。

 we see that longer are learning ourselves on Y Xs are。On the one hand。

 just have the top one accuracy and the color in the bars indicates the batch size from the left to right。

So the smallerest batch size that charge is 25 physics。which is already not so small。

 but they see that we really need at least the batch size of 1024 when drain on INe。To do any。せ。

And this is with compressive learning generally a big challenge to get like trying with high enough batch size to overcome。

This bias。And there are some ways to do with this that can use like exponential moving average。

Which you will learn about next week。But for now it's you know， contrast it's a high edge size。

They also did some major studies about the projection hat。Which mimics our criticlia。

They check just the linear layer， nonlinear network， so M few with the significant layer and。

No projection I basically just the and similarity。This corresponds here to something where F has no lo will parameters it。

嗯。And it turns out if we had a nonlinear project， so MQ with in layer。With a large。

Dimension at the end， then we get good platforms。Because this corresponds。To a expressive。Crittic。

 so we get a good estimate of the mutual information。And that's basically。

 so that's the take away here is that contrast of flowing maximize motion innovation approximately enough。

 and then you could talk about if there's even a good idea to。Maximize speech information。

 there are some people that say no not really， but there's no topic altogether。

But to actually train it， you need the right quos with large batch size and a somewhat large nuch。呃。

国展实战。And let's get part week。
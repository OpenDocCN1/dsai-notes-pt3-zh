# CMU《生成式AI｜10-423 generative ai 2024》中英字幕 - P29：-P29-Lecture 25-.zh_en - GPT中英字幕课程资源 - BV1CyC9BPEhG

And。Okay， hello everyone， yeah， let's start today's slide and first of all。

 I mean I need to apologize I didn't have too much time to prepare for this lecture because I was working on some for that。

😊，Meing， you probably heard that La my3 release right from last week。

 there will be a better model release tomorrow。😊，O。So， anyway。呃。That's， that's the story。 And also。

 I mean， because I didn't prepare very much for today's lecture in Wednesday。

 we will have another special lecture。 Okay， and this time， there will be no announcement， so。😊。

You guys come here every lecture。 I guess that's a bonus for once they lecture。

 just don't tell the people who didn't come， right， This time， they will miss it。

 And once the lecture will be really special。 I think the lecture itself probably worth couple million dollars。

 But anyway。😊，Right， you will learn what the Wednesday lecture。

 We have been prepared for the entire semester semester for learning the Wednesday lecture， right。

 we will be talking about。😊，The yflow of all day I hate。But anyway。

 let's start today's lecture and don't tell other people they。

 they don't come to lecture and they miss it。 I mean， that they deserve it， right。😊，Okay。

 so today's lecture we will talk about the state space model。Okay， and what is state space model。

 Well， state space model is the series of work by Albert Gu from here。 Okay， so you know， I。

 I did an interview for Albert Gu when he was applying for CM MU。

 I was actually the one objecting him。😊，Don't tell him， right， Okay， But at that time。

 I I thought this state space model washi， although the recommendation letter from like Per Liang says this is a new transformer。

 and I， I look at the recommendation letter。 Okay， it's from Stanford。 You know。

 the recommendation letter from Stanford and Berkeley。

 You need to read it differently because the letter will say everyone is the next goals。 right。

 Its so smart。 Its the next。 That's basically the average of a person coming out of Stanford and Berkeley。

 That's how they write the recommendation letter。 And I see， okay， it' the next transformer。 I look。

 I look at the citation of the paper。 I see 10 citations at that time。😊，Okay， at that time。

 transformer already have like N K citation。 and I think。😊，I mean。That's just exaggeration。

 But now I look it back。 I'm glad that there are someone smarter in the decision community that actually to him。

 because the state space model is actually pretty useful these days。😊，Okay。

And what is state space model。 Well， state space model is kind of a model that are similar to recurring neural network。

 And1 of all， I if to apologize I only check the paper this morning。 Okay， so it only。

 I only prepare this lecture for 10 minutes。 So let's see how how good I can go with。

 with those things。Okay， but anyway， space space model is kind of an upgrade version of the original recurrent neural network before the transformer architecture。

 Oh thanks， before the transformer architecture， I mean， most of the people。

Use recovery and neural network for processing natural language。Okay。

 so what is a recurren neural network， I mean， ideal do or just to say the most simple way of thinking about recur neural network is really you have a state。

Okay， and wherever you have an input or you have a sequence of input here。



![](img/92b5331b966f21943acecf543713d871_1.png)

![](img/92b5331b966f21943acecf543713d871_2.png)

And you will just keep updating the state based on the sequence of input。😡。



![](img/92b5331b966f21943acecf543713d871_4.png)

So it's almost like how human brain works， right， You are hurt。

 You are looking at the word one by one and your brain is some state and you're actually updating the state one at a time。



![](img/92b5331b966f21943acecf543713d871_6.png)

ok。

![](img/92b5331b966f21943acecf543713d871_8.png)

And anyway， so this is kind of like the over， I mean， this is the original recovery neural network。



![](img/92b5331b966f21943acecf543713d871_10.png)

![](img/92b5331b966f21943acecf543713d871_11.png)

And it was used to process natural language because it's a very natural architecture to process language。

😊，ok。😊，But what is the kind of bad about this recurrent neural network or why do people abandon the recurrent neural network。

 Well， the first is the rerent neural network is kind of like a sequential step。



![](img/92b5331b966f21943acecf543713d871_13.png)

![](img/92b5331b966f21943acecf543713d871_14.png)

![](img/92b5331b966f21943acecf543713d871_15.png)

Right， it's very sequential。

![](img/92b5331b966f21943acecf543713d871_17.png)

So things of this sequential is not really compatible with the current or with the new generation of the GPUs because they prefer parallel。

 I mean， think about about transformer， right， The transformer is just have a self attention layer and all those MP layers。



![](img/92b5331b966f21943acecf543713d871_19.png)

Or all those MOE layers。

![](img/92b5331b966f21943acecf543713d871_21.png)

Okay， even this attention， maybe it's like sliding window attention。 Okay， so it's also local。

So for transformer architecture， the real benefit is， is very parallel。

 everything can be computed in parallel and the computation speed is very fast。

 especially those M O E layer， if you use expert parallelization。😊。



![](img/92b5331b966f21943acecf543713d871_23.png)

Okay， but for recovery neural network， it's kind of hard to make it parallel because the state is really updating just one at a time。



![](img/92b5331b966f21943acecf543713d871_25.png)

![](img/92b5331b966f21943acecf543713d871_26.png)

ok。Any questions？

![](img/92b5331b966f21943acecf543713d871_28.png)

So basically now what is， I mean， the R architecture is not very good because it's just fully sequential。

 I mean， right now， there are some new ways to make R NN more efficient by using the pipeline parallelization。

 right this， you can view it as a pipeline， but the depth is really deep。 Maybe there's 10 K layers。

 But if you have a large enough PO cluster， You can actually pipeline the R and actually make it efficient。

 But that's a different story。😊，Okay， so original R is just lack of parallelization。

 That's one problem。 And the second problem is the R lack of longer term memory。

Right it's its just updating the state one at a time。 And there's nothing for， for example。

 this token here， it want to go back to look for what's happening here。 For example。

 this token is like a question that asking about some particular account that happened very。

 very long ago。Okay， and if you look at， look at it， if you process the data this way。

 and if you encounter a question here。There's no way for this question to look back to search for the answer。

Right， and that is the advantage of transformer architecture。

 for transformer architecture where you see this question token， Theres a self of attention。

 this question could just attend to this token and immediately find out the answer。😊。

Right so the kind of the drawback is basically lack of paralyization and also lack of longter memory。

 I mean， you may think there's LSTM。 There's long short term memory。

 but it doesn't solve the issue because the R and N， is like this。 I mean。

 it's like this sequential architecture that goes forward。 Well for actual N LP。

 you need some mechanism to go backward， which is what attention is doing， right。

 when you see this query thing。 you really want to go backward and search for the answer。

 You cannot really prepare for everything。 You cannot do forward and prepare for everything because you don't know what this question is going to ask。

😊，Right if you read the entire paper。You cannot really memorize the entire paper。😡。

But if you have some way to go back， I mean， when you see this question。

 you can actually go back to some screen search and find the relevant content in the paper。

 and then you can extract the answer pretty easily。😊，ok。Any questions？So there are some drawbacks。

 or there are some very glaring weakness of R N。 And that's why people kind of abandon it at some time。

 But now， somehow with the creation of state space model， this R structure seems to be revived。

 again。 okay， and I'm not sure why it's revived， I mean。

 I'm trying to figure that out by giving this lecture。 Okay， so when I'm talking。

 I'm also trying to figure out why this thing is useful。😊。



![](img/92b5331b966f21943acecf543713d871_30.png)

![](img/92b5331b966f21943acecf543713d871_31.png)

Okay， so let's try to lu it together。😡，But anyway， what is the architecture of a state space model。

 Well， it's just a combination of something like R with something like a transformer。 Okay。

 so we see that transformer has this sound potential layer。😊，He。

 that is a global layer and then there's this MOE layer or MOP layer。😊。

Those are local layers that apply to each individual token。

And this is transformer and to go to state space model。😊。

Didy I actually just replace this attention layer by something R like。😊。

And then still apply this local operation， which is MO E on top of it。Okay。

 so it's quite that simple modification。I mean， you just have those tokens and you actually use those R Ns to compute the representation。

He something like already。And then you UC MOE here。Okay， any places？So this is basically the portal。

 of course， you can use MOP inside of MOE。 I mean， MOE here some more general notation。

 But the prototype just looks like this。😊，And so instead of computing the attention。

With the self attention layer。They actually compute their attention with an RN architecture or with a state space model。

O， our space space model is actually a simplified R。 iss a something called linear R。😊，Okay。

Any questions。 So it's really， really like just a naive combination of R and MO E and。😊。

You cant understand my point when I was interviewing our school， right。

 This architecture just looked like somebody really loves R N。 Like， you know， the Stanford people。

 right， they really love R N because they created it。 They really just want to make our work。

 And anyway， I mean， they one trade pony。 So they just use R anyway。

 And they want to use it in transformer。 And that's how they create this architecture。

 It really just look like this way。😊，And but there are some tricks that they actually do recently。

 which make this architecture really powerful， okay？😊。

But this is the original kind of origin of the state space model。 Just look like this。Okay， so you。

 you'll just replace yourself attention with our。 Don't ask me why。 I mean。

 they just do it and show some numbers。😊，ok。Any questions？Yes。😊。

R language model also have a linear and a soft next to predict which word comes next Yeah this seems all of right inside here you have some MLP layer or whatever inside this processing unit。

But this is one layer for state space model， just like one transformer block， and you concatenate it。

Okay， so that's how you can get an entire state space model。 This is like a state space model block。

 and you can like 1 hundred of these blocks。 and you get a hundred layer stay space transformer。😊。

Just like the original transformer block， The only differences inside of self attention。

 you have an RN here。😊，Okay， so what is this R N， Well， this R N is really the。

The simple as the R as possible is a linearized R N with some discretization。 Okay。

 I just directly it across this picture from the paper。 and let's try to read it。😊，Okay。

 so you have the X T， which is your input， a sequence of X T。

 which is your input and a sequence of Y T， which is your output。😊，Okay， so this is IT。This is yy。

Okay， so how are the X T and Y T computed， Well it's just through a linear process is the most basic process as possible。

 So basically you maintain this H T， which is a hidden state。 Okay。

 and H T is going to be updated based on X T and Y T。😊，Okay， so according to this formula。

 this is the， I mean， the left hand side formula is a continuous time formula。

 but we really look at the kind of the middle formula， which is the discrete time formula。ok。

And you'll see this thing called zero older hold， which is a buzzword。

 But what does the zero older hold mean， It just means this。

A bar is kind of like a contization of the continuous formula。ok。So I mean， think about。

 you have an O D E on the left hand side on on the most left hand side， right。

 And you want to disretize it to a discretized update process。

 And what's the A bar and B bar that you want to use to simulate the continuous process。Well。

 the optimal A bar and B bar is actually given by this formula。

 It's kind of like think about the formula。 There's a times H。 The derivative of H is a times H。

 right， So the H involve like an exponential function。 And that's why there's an exponential here。😊。

Okay， so think about where you have。 I mean， we you have H。

 you remember people H is equal to a times H。Right， what's the solution to this O D E。

 The solution to this O D H T is equal to something like or H T plus Y is equal to exponential。

on HT is equal to exponential of A。which means Ht plus one is equal to。😊，E times A times HE。Okay。

 theres this exponential of a here。 So there is this exponential of deta a here。

 And Dlta a is some like time scaling factor。😊，Okay。

 so you use the discretization to discreetize the original state space model the continuous time1 into this discrete time1。

😊，Okay， that's the formula you willll get from the middle， which is just a deretization。

And then on the right hand side， you discuss a more fancy way to write the formula。



![](img/92b5331b966f21943acecf543713d871_33.png)

ok。So let's just look at the update formula and we try to unroll it。So， we have。I mean。

 I don't know the formula so I need to copy。H T is equal to a bar times H T minus-1 plus。

Be bar ham side steep。Okay， and Y P is equal to C times X0。Okay， so what's。

 what does this formula or what does this thistization formula give us。 So let's first look at y 1。

 This is equal to sorry， C times H E， C times H1， which is equal to C times。A bar comes HDO。

 which doesn't exist。H Sp bar comes x1。Right， and then what is Y 2， This is equal to C times H2。

 which is equal to。试探。A bar times H1 plus B bar times x2。

 which is equal to C times B bar times x2 plus C times a bar H1。Okay， and what is H1。

 H Y is equal to a bar times the H deal， which doesn't exist plus B bar times x2 x1。

 So there's the P bar times x1 here。😊，O， so以 C YY is equal to C times B bar times x1 Y2 is equal to C times B bar times x2 times C times a bar times B bar times x1。

 And this actually we can get the general formula， which is Y T is equal to C bar C times B bar。😊。

I see。Plus c times a bar C bar。X t minus1 plus c times a bar square B bar X P minus2。系。ok。

So if you write this same as a vector， so if you write C times B bar， C times a bar v bar。

 C times a bar square B bar， everything as a vector， then you really get。As this vector K bar。

 So you really get y is equal to x convol with K bar。Okay。Because you see。

 this is like a convolution operation。 You look at the first index of K bar con with the last index of x。

 Second index of K bar con with the second last index of x。😊。

And the third index of K bar can work with， I mean， multiply with the third last index of X， right。

 That's a coalvol operator because the index here and the index here， the sum is a constant。Okay。

 any questions。北库。So basically， this is a state based model。

 this is what's inside this RN I see original version。😊，ok。And to ask me。

 what is good about this model， I would tell you there's nothing good about this model。

 beside this R N。 Okay， so besides this will make those old men happy because it trigger their memory。

 There's really nothing good about this model。😊，Hey， I mean， that is the truth。

 Once you talk to those old professor， you know what I mean。系い。😊。

But there's really nothing input about this model at the moment。 The computation speed is terrible。

 right， You have to keep squaring a square matrix。😊，Okay， so the computation speed is really bad。

 And also， the R N doesn't really have the advantage of transformer。

 which is you can look back and try to search your answer from the previous content。😊，诶。😊。

So how do we actually try to make this thing work， right because your advisor is really an RN guy and you have no choice to try to make this thing work。

He， that that is usually what would happen。 and you try hard to make this thing work。Okay。

 so now let's， let's put ourselves in that situation。 So we start at this formula。

We want to try hard to make it work。😡，So first thing we need to solve is a computation issue。

 why this say is so slow。I mean， think about this thing for。Or if you use this type of formula。Right。

 so every time you need to compute a matrix times a vector and you need to compute a matrix times a vector and keep computing matrix times vector。

😊，Okay。😊， so maybe it's not that' slow， but anyway， we can make it faster。O。So basically。

 the first thing that people do to make it faster is really by the socalled diagonalization or the socalled。

 I mean， this is really just one state。 So usually you want to have like multiple state。

 So this is like one state where you just use X and you use the fix A bar and B bar。 But I mean。

 think about attention right， You have multi hide attention。

 You don have different key and query and value matrices。 So here， I mean。

 you also want to have that advantage， which you may have a set of state inside of one state。😊。

that will make the computation much， much slower if you want to upgrade to the multi head tension architecture。

😊，So one thing people are doing is really this egonolization trick。😡。

Or this is what people do in history all the time。 I mean， think about algorithm Adamom， right。

 Origin， you， you want to do this precondition gradient design。

 But this preconditioner is to kind of call to compute。 And what do you do， You diagonalize it。

 right， You just make it a diagonalize matrix， which is the Adam matrix。

 And then this thing inverse can be compute pretty easily。😊，ok。And here for state space model。

 people do the same thing， which is they actually just diagonalize it。

 So they change it to a diagonalized matrix like this。😊，O。

And then how do they do multihyide version of the state space model？

So this is their upgrade from Matji Hyat version of state space model while keeping the computation efficient。

😊，Okay， so basically think about your XT or your HT， which is a hidden state。😡，Okay。

 so now they look at each coordinateor of H。诶， they look at each coordinateordinator which is。

 they call it H咦。😊，嘿。And they are going to apply a different state space model per coordinate to make it like much higher。

Hey， any questions？He cool。 So how do they apply a different state based model per coordinate。Well。

 I mean， naively， we are just thinking， maybe we should just。I mean， apply some。

Apply some like simple linear function or apply some simple one dimension function on top of this thing。

😊，Okay， but people are actually doing it in kind of a more。I mean。A more。还 would say啊。

Pmeize away or something like that。 So the way that they do diagonalization is the following。

 so they parametermeize a to be a diagonal matrix。😊。

And they parameter or parameter a to be a diagonal matrix。 and they parametermetize B。

To be this one dimension matrix。诶 or。Yeah， this one dimension matrix。

Maybe I should write it in another way。 and that time me try C to be this one dimension matrix。睇。😊。

Then for each coordinate， instead of applying the。I mean， for one coordinate。

 I can still apply the original formula， which is。So。Does H teach？Hey， this is equal to， I mean。

Now I have this A bar。Which is， I would just。Okay， so I would just make it。sorryrry。没得晒た。Sorry。

 you see， I already made a mistake， like because I didn't prepare。Oh。

 this is now they do diagonalization or this this is now they do multi head。

 So what they do multi head is they look at the F T。😊，8ight。And they look at each of these X key。诶y。

😊，And they call this X of I of T channel。He， and then for each X of T。

 they apply the following operation， which is this H T， maybe I call it I， is equal to this AI。😊。

A bar of I of HT of I。last地板儿。As hikes。ok。So what does this formula mean。

 So this formula means So the X of T is one single coordinate， right。

 So the up project this X of T this one single coordinate to a vector。

So this thing is a single coordinate， and then they I project this thing into a vector。😊。

And then they're just updating this vector using this dynamic， which is called AI a bar of I。😊，Okay。

 so then they have those a biopha。😡，B of I， I mean， this B， I'm not sure it has B， I or not。

 I need to look at the later slice， because I forget。But anyway。

 let's just think about the B to be a projection vector and C to be another projection vector。😊，Okay。

 so then for each coordinate of the XI， you can apply a different state space process。😊。

Or different RM process。 So those X size， the Y I will be kind of the output of the Y I will be according to different rules。

嘿。😊，Any questions。So this is really the first hell of。😡。

Effort to incorporate the multi head structure into the state space model。

 because if you look at the original state space model， it doesn't have the multi head structure。

 Everything is just one single matrix， and one single dynamics。So they want to make this RN as good。

 as close to the transformer model as possible。😡，Right， so they need to， first of all。

 include the multi high thing and also improve the speed。 Okay。

 and the way they do it is really just by diagonalization。😊，So they look at， so basically， I mean。

 they look at each coordinate of the X of T and they treat it as like one key vector。

 or here is just one key value or one query value。 And for each X of T。

 I'm going to apply individual or for this channel dimension。

 I will apply individual space space model rule Okay。

 and then I will really get the final output for this X for this particular dimension using that particular rule。

😊，诶い。Any questions？So let's think about， I mean， this maybe this is still too abstract。

 but let's think about some concrete stuff。😡，诶。😊，So I say I want to implement something like rotary embedding or something like positional base attention。

 Right， So I want to make sure that this y。 So I want to make sure this is my X， right。

 This is the y。 So I want to make sure this coordinate of y is like the average of the past。😊。

and I want this part in white to be only look at recent stuff。ok。

So basically if you want to make sure that top coordinate y is like the average of the past and the lower coordinate Y is like the most recent stuff。

 how do you implement the dynamic of this？I mean， this state space model。Okay。

 so this thing is actually pretty easy to implement。 Maybe you can even leave H to be one dimension。

 So you just need to make sure that A here。😊，The a here is equal to one。 right。

 This a here is very small。Okay， so if the a here is equal to one， you see you keep powering this A。

 right， or maybe you need to make sure the a bar is equal to one。So you keep powering。

 you keep doing this A bar multiplied by this， right， You look at the convol。

 If the a bar is equal to one， you're just doing like an unweighted average of the past。Right。

 so you can implement something like this coordinate only look at the past by saying a bar is equal to one。

 And here the A bar is very small。 You can see if you keep doing powering of the A bar。

 then the A bar becomes very， very tiny。 right， So this same will only look at the reason stuff。😊。

Okay， so at least you can make sure that there are some coordinate that look at the past。

Or look at very deep in history and some codion。 look at very recent stuff。

 So there is some kind of position based structure that you can already implement with it。

 Some non homogeneous， right， So different codian may do different thing。

 This is an analogy of the rotary positional ecoding。😊。

 but this is really decent based inside of periodic base。😊，哎。😊，Any questions？A酷。

 so there this is the first update of state space model， which is。😊，Dagonalization plus。I mean。

 diagonalization， plus all those。I mean， applying different AI per coordinate。Hey。

 it's really just that look at this particular set of。I mean， this one coordinate。

 And then if you look at the time dimension， this becomes a vector。😊。

And then you use some convolution kernel cover wall with this vector。Right。

 and the co kernel is different per channel。That is exactly C。

 That's why they cannot want to view it as convolution。He， any questions？得酷。

So this is a diagonalization。 Okay， looks like their Bs are also different。Okay。

So the correct way to think about it is really looking at an above formula， right。

 There's the K or looking at this formula here。 There's a K， which is a convolution kernel。

 And for each different coordinate or for each different coordinate of X。

 you are actually convolving those X T and that coordinate with a different convolution kernel and get the output。

😊，So the correct way to view it is this is your input。Right， this is a time dimension。

 This is the inva dimension。 And you just look at it like this。

 And you apply different convolution kernel on each of those individual dimension。😊。

And you get the output。Yes。😊，F explain or does it apply like across the entirety of the it's not fixed that right。

 it's just defined by the K bar It is a infinite length or not really technically in。

 but almost infinite length convol kernel。嘿。Okay， and that's a parameter size convolution kernel。

 I mean， and that's probably also why you need diagonalization because you need less parameters than the time。

 where otherwise， it doesn't make sense。I mean， because the correlation kernel are parameters by a bar B bar C bar。

 you want the A bar B bar C bar they totally have in total have less parameters than time。

 and then that's a more succinct parameterization。 Otherwise。

 you would just rather parameter each coordinate by the different parameters。 So that's why， I mean。

 originally the A bar oupies a lot of parameters is。It's kind of like n by N matrix。

 And after diagonalization， it only has n parameter。

 So I s0 n is much smaller than T than you are parameter by the kernel more successfullyively。😊，Hey。

 any questions？Okay。Okay cool。 So that is one update。 And this is like the architecture ice work。

 which was the old state space model that didn't really work。 But it's already a very good update。

 It has a market ice factor in it。 So a pretty good update compared to the original R。

 at least now we can implement something like。😊，Some non homogeneous operation across different parties。

诶。😊，Any questions？But still， you can see that disadvantage of the state space model is that it's still not content based。

Pa the criminal the套 thermal it just like个。Eage evolution， those kernels are prescribed。Right。

Those colors are timeized， but they don't really depend on your input。 They are just fixed。

 They are C times a bar times B bar。 They are fixed。

 So youre just applying fixed convol or dimension here。 which is not really very ideal for language。

 maybe for image is one because for image， you are just detecting different objects。

 and those objects are fixed in your object dictionary。 But for language， So not really ideal。

 you want something counterdependent。Okay， and that is the final update。

 which is updating from the ice core， which is the original simple state space model here to the。

Mバ or the so called ice。So called State Space model plus selection or I6。Hey。😊，So let's forget on a6。

 Let's first look at this I4 to see if we agree that this is what I'm talking about because I am not very sure。

 Okay， so let's just check if this is what I'm talking about。

 So they have this A right A is an E by N matrix。😊，Okay， so a is a deep N matrix。 you may think。

 okay， this is already not what you learned， but this is this is what you learned。 Okay， so a。

 this is an n dimension right。😊，Okay， and this adds is in C dimension。😊，Okay， so for if carbonal ice。

You have n dimension vector。 So A is a D matrix， but you should think of this N as a diagonal of this a matrix of the in a matrix。

 But because that diagonal matrix， you can just parameter as a diagonal。

 So A becomes the total parameter of a is D。😊，哎。😊，Im for B B measure there there are different B so is also given I see measure there are d awesome so is given okay。

 and this type check。 I also have a and B and c and you have a dota， which is。

This linearization or time parameter。 okay， and then you can use the disitization formula to compute the A bar and B bar。

 and after that， apply the space space model on it。哎， so I'm actually hiding a step here。

 This is a bar B bar， right， So we this the formula of this de or0 whole deitization to compute a bar and B bar using the。

Hey， and let me check。 How is it computed by count the sees， The tall is D dimension。 Okay。

 so this probably implies for each of the AI you are actually multiply by this how。Okay， so multily。

 so a bar of I is equal to exponential。Of how of白 I a。老板了。Okay。

 and this is coordinate and AR is a diagonal matrix， so it's like coordinate by exponential。

 pretty easy to compute。Okay， and we can use the same formula for this B bar， Okay。

 which is how I times a bar universeverse， But because it's diagonal。

 it's also pretty easy to compute， okay。Any questions？Yes。

 so there are there is there a linearity between the HGs because otherwise would the whole thing not be linear the H。

I mean， those Hs are linear function of the Xt。They are all the y t的 output are linear function of X such convolution。

😊，Right， so there's really no non nonlinearality here。 It is a linear function。

 That's why it's linear state space model。😊，So what is。Yeah， I mean， the part。

 it is not the linear function in parameter space， but it's a linear function of the input。😊，Yeah。

 and the non nonlinear energy come from the MOE layer or transformer layer or whatever the MOP layer。

 whatever non nonlinear layer you have on top of it。 this is the state space layer。

 you should just think of it as a replacement of the original attention。😊，ok。😊，So we learned I 4。

 I mean， at least ice4 is what I we learned about， right， That's good。

 I made one mistake when talking about it。 but let's pretend that I didn't。😊，Okay。

 so we learned ice4， which is pretty good。 and okay， I also just learned ice4 now。😊，Okay。

 and now let's try to learn what I say by looking at this picture。

 which I'm trying to look at it now。 Okay， So， so I six this architecture seems pretty strange。

 right， You see the dimensions doesn't even match。😊。

It's not given the same dimension as the ice sport。 So let me try to explain what happened here。

 hopefully， because Im， I need to figure it out。Okay， so first of all。What's the， I mean。

 what's bad about I4， as I said， I for the coal thing you applied here。

 there's no context information right so you still cannot say maybe I have a word here which is questionian。

😡，的 question哎。Of blah， blah， blah， and I need to look for the corresponding content for the answer。

So I cannot really do it Ipo aspo the Covol has no contextual information。😊。

So the upgrade from S4 to x6， this really makes the convolution kernel context dependent。😊，Okay。

 so they want to instead of applying those context independent convolution kernel。

 they want to apply a context dependent convolution kernel。Okay。

 so that when we look at the entire sequence。 you kind of know， for example， there's a question here。

 Then there some of these conution kernels will actually pick this question up and really just only do convol to the corresponding thing that are corresponding to this question。

😊，so they want to change the col kernel from context independent to context dependent。

 which makes it almost like a self attention。诶。😊，So how do you do context dependent convol kernel。

 Well， let's just。W to do it now。诶。😊，So recall， I mean， in the ice4， right in the ice4。

There's this matrix， AI， which is a diagon matrix。And those one dimension vector B I。安走斯。

One dimension vector C。哦BI说B。哎。😊，And so， first of all， I mean。Need to look at it here。

So first of all， they are kind of updating the structure of B。 So originally， this BI is， I mean。

 this B is an n dimension vector for each of the I coordinate。😊，Right。

 and now they kind of ship it to those new B matrix and new C matrix。 So you can see those。😊。

New B matrix and new C matrix。 They are actually computed by this SB function。

 which is a linear projection function of X。😊。

![](img/92b5331b966f21943acecf543713d871_35.png)

So which means they are kind of updating this， at least updating the B matrix and the C matrix to be somewhat content dependent。

 Okay， and they keep the A matrix to be。The same。 So basically， the a matrix is kind of like， I mean。

 one way to think about this A matrix is like the loty embedding。

 which determines like the speed of the convolution。😊，Right。

 whether you look at average over history or you look at the adjacent one。

So a is kind of like the rotary embedding。While the B and C matrix。

 they are like the key and query matrix。诶。😊，Any questions？Yes，Iage just third by。I mean。

 because a bar and B bar is really some。 I mean， A bar and B bar exponential of something， right。

 which means a bar is always positive now negative。Okay。

 so this means on a bar and B bar are always all non negative。

So if you want to manually learn A bar B bar， you have to have the restriction。

 which is A bar B bar being non negative。He because if you， I mean， think about。

 you are applying a to the power of T。 if a is negative， then it doesn't make sense。

RightSo you need to have the restriction of non negativity， but once you have that。

 it's better you p a and apply some function on top of it to make it non negative。😊。

So you're don't really have to constrain on it directly。Hey， that's a very basic trick。

That people do， yes。A bar is exponential of a deelta。

 do we mean matrix exponential or like element wise exponential？I mean。

 in the original state space model， it is matrix exponential， but becomes you diagonalize a。

 so it's just element wise。😊，ok。😊，Any questions？So let me try to figure out what those formula mean。

 because that's also my first time looking at this formula。 Okay， so basically。

 they have the B matrix。😊，Okay， so they have the B matrix， which is batch size， times L， Hson。 okay。

 and this is this matrix on this new matrix， which is a content dependent B matrix。😊。

Or we shall call it必要 X。Okay， this matrix is just equal to， I mean， you have original x。😊。

The original x is P times L times n。Right， so youll just apply a linear function。好X。sorry， this is第。

So this linear functions。The input is D dimension的 output is n dimension。

 So you applied the linear function on this D dimension。 and you will actually get the B。😊，He。

 so we should。 I mean， we should forget about this batch I because it doesn't really matter。

 So we think of the apps。😊，As those input X1， x 2， a up to XL。😊，是。

And now you want to apply a linear function。You get the B matrix here。This is BT。B in minus-1。He。

 looks very familiar， right， Because when you compute key and query matrix。

 you are also doing the same thing， which is multiplying。

 which is go through a linear function and you get the key vector and query vector。😊。

And you see here， you do the same thing。 You use a linear function here。To get those B matrix。

 and you use another linear function to get the C matrix。

And so those are really just your equivalent of the key and matrix。😊，哎。😊，And that mean。

 you can see why I'm saying they really just want to make。Stay space model work。

 They are kind of just trying to replicatere the self attention。

 But in the language of a state space model。But it's going to be a little bit different at the end。

 as we will see。 But right now， this just look at key look like key and query matrix。😊。

And look at your key and query matrix， which are content dependent。

 They are just linear transformation of your original X。诶。😊，Any questions。爱酷。

And then you have the delta matrix， which is also。😊，I mean， the delta matrix。Which is also something。

 I mean， it's not exactly content dependent。 It's almost like a person。

 or it is still content dependent， but it's kind of like。I mean。

 something like a time variant factor。诶。😊，So， the delta matrix。Is he himself。

AndAnd this delta matrix is just a times variant scaling factor。

 which doesn't really sell that important。Okay， and what's more important now is how do they do decraittization？

😡，And you can see D and C are B times l times the matrix， and then they apply deittization。

 They just get a B times l times B times some matrix。 Okay， so how is this thing even done。😊，Okay。

 any questions？Okay， so first of all， I'm the following word that I said is probably not 100% correct because they didn't explain how this is done in their paper。

 So I need to just guess how this thing is done。 Okay， let me just try to。I mean， basically life 5。

 they didn't actually explain the paper。 Okay， I checked it。 There is no explanation。

 So we probably need to guess how this is done。 Okay， let's just try to do it。I mean。

 let's look at a discretization formula， which is this same。Let's just write it down here。Hey。

 and I mean。I'm trying to give you the 100% authentic experience of radio paper， right。

 Many times you have to guess what the author mean。😊，So let's just write the a bar here。

 which is equal to exponential of delta。 This is in the original formula。😊，A， and B bar。Is equal to。

啊。导体 inverse。Those have people。哎。😊，And now let's just try to apply it to line five。Okay。

 so the a matrix is B times1 and the delta matrix is B times l times B times 1。

 So it seems that it there's a possibility of applying it。

 So let's just ignore those B times L dimension。 or let's just ignore the batch dimension。 I mean。

 this batch dimension is really not that important。

 It's just the same rule apply to each individual batch。And this delta for each of the L and D。

 let's call it thelta I of T。😊，Okay， so I belong to G。And T belongs to L。嘿。

And I won't forget the A bar。I want to get the a bar matrix。Which is basically this diagonal matrix。

Okay， of each individual coordinate。 So a bar of I of T。This should be。And so this is in L。

 this I is in D。 So this should be an N by N matrix。诶。😊，So how is this a bar I of T computed。

 You can see from the formula， right， This is exponential of delta times A。 So if I applied deta I。

 which is this thing， sorry， I should use delta。 If I applied deta I of T to here。Okay。

 deta I of T is a value， and then times this original a。So times this original matrix。

 which is a of I。Okay， so I have deta I of P times AI。And then I go through exponential。He。

 this should give you an M by N matrix。ok。Any questions？So this istercraitization of a。😡，He。

 you can see they apply the time in。 I mean， the time scaling vector。

 which depend on the coordinate of x and depend on the time T arms A of I。

 which depends on the coordinate。 It's really just this matrix。 and then go through exponential。

 They give you by a matrix。 And this then depend on the。😊，Coordinated depends on the time。

so basically， there's the coordinate dimension， which is D and time dimension， which is hell。

 and then there's a batch dimension， which is B。😊，I mean， that doesn't matter。

 It just means you have different data。 Okay， so this is your disctization of a。😊。

So this is your discretization。 We， and you can apply the same rule for B。Right。

 so this B also depending on coordinate。 It also depend on time。 And then this A depend on time。

 depend on coordinate。Right， and this dolta depend on coordinate， depend on time。

 and this A depend on coordinate。 and this B depend on coordinate， depend on time。A or maybe yeah。

 be depend on time。诶。😊，嗯。Something didn't have check here because this thing is B。 This thing is N。

So be here。 There is no I here。Theres no eye hear。Sorry， there is a high here。嘿。😊，Anyway。

 this is a formula that I guess the discretization is using。 I need to。 I mean。

 we have to go to their Gi to check what's going inside the code to what this formula mean。

 But at least here it looks like it type check。 So you look you have the do。 I mean。

 this dota depend on I and depend on T。 right， you have deta I T times AI times exponential of dota I T times A and minus I。

 and then times dota of B T， Theres this B。 I mean。Is an n dimension vector or time。

 So this is an n dimension vector， right， and the entire thing。

 just give you like an n dimension vector， because this thing is a matrix。 This thing is a matrix。

 This is an n dimension vector。😊，And the entire thing， give your an dimension vector。诶。😊。

Any questions。很酷。So basically， we can write this new formula as the following。

 so the decraitization of a is equal to exponential of deta I T times AI。

 where this deta I T is basically the that。😊，Kind of new deta that is there。 Okay， and the B。

 I of T E is equal to this formula。He， this BT is basically what you get from here。Ok。Any questions。

太酷。So basically， we kind of have the formula after deization。

 and then we apply this state space model on this new A and new B。😊，Okay， so what does， I mean。

 what does it mean here well。Unfortunately， I don't think the paper explain。 what does this mean。

 Okay， compared to the original state space model， but。My guess is， essentially， you just replace。

The C and or the C here and a here and B here by something that depend on the time。Okay。

 or maybe we should go to the。Coordinate wise formula here。

We should go to the coordinate by formula here， and you see originally等于 depends on the coordinate。

 And now the new formula will make sure that it depends on time。

Maybe it depends So there should be a time here as H T minus-1。Of。A plus be bar of high of time。

 so basically inside of having like a time independent or just a constant convolution kernel here。

 they successfully parameterize a convolution kernel to depend on time。He。

 there is a time dimension here， and the time dimension is actually computed。 You see from。😊，A this啊。

From this formula here。😡，Okay， so the cloud dimension is really computed many based on this thing。

 which depends on the content here。哎 so depend on the content here。Okay。Any questions？S basically。

 I mean， what does it mean here， Let's just try to look at the formula。

 So each X I will be map to B I of T or each X I will be map to B， I， or each X T will be map to B T。

Okay， so the I C will be map to B T and then B T will be applied to there。 to this formula。

 which will actually multiply with Xie。😊，诶。So BT will actually multiply with X。

So this is what they call a selective process， which means the X C will create the socalled content vector。

 and they will use a content vector to select whether this X C will be used in the final Y T or not or in the hidden state or not。

 So this means when you see some X C， which is like a junk word or some very common word。

 Then they actually remove the X from this。 So the B T may be very tiny。

 and then they actually remove this X E from the update of the hidden space。😊，Okay。

 so it's like a select model， which is why they call it I 6。

 So the X C has some content information that X C will decide whether it is important to be a in the hidden state or not。

😊，Hey。😊，Any questions。So， I mean， let's just recap in some word that a normal user would understand。

Right， so in the original state space model， you're kind of doing。

Like a linear or you kind of think of it as you have some state where you just update using each X D。

 But the contribution of each X to the state doesn't really depend on X， I mean， or。看 of这。

The诶 I mean。How should I say it， The multily factor of how the X would contribute to the state doesn't depend on X。

 Okay， so basically， you see each word one by one， and you just add a word to your。

Ice H or to your hidden state， no matter what the world is。Okay。

 no matter the word is a very important word， or the world is just some random word。

 you kind of just brandly merge them into your hidden state。😡，Okay。

 so there is no like importance or whatever that you can or important factor or whatever you can choose to whether choose this to whether I keep this word in your hidden state or no。

He， and now， after upgrading to S 6。You kind of has this selection mechanism where you can actually choose how important this word is in the current content。

😊，Okay，And the choosing mechanism is kind of like a linear function。 Okay。

 that depending on your entire world。I think about it as a transformer。

 So this word may actually encode all the previous content already。

 So kind of using this embedding vector， which encode all the content before it to kind of decide how this particular word or the embedding of this particular word。

 how important it is to be kept in the hidden state。😊，哎。😊，Any questions？Yes。😊，啊。好会。

is that it is to just sort of fly people at。You mean computation time。

 it is quite efficient because the main computation time is really just computing those B Y B matrices and computing those C matrices。

😊，And I haven't really talked about that， but they have like a ka implementation。

 which put everything into the ice run to do faster computation。

 So they still do this for loop as the original recover neural network。 But because this diagonal。

 which means you can actually put each diagonal， just recall from the last lecture。

 you learned kuda can spa those different thread。😊，Right。

 you can put the computation of each coordinate to each block that has a shared memory。

 and you can put the B matrix into the ice Ram， and the computation is actually very， very fast。😊。

Okay， and the dimension of the B matrix， which is this N。Where is the嗯。So this， this end here。

 they are designed so that it can be put into the icerap。So basically， the L times then。

 they want this thing to be able to put into the H one， and then the computation is very， very fast。

😊，Hey， yes， it seems like this whole thing is just trying to。

Cooffpy attention inside the framework when aren'tt， so yes， that's what I mean。

 Is this like faster or it is faster。Okay， because you can see the computation time is linear。

 It's not quadratic， right， The state space model you just go one path and you compute the hidden state of everything。

 So it is like a linear。😊，Linear time attention。Hey， if you implement it correctly。

 which means you keep the eyes H inside the eyes， run。 So you cannot do it in my toch。😊。

Because if you're doing it in P， you know， you put it back to the V Ram and then fetch it from the V Ram again。

 That is very slow。 So they implement so that the H always stay in the ice Ramm。 So the hidden state。

 always stay in the ice Ram。😊，And then the computation is very， very fast。

 So all the updates of which stay inside， as run。😊，He，看着。😊，Basically。

 this is a linear time attention， Line in end。 Well for flash attention， you can make it linear。

 But if the contact size is very， very large and you don't do like。

Sing window attention is still not going to be linear。系。But for this thing， it's always linear。

 no matter how long the sequence size is。 So it's kind of a very good architecture for long sequence size。

 which is important for video。😊，Okay， so the man architecture is actually currently being by the adaptive video。

😊，Models where the contact science is very， very large。

And you can see the state space model has just a very large advantage where the computation time is linear。

 There's no self attention。 There's no n square self attention。 It's just you go through it one pass。

 and you compute everything。😊，诶。😊，爱酷。So basically， I mean。

 then why do I say that the original RNA is very slow。

 That's really because you cannot put everything in I run。 So if you put everything in V。

 write it in P， is going to be super slow。😊，He is's going to be non non tolerably slow。

 But if you put the edge in ice ramp， then the computation is very fast。😊，Hey， any other questions？

So， yeah， I think。I mean， it is correct that this is really just trying to reproduce attention in the。

 in the framework of a re neural network， But it still has an advantage。

 which is the state space model， the linear computation time。😊，Okay， and also。

 this model is actually better than an original transformer。

 Why is that Because the attention layer actually has very few parameters。😊，Okay。

 let's just think about how many parameters are there。Theres a， which is B timesson。

A and a is typically very small， so it just。And A is like， a very small matrix。Okay。

 and then there's this linear function here， which is still T板。😊，This is a one by D function。

 and then a one2 D function， whatever。 And all those parameters are like B by N。 So it's very tiny。

 N is very small。 A N is something you have to like all times then you have to feed in the S So N is very small。

😊，诶。😊，So it has very few parameters in the state space model。So think about original。Attention layer。

 it has一 square parameter。 here， you only have b times n parameter where n is very small K think about N being like32。

😊，诶。😊，So this means for a transform model with the same number of parameters。

 you can actually put more parameters in MOP or put more parameters in your MOE。😊，And， of course。

 MOP layers are more powerful in terms of memorization， What etc cetera。 Okay。

 and I saw this thing can do the same equivalent job as attention。

 Then you actually save a lot of parameters you can put in MOP。😊，Okay。

 so in terms of the model with the same number of parameters。

 member model usually perform better because it has more parameter in MOP。 He that's simply， I mean。

 that's simply how it works。😊，And also， in terms of the same computation time。

 member model is also better than the original model because it save a lot of computation time in the attention layer。

😊，Okay， it is even faster than flash attention。 If your sequence science is very low。And also。

 it almost looked like a transformer model。😡，And but the only thing that you cannot do at the moment is really the self attention。

 which is kind of like the exact look back。 I mean， the exact look back operation。

 But here you kind of can do somewhat can do the look back operation， because this X。

 if this is some intermediate layer， this X will encode all the content of previous stuff。😊，Hey。

 so maybe it just learns somehow these things。I mean。

 this coordinate is kind of like a look by coordinate of the same word。Hey。

 and then what would happen is。I mean。Think about this X， right。Or think about when you。I mean。Or。

How should I say it。啊。I mean， think about when you are had the X。 Okay， so basically。I mean。

 it cannot really do this look back operation yet， but at least it can say， okay。

 I have some keyword here。 I have some person's name or I have some special word here。

 then those special word will occupy more in my hidden space。 So I have an easier time to look up。

 So it's just like a summarization unit here where the content where this B can say I only pick up the keywords in my past in my past paragraph right is almost like a summarization unit。

 And then here it can try to look look for the keywords。😊，Okay。

 but you still lack of this exact lookup in attention。 But that's it is probably quadratic time。 Hey。

 you cannot do it in linear time anyway， So that in linear time。

 the best thing you can do is do some like keyword extraction or contact space attention。

 which is what the member director trying to do。 And that seems to be at least sufficient for most of the task in in practice。

😊，嘿。😊，And I think you look at this architecture。 There's a lot of room for improvement， right。

 For example， you want to add this exact look back， Okay。

 or you want to implement something like that。 I mean。

 that those are some upgrade that they actually already considered in the member architecture。

 And there is something like exact look back layer in the member architecture that I'm not going to cover。

 but it' going to make it more like。While grounded。哎。😊，Any questions。Yes。😊，Ass。

Doesn't seem to be sufficient。Right now， at least we didn't see anyone。 I mean。

 we tried the member architecture on the standard model using our standard training data set。

 And it does work better compared to transformer。😊，So across almost all tasks。

 but we really didn't test like very complicated tasks。

 Maybe there are some complicated multihob reasoning tasks where you still need self attention。

 But for most of the tasks， you really don't。Hey， it's just like think about state space model is almost like。

It's almost like， I mean， the listening hyper。Right， you， you are not allowed to replay。

It's just like， I mean， just think about human conversation， right。

 And I'm not going to tell you replay。I'm going to just talk to you like just in linear time， right。

 Singapore videos， especially You' are just watching it in linear time。 There's nothing like replay。

😊，So for those scenarios， which is most of the scenario， they say is's already very good。😊。

But there are some scenario where you need very large replay。

 Like you need to do multiho reasoning all those things。

 Maybe this architecture is still liking in certain scenario。

 But I think that this is a good thing to try。 Maybe you need to do alternative of member and flash attention。

 Something like that。 That would be a pretty good stuff to do。😊，Yes。😊。

Try to address some of the improvements that S6 makes。

 so how does that compare to this it's kind of similar I6 is like our IM version of the of the of the。

I mean， I sport。So， but the point is。I mean， the main contribution of I6 is not really the architecture。

 It's actually their infrra， which is a kuda kernel that makes this fast。😊，The in， I mean。

 this implementation， I don't think is very kind of creative or very intuitive or very inspiring。

 but it's all any infr。 I mean， this is the same author of flash attention。 So they implement a very。

 very good kernel to make it very fast。😊，诶。Any other questions？Hik cool。

 So I hope you learned something in the iceboard because I saw in Pi。 someone want to learn iceboard。

 So I just prepare the lecture this morning。😊，RightAnyway， and hey， I will see you this Wednesday。😊。


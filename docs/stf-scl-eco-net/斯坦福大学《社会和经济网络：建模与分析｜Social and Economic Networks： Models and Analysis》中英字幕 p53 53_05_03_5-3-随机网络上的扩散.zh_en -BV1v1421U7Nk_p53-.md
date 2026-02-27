# 斯坦福大学《社会和经济网络：建模与分析｜Social and Economic Networks： Models and Analysis》中英字幕 p53 53_05_03_5-3-随机网络上的扩散.zh_en -BV1v1421U7Nk_p53-

![](img/a736bc9df6e6bc06a4cfc92cdc4737a9_0.png)

Hi folks， so we're back again and we're talking more about diffusion and so we've gone through some basic questions and looked at the BaSs model。

 and now we're going to look at richer models that begin to bring in some network structure and try and understand how network structure impacts diffusion。



![](img/a736bc9df6e6bc06a4cfc92cdc4737a9_2.png)

And what we'll do is we'll start with very simple versions of this。

 where we'll work with Erdaranni style networks。 And then we can talk about other kinds of networks as well and what we can say about how things like the degree distribution。

Fect。

![](img/a736bc9df6e6bc06a4cfc92cdc4737a9_4.png)

Diffusion processes。Okay， so we're bringing in the interaction structure now and the basic idea here is going to be that there's some process going on in a network and we'll be thinking。

 you know one thing that's going to be important is thinking about what's the right network to define。



![](img/a736bc9df6e6bc06a4cfc92cdc4737a9_6.png)

And often in a lot of what we've been looking at， we've just been sort of taking networks and links as a given and not explored too much which particular network we want to be looking at and exactly what should be defining the nodes and the links so in this kind of situation ultimately what's really going to be important is when we think about a relationship or a link between two individuals。

 we should think of two people being related if one has a chance of passing something to the other。

 in whatever our diffusion process is， so if we're thinking about the flu。

 then we would think about I'd be connected to all the individuals who I might infect。

 and so that might be a very broad range of individuals whereas if we thinking about a political view or some new technology that I might tell somebody about it might be a much narrower set of individuals who we might have that kind of interaction。



![](img/a736bc9df6e6bc06a4cfc92cdc4737a9_8.png)

nodes are going to be linked if one would infect the other and one substantial simplification we're going to make to begin with is that this is going to be sort of an independent and identical probability across links。

 so each person has an equal chance of infecting any one of their neighbors。

 whereas that might not be true in reality where you might spend more time interacting with some individuals than others and have more of a chance of a diffusion process proceeding across some links than others。

 so we define the links by the interactions that are necessary for diffusion。



![](img/a736bc9df6e6bc06a4cfc92cdc4737a9_10.png)

We'll think about questions about when will an infection take hold。

 how many nodes or how many people will reach So know when do we get diffusion。

 what's the extent of the diffusion， How does it depend on the process and the network structure who's likely to be infected earliest。

 these are the kinds of questions that we can begin to answer now with the network analysis。

 So an important part of this is going to be understanding what the component structure is So the reach of the contagion is going to be determined by the component structure where what we think of as in terms of links as links being put down probabilistically according to whether or not to individuals would actually transmit from one to another。



![](img/a736bc9df6e6bc06a4cfc92cdc4737a9_12.png)

![](img/a736bc9df6e6bc06a4cfc92cdc4737a9_13.png)

So it's possible that some nodes or players are going to be immune， links might fail。

 so what we're going to look at is what do the components look like if only we consider the nodes that are susceptible and links that are actually going to transmit。



![](img/a736bc9df6e6bc06a4cfc92cdc4737a9_15.png)

Okay so just to sort of remind you， this is a picture from Berm Moody and Stovl's 2004 data of the high school romances。

 this would be something if we were thinking about transmission of mononucleosis or something we could think about a network like this and we end up with is the component structure will actually tell us a lot so if an initially infected individual ends up being in one of these nodes。

 then if they end up being in a large component then things can spread quite extensively if they end up being in a small component。

 then things can be quite limited and so looking at the component structure will help us answer two questions first of all what's the probability that we start a contagion and that's going to be the probability that we end up sort of hitting one of these large component。

 the large component in this case the giant component and then how extensive should it be。

case if we did hit somebody in the giant component。

 then the reach of it could potentially be the size of the giant component。

 so understanding what the component structure is will help us understand both the probability of starting and the eventual reach conditional on that。



![](img/a736bc9df6e6bc06a4cfc92cdc4737a9_17.png)

![](img/a736bc9df6e6bc06a4cfc92cdc4737a9_18.png)

So we'll think about getting nontrivial diffusion of somebody in the giant component is infected。

 adopt。 So I'll use the word infected， but it could be adopting into technology and so forth。

 and the size of the giant components can determine both likelihood and its extent and random network models are going to allow for giant component calculations。

 And now in terms of what we want to be thinking about in links now， we could say okay， well。

 a lot of networks we actually look at in the real world might be very well connected and have links so that everyone can reach everyone else in the world and so the world is one giant component。

 But the component structure we actually want to be thinking about are going to have link probabilities that are associated with the likelihood that one individual actually infects another。

 So it might be that somebody just doesn't catch the flu because they don't have interactions with people at the right times and so forth。

 So the network again we're going to be looking at is our people going to interact within a given time period when they're infected enough。



![](img/a736bc9df6e6bc06a4cfc92cdc4737a9_20.png)

![](img/a736bc9df6e6bc06a4cfc92cdc4737a9_21.png)

![](img/a736bc9df6e6bc06a4cfc92cdc4737a9_22.png)

![](img/a736bc9df6e6bc06a4cfc92cdc4737a9_23.png)

to transmitm and that can actually have a much more fragmented network structure than an overall long term network that we would look at normally。



![](img/a736bc9df6e6bc06a4cfc92cdc4737a9_25.png)

Okay， so what we can do is a simple example of such a calculation。

 and we'll start by working at a Ndsh Reni style random network。

 and then we'll also talk about other degree distributions and the main question we're going to be answering is just what can we say about how big the drag component is in such a network？



![](img/a736bc9df6e6bc06a4cfc92cdc4737a9_27.png)

Okay， so how big is a giant component if there is one？

And let's about so let's think about GNP as our starting model and if we think about that in terms of the starting model。

 then the size of the giant components is going to be interesting when P is in the range where the giant component isn't so small that it doesn't exist or so large that we have almost full connection so the interesting region is going to be when p somewhere between1 over n and log n over N and otherwise we're going to have basically isolated small components or a fully connected network。



![](img/a736bc9df6e6bc06a4cfc92cdc4737a9_29.png)

![](img/a736bc9df6e6bc06a4cfc92cdc4737a9_30.png)

![](img/a736bc9df6e6bc06a4cfc92cdc4737a9_31.png)

![](img/a736bc9df6e6bc06a4cfc92cdc4737a9_32.png)

And if we remember from before you know when P was smaller than one sorry the expected degree is smaller than one。

 so that's what you know in this range here with 50 nodes， P being 0。

01 each person that has an expected range of half a neighbor then we end up with not many people infecting each other and so we end up with you know lots of very tiny components actually only one that even has two links in it and lots of isolates。

 so this kind of situation if if the interaction structure was so limited we wouldn't see much of a contagion at all。

 so 0。02 is the point at which you have one expected neighbor above that you begin to get a giant component and here we would end up having know about half the nodes a little more than half in the giant component and so know it would be about half a probability of infecting and it would infect half the probability the population。



![](img/a736bc9df6e6bc06a4cfc92cdc4737a9_34.png)

![](img/a736bc9df6e6bc06a4cfc92cdc4737a9_35.png)

Once you get to about two and a half isn't expected。Set of neighbors。

 then we get almost the whole network， the whole population connected。

So we have a high probability of reaching everybody and a high number of people infected once one person is。

 and then once we get here to with with 50 nodes， once we have an expected degree of five。

 we were past the threshold for a connection and we end up having a connected network and now if this was if the interaction structure resistance。

 then you would expect full contagion。

![](img/a736bc9df6e6bc06a4cfc92cdc4737a9_37.png)

![](img/a736bc9df6e6bc06a4cfc92cdc4737a9_38.png)

Okay， so what we're going to do is actually go through some calculations next to give us more explicit numbers on on some of these things and calculate the size。

 the expected size of the giant component， rather than just looking at these pictures。

 So the pictures are based on these thresholds。 and indeed， you know， when we go。



![](img/a736bc9df6e6bc06a4cfc92cdc4737a9_40.png)

![](img/a736bc9df6e6bc06a4cfc92cdc4737a9_41.png)

From the threshold below expected degree of one to high enough expected degree to have everybody connected。

 we're going to hit the two extremes and the interesting part's going to be in between。

 And so let's take a look at that next。

![](img/a736bc9df6e6bc06a4cfc92cdc4737a9_43.png)

![](img/a736bc9df6e6bc06a4cfc92cdc4737a9_44.png)
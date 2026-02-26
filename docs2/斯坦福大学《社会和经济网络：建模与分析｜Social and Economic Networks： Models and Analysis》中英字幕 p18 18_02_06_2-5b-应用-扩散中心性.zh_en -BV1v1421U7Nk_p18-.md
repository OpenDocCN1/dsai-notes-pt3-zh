# 斯坦福大学《社会和经济网络：建模与分析｜Social and Economic Networks： Models and Analysis》中英字幕 p18 18_02_06_2-5b-应用-扩散中心性.zh_en -BV1v1421U7Nk_p18-

Okay， so let's have another look at centrality measures in the context of this diffusion process in rural India we were just talking about。

 and the idea here is going to be to come up with a centrality measure that might even do better than any of the ones we looked at before。

 I think the standard ones and I guess once you're in this business long enough if you've looked at enough networks。

 you'll find some need to invent the new centrality measure。 So what's the idea here。

 the idea is we'll define something what we can call diffusion centrality and the diffusion centrality of a given node I is going to depend on two different parameters。

 So again， this is out of the project with Abujiep Energy， Arunandra Ccar and S do flow。



![](img/10716a645298c0e8ea9e60e2faf5abb6_1.png)

![](img/10716a645298c0e8ea9e60e2faf5abb6_2.png)

And what we're doing is now looking at given nodes are informed about microfinance。

 they're going to tell their friends and eventually we want to see how that diffuses through the villages but in general we could think of know there's some node which is initially informed and how influential is going to be well we can do a calculation where each node is going to talk to its friends with a probability P in any given period so I talk to my friends with some probability P that goes on。

 then they talk to their friends and we continue on in this manner and this is going to run for T periods。

 some number of periods and then at the end we'll find out how many people have heard the news by the end of this process so one way to do this would be actually to simulate it。

 you could just start with the network inform a node flip coin so that if they talk to their friends with probability P and then it goes on and then just keep track of who heard another way an approximation of。



![](img/10716a645298c0e8ea9e60e2faf5abb6_4.png)

![](img/10716a645298c0e8ea9e60e2faf5abb6_5.png)

![](img/10716a645298c0e8ea9e60e2faf5abb6_6.png)

![](img/10716a645298c0e8ea9e60e2faf5abb6_7.png)

![](img/10716a645298c0e8ea9e60e2faf5abb6_8.png)

![](img/10716a645298c0e8ea9e60e2faf5abb6_9.png)

This will be just to multiply the adjacency matrix by P。And raise that to the T power。



![](img/10716a645298c0e8ea9e60e2faf5abb6_11.png)

And multiplied by one so that keeps track of how many people we have heard at each point in time and then what we can do is sumness from1 to T so this is going to be a situation where it's going to keep track of basically how many walks of different length。

 multiplied by times a P were going out so。

![](img/10716a645298c0e8ea9e60e2faf5abb6_13.png)

![](img/10716a645298c0e8ea9e60e2faf5abb6_14.png)

In situations where t is just equal to one， then this becomes proportional to degree centrality。

 So it's just calculating how many people do I reach directly。

 And so it's just going to be proportional to degree。

 If we look at a situation where t becomes large then this is beginning to look like the boage centrality calculation。

 and in particular， if p is smaller than one over the largest eigenvalue of the matrix。

 the adjacency matrix then this thing will converge and indeed will converge to cat's boage centrality where the p is playing the role of the weight。

 So this is sort of like doing botic centrality， but with a finite t。 in contrast， if p is larger。

 So if it's larger than one over the eigen value， then as t becomes large。

 this begins to approximate eigenvector centrality。 So this is a measure which for large t can。



![](img/10716a645298c0e8ea9e60e2faf5abb6_16.png)

![](img/10716a645298c0e8ea9e60e2faf5abb6_17.png)

![](img/10716a645298c0e8ea9e60e2faf5abb6_18.png)

![](img/10716a645298c0e8ea9e60e2faf5abb6_19.png)

either like eigenvector or some variation of boci Centrally， for small tea。

 it looks just like your immediate neighborhood and for intermediate tea。

 it's going to capture some repetition numbers of communications that you might have。



![](img/10716a645298c0e8ea9e60e2faf5abb6_21.png)

So let's have a look at what this does in the Indian data that we talked about before。



![](img/10716a645298c0e8ea9e60e2faf5abb6_23.png)

And in particular， what we've got here is a situation where we've got the diffusion centrality compare it to eigenvector degree closeness。

 boage and so forth that we did in our regressions before and what we find here is diffusion centrality significant and significant at 99% level so highly significant diffusion centrality here is defined by setting P actually equal to one over lambda 1。

 so equal to one over the largest eigen value of the matrix and so it's and then running it for some number of periods which was actually equivalent to the number of trimesters that a village had been exposed to information。

 so some villages had eight trimesters， some had three and so forth。

 but that gave us some number of rounds of communication that might go on in a village。

So here we see that this basic measure of diffusion centrality does fairly well。

And you know the other horse that seemed to be running pretty well is eigenvector centrality。

 so we can say， well it's hard to compare coefficients。

 becauses a larger coefficient just indicates that the units are different and so if we renormalize things we could make either coefficient larger or smaller so in order to figure out which one might be doing a better explanation。

 we can sort of put them together and the same regressions where we keep track of know things like the degree of the leaders。

 the number of households self-help group participation savings fraction in the CAs and so forth。

 so if we keep track of all these controls， then if we do the diffusion centrality。

 it turns out to be significant eigenvector centrality is also significant when we put them together then the diffusion centrality remains highly significant and doesn't change much the eigenvector centrality part of it is disappearing。



![](img/10716a645298c0e8ea9e60e2faf5abb6_25.png)

![](img/10716a645298c0e8ea9e60e2faf5abb6_26.png)

And the idea here is diffusion centrality is keeping track of the fact that communication is not going on forever。

 it's only going on some finite number of times and if you have some feeling for that then this is a very practical measure which is designed to actually figure out how nodes are what their position in a network is designed to spread information and that particular measure seems to do very well in this sense so once we look at a very specific process that can also suggest how we should measure the importance of nodes we can weigh them directly by the process that we think might be governing the communication or whatever it is that we're examining in a particular network and that'll give us a new idea of centrality measures or other kinds of measures of nodes。

Okay， so that's a little more about position in networks。

 there's a lot of ongoing research in this area it's a fascinating area for study。

 but now what we're going to turn to is beginning to understand network formation processes。



![](img/10716a645298c0e8ea9e60e2faf5abb6_28.png)
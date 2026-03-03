# YannicKilcher【中英⚡AI经典论文领读(全203篇)(上)｜Papers Explained】 p58 P70 《叠加中的超级掩码：深入解析》论文增补说明 [BV1o3xLznExj_p58]

Hi there。 Today， we'll look at super maskasks in superposition again。

 So this is part two of this paper by Mitchell Wetzman and Vivek Ramannuin。

 And here's a reason why there's a part2。 So after yesterday's video on this paper。

 I I couldn't sleep because I really felt that I had left out some important aspects that I wanted to touch on during the video。

 Now， sometimes during videos， I I look at the clock and I realize like oh。

 crap the videos already like an hour long and I know people are watching on2 x speed anyway。

 but still it's like too long and I need to wrap it up really soon。

 And what I felt were pretty important messages about this paper got lost。 So specifically。

 I want to address three different things。 First of all， they have like a formal analysis。

 not a formal， but a kind of more rigorous analysis of what their modified G objective does。

 And I also want to give some intuition in that because I felt I felt。

Really hadn't done a good job at that。The second part is that。

The the two different ideas right here being the super masks and the superposition。

 And I think my opinion is sort of that these are two separate things。

 and they really have nothing to do with each other。

 And I think that didn't really come through last video。

 And the third one being the broader impact statement of this paper。

 which I you know I usually kind of gloss over it and go like ha but I here there is an important point to it。

 So yeah， we'll get to that。 Allright， so again， not a new paper today。 I realize this。

 but I think it's worth kind of diving deeper into this paper， which is a very cool paper。 you know。

 so so don't don't get me wrong right here。 And I feel mostly I have done a good part at explaining it。

 like literally lying away。

![](img/1b34dd00d04aac00e10b342a11a6d7a4_1.png)

![](img/1b34dd00d04aac00e10b342a11a6d7a4_2.png)

![](img/1b34dd00d04aac00e10b342a11a6d7a4_3.png)

![](img/1b34dd00d04aac00e10b342a11a6d7a4_4.png)

Okay， so let's go to the first point。 we had this。 So if you hadn't seen the first video supermaasks and superposition basically says that we want to do lifelong learning and we want to do lifelong learning by lifelong learning is the task where you have a bunch of tasks in sequence and you learn them in sequence。

 So one after the other。 and basically the goal is to not forget tasks onces new you learn new tasks and this model does it by always building one of these supermaasks for each task that is applied to the same randomly initialized base neural network each time。

😊。

![](img/1b34dd00d04aac00e10b342a11a6d7a4_6.png)

![](img/1b34dd00d04aac00e10b342a11a6d7a4_7.png)

And you know by by keeping the supermask around you won't forget the task and then at inference time。

 if you're given the tasking just to retrieve the mask， if you're not given the task。

 you can do this superposition trick where you apply all the masks in a superposition and then you look at sort of the gradient of an entropy function in order to decide which task reduces the entropy the most so which task is the most certain about a particular data point and that you kind of infer that that's the task you're going to go with。

 so instead of the entropy。

![](img/1b34dd00d04aac00e10b342a11a6d7a4_9.png)

![](img/1b34dd00d04aac00e10b342a11a6d7a4_10.png)

![](img/1b34dd00d04aac00e10b342a11a6d7a4_11.png)

Wwhichch is you know well reasoned， they had this other objective they call a G and G basically looks at the it's really strange。

 it looks at the superfluous neurons so they also add these superfluous neurons。

 these S neurons right here。

![](img/1b34dd00d04aac00e10b342a11a6d7a4_13.png)

And。They they， the G objective will only look at the S neurons in order to decide whether or not that's the correct task。

 And it's basically just the log sum X of the S neurons。 And we had some intuition about them being。

 you know， all small and so on them being like outlier detectors。

 But there is an entire chapter in the appendix where the authors do a sort of more in depthth theoretical analysis of that。

 which you know， I。It's not necessary to do this for them。

 so I really I enjoyed reading that and that gave me sort of the better intuition of what this G objective does。



![](img/1b34dd00d04aac00e10b342a11a6d7a4_15.png)

![](img/1b34dd00d04aac00e10b342a11a6d7a4_16.png)

So here they say the aim is not to formally prove properties of the algorithm。

 rather we hope that a more mathematical language may prove useful in extending intuition， okay。

So again， that's pretty cool。 So they start off by saying you have your neural network is basically W and sorry it's this phi right here and the W are the last layers weights which compute your logs。

 so y is going not to be your class but y is going to be your logs and P is going to be the probability vector over your class。

 which if you calculate this via a softmax is going to be the following expression right here。



![](img/1b34dd00d04aac00e10b342a11a6d7a4_18.png)

![](img/1b34dd00d04aac00e10b342a11a6d7a4_19.png)

![](img/1b34dd00d04aac00e10b342a11a6d7a4_20.png)

If you have a mask， right， then at least in the last layer。

 you can you can infer it as this right here， so you multiply the mask by the last these weights and then that gives you your locks。



![](img/1b34dd00d04aac00e10b342a11a6d7a4_22.png)

![](img/1b34dd00d04aac00e10b342a11a6d7a4_23.png)

So they say here they initialize the weights right here， actually。

 they initialize the they have no bias term and they initialize the weights by this constant。

 So plus minus this constant， it's not really necessary to do that。

 but they do it right here makes the analysis also a bit easier。 I guess it just works more well。

 if you have these masks in superposition， of course you want to add all of these masks with the respective alpha weighting factor then multiply by the weights and that gives you your logins。



![](img/1b34dd00d04aac00e10b342a11a6d7a4_25.png)

![](img/1b34dd00d04aac00e10b342a11a6d7a4_26.png)

![](img/1b34dd00d04aac00e10b342a11a6d7a4_27.png)

![](img/1b34dd00d04aac00e10b342a11a6d7a4_28.png)

![](img/1b34dd00d04aac00e10b342a11a6d7a4_29.png)

So。Note that this， this doesn't necessarily only only have to be the last layers weights right here。

 You can view that as any sort of weights of the neural network if you formulate this phi correctly。

 So you don't think that they only apply the mask to the last layer。

 They do apply the mask to the entire thing。 Alright， now the， the important part here is。



![](img/1b34dd00d04aac00e10b342a11a6d7a4_31.png)

![](img/1b34dd00d04aac00e10b342a11a6d7a4_32.png)

What happens if we look at the derivative of G with respect to one of the alphas and take the maximum negative derivative of that G。

 which is that mysterious function that only looks at the superfluous neurons。What they want。

 They kind of construct this G by principle。 What they say is we want a function G that mimics the supervised loss。

 right， we want a function G that is kind of equal like the supervised loss if we had the task I D。

 right， And that's， that's pretty cool because。😊，You know the supervised loss。

 you sort of need all the information， you need the label。

 you need need all the you need the task ID， so the supervised loss is unavailable。

 but we want a function G that in its gradient mimics the supervised loss。



![](img/1b34dd00d04aac00e10b342a11a6d7a4_34.png)

![](img/1b34dd00d04aac00e10b342a11a6d7a4_35.png)

So they go about constructing this right here。 They say Lemma first lemma。

 it's possible to construct the function G such that the gradient matches the gradient from the supervised loss for all S neurons。

 So for all the superfluous neurons specifically we want that the gradient with respect to the logts。

 If the gradient to the logts is equal， that means the gradient to all the rest of the network is equal because the rest of the network goes through the logs the gradient through the logts is equal to the gradient of the supervised loss to the logits for all the superfluous neurons and0 otherwise。

 So they say the0 otherwise is pretty easily done in math。

 you know simply set it to0 and in the actual code。Which you can achieve like this。

 where M indicates the superfluous neurons。 So this is just they multiplied here and the other ones are detached。

 so there is no gradient flowing。

![](img/1b34dd00d04aac00e10b342a11a6d7a4_37.png)

This is the property that we only look at the superfluous neurons。

 and now we are going to show that the gradient is going to be equal。



![](img/1b34dd00d04aac00e10b342a11a6d7a4_39.png)

![](img/1b34dd00d04aac00e10b342a11a6d7a4_40.png)

So they say if you had D。Supervised loss， which means if you had the label。

 then this would be your cross entropy loss。 Okay， so you cross a divides into this part where you need the label。

 And then this part here。 You don't need the label。 Now， you， you can pretty say pretty much say。

 look， the label is certainly going to be one of not the superfluous neurons。

 because the superfluous neurons are superfluous。 They are never the correct neuro。

 So this is always going to be， you know， not the not the neurons we look at。 So the gradient。

 certainly this is always going to be 0。 because we never we。



![](img/1b34dd00d04aac00e10b342a11a6d7a4_42.png)

![](img/1b34dd00d04aac00e10b342a11a6d7a4_43.png)

Wherever the gradient is flowing， that's not where this is one。So。

The gradient of any superfluous neuron is just this thing right here。

 And that's exactly why they build the function G。 So the function G has this exact gradient。

 The function G， if you derive it， has that same gradient as the supervised loss for the superfluous neurons。



![](img/1b34dd00d04aac00e10b342a11a6d7a4_45.png)

![](img/1b34dd00d04aac00e10b342a11a6d7a4_46.png)

Okay。
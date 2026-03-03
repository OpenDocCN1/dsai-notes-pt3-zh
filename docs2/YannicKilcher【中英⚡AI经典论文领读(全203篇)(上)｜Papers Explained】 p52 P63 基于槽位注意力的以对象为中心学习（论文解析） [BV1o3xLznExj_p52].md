# YannicKilcher【中英⚡AI经典论文领读(全203篇)(上)｜Papers Explained】 p52 P63 基于槽位注意力的以对象为中心学习（论文解析） [BV1o3xLznExj_p52]

Hi there。 Today， we'll look at object centric learning with slot attention by Francesco Locateello。

 Thomas Kipp and others of Google Brain， ET Zuric and MP On a high level。

 this paper recognizes scenes of objects from single pixels and it's best I show you a picture of what's going on。

 So you have scenes like this where there is some sort of a arrangement of objects and there are multiple tasks you can do here specifically they consider the task of unsupervised recognition of objects which they call object discovery and supervised classification of objects。

 The difficulty being that these are sets of objects。

 So there is no ordering to the sets They do this via a thing they call slot attention that basically is a permutation invari attention mechanism over these objects in both the supervised and unsupervised domain and they do this in a fashion where they iteratively。



![](img/81644ce362ca18a50f176725f48334a9_1.png)

![](img/81644ce362ca18a50f176725f48334a9_2.png)

![](img/81644ce362ca18a50f176725f48334a9_3.png)

The attention in order to make the different slots compete for attention over these objects。

 So that's the sort of high level。 If you are in this field。

 you probably know right now what's going on if you're not we'll dive into it together so stay tuned if you like content like this。

 consider sharing it out leaving a like or tell me what you think about it in the comment。

 I appreciate any suggestion for making these videos better and so people can learn more from it。



![](img/81644ce362ca18a50f176725f48334a9_5.png)

![](img/81644ce362ca18a50f176725f48334a9_6.png)

![](img/81644ce362ca18a50f176725f48334a9_7.png)

Alright， so the problem I've already described the problem a little bit。

 but let's go a bit deeper here you have images like this and the images we're considering are going to be images that have some sort of arrangement of objects or what we humans would call objects in this case you can see there is this gray square not sorry these gray cube right here there is a smaller green cube and then there is a yellow cylinder Now in the task of object discovery what you're supposed to do is you're simply supposed to say that there is an object right here there is an object about here。



![](img/81644ce362ca18a50f176725f48334a9_9.png)

![](img/81644ce362ca18a50f176725f48334a9_10.png)

And there is an object here。 right， So basically， you're supposed to point to the pixels where there are objects and you're supposed to segment the objects from each other。

 You can see right here that this model。

![](img/81644ce362ca18a50f176725f48334a9_12.png)

We don't know how it works yet， but it separates the left cube here， the bottom cube here。

 and the top right cylinder right here。

![](img/81644ce362ca18a50f176725f48334a9_14.png)

In the task of set prediction， you're supposed to say what objects there are。

 So you're supposed to say there is a gray cube right here， a green cube right here。

 and there is a yellow cylinder right there。 Actually， you don't have to say where they are。

 I guess there are many different variants of this task， but mainly you're supposed to classify them。

 meaning you you have to say there is a gray cube there。

 I believe in this case it's with coordinates， but you can do it without the difficulty here。

 of course， being that these are sets， So there is no natural order in it。

 So if you say there is a green cube and a yellow cylinder it's going to be the same as there is a yellow cylinder and a green cube。



![](img/81644ce362ca18a50f176725f48334a9_16.png)

So you'll have to build an architecture that is somehow invariant with respect to the labels and。



![](img/81644ce362ca18a50f176725f48334a9_18.png)

We've seen a lot of the concepts in this video in this paper before。

 This video is sort of a kind of a mash together of different concepts of other places。

 So what you'll see is， for example， this property of the fact that here you see are the labels for these objects。

 This could be there is a green cube。 There is a gray cube and。



![](img/81644ce362ca18a50f176725f48334a9_20.png)

![](img/81644ce362ca18a50f176725f48334a9_21.png)

![](img/81644ce362ca18a50f176725f48334a9_22.png)

You'll have to come up with an architecture that if here you predict that green cube。

 you consider it correct， even though the corresponding label isn't the one for the green cube。

 and we saw this， for example， in this DETR architecture by Facebook where they use a matching loss。

 but we'll get into that。

![](img/81644ce362ca18a50f176725f48334a9_24.png)

![](img/81644ce362ca18a50f176725f48334a9_25.png)

Okay， so these are the tasks， the task are object discovery and set prediction。

 So how does this paper deal with this。

![](img/81644ce362ca18a50f176725f48334a9_27.png)

![](img/81644ce362ca18a50f176725f48334a9_28.png)

Use this thing called a slot attention module。Now， the slot detion module is in essence。

 it's pretty simple。 What it does is it has these different slots right here。As you can see。

And it divides the input into features。 So you can see there is a CNN encoder because we're working with pixels。

 It's natural that we want to encode these into a CNN。

 The CNN will probably down sampleample the image of it and。

Divide subdivided into this grid right here so you have a fairly coarse grid。

 the grid is actually not a bit finer than you see here， this is just for example。

 but you'll have ultimately a number of features so each pixel right here is going to be a feature each feature will have not only this one channel as you see here but many。

 many channels of information down here so the CNN will encode each of these regions in the picture into a feature vector。



![](img/81644ce362ca18a50f176725f48334a9_30.png)

![](img/81644ce362ca18a50f176725f48334a9_31.png)

And then you have these slots。So what you'll want to do， we maybe look at this。

 so you'll have the features right here。These are your features。And you'll have the slots。

And the slots， let's say there are fewer slots than features。To three， three slots， four slots。

 as in this case。4 slots。What you'll want to do is you'll want to assign the features to the slots。

 so you maybe say， okay， this feature right here and this feature right here。

 they go to this slot and then these two features go to this slot and this these two go to this and that feature goes to that and that's equivalent to basically subdividing the picture into these slots ultimately your goal is going to be to say that these features right here。

 these pixels right here。

![](img/81644ce362ca18a50f176725f48334a9_33.png)

![](img/81644ce362ca18a50f176725f48334a9_34.png)

Are going maybe into that slot and then these ones right here are going into that slot and these ones here going into that slot and the rest。

 So all of their background is going into that one you can see that if you have a system like this if you can train it correctly then it becomes pretty easy too so it becomes super easy to classify it right here because you can just take each slot and independently classify it right because you already know you already have assigned all the pixels where the object appears into that slot。

 you can just super easily predict a class from it。



![](img/81644ce362ca18a50f176725f48334a9_36.png)

![](img/81644ce362ca18a50f176725f48334a9_37.png)

![](img/81644ce362ca18a50f176725f48334a9_38.png)

So we're almost at the end。 so you now predict for each slot a class or a description of the object。

 whatever you want to predict。 And this is the exact same thing as in this Facebook paper now where for each for each of these slots。

 we've predicted a bounding box。 The question is how do you assign this to the labels and that's pretty easy that there's this thing called the Hungarian matching。



![](img/81644ce362ca18a50f176725f48334a9_40.png)

![](img/81644ce362ca18a50f176725f48334a9_41.png)

![](img/81644ce362ca18a50f176725f48334a9_42.png)

That， basically。What you're saying is you want to be as forthcoming as possible right。

 So if you predict a gray cube somewhere and there is a gray cube somewhere here。

 you want to match them， you'll say， okay， I'm going to give you the benefit of the doubt and I'm going to。

Dear model， I'm going to assume with the gray cube， you meant that gray cube right here。

And if there is the yellow rectangle and the yellow rectangle somewhere over there。

 you don't incur any penalty as long as you predict the correct thingss now only。

Whenever you predict like a second yellow rectangle。 So both of these slots。 now。

 so this slot and this slot， for some reason， they predict a yellow rectangle。 This one correctly。

 and this one was assigned this object and it incorrectly predicts a yellow rectangle。 sorry。

 other way around。 This one incorrectly predicts a yellow rectangle。

 where there is no second yellow rectangle in our label set。

 there is only this maybe this green cube。

![](img/81644ce362ca18a50f176725f48334a9_44.png)

![](img/81644ce362ca18a50f176725f48334a9_45.png)

![](img/81644ce362ca18a50f176725f48334a9_46.png)

Then this will be a mistake because it it can't be matched。

 It will be matched to the one where it has the least loss。

 but it will be matched to something that's not a yellow rectangle。

 And therefore that's going to be a mistake。 So this is how you calculate the loss function with this matching algorithm and you can calculate that matching in a deterministic fashion。

 so you can back propagate through it。

![](img/81644ce362ca18a50f176725f48334a9_48.png)

So you can see if this slot assignment works， we'll have a pretty easy time。😊。



![](img/81644ce362ca18a50f176725f48334a9_50.png)

Then calculating the classes coming up with a loss， the same for the unsupervised object discovery。

 What we'll do is we'll run these things through this slot decoder。 Now。

 this slot decoder is very similar to an a generator in GNs， for example。

 it takes a hidden representation as input。 Now the hidden representation here is going to be these slots and it's going to ups sampleampble it into an image if we train the whole。

 if if we have a good slot assignment mechanism。 we can pretty easily train a decoder like this right with any method you want in this case。

 I believe they use。

![](img/81644ce362ca18a50f176725f48334a9_52.png)

![](img/81644ce362ca18a50f176725f48334a9_53.png)

![](img/81644ce362ca18a50f176725f48334a9_54.png)
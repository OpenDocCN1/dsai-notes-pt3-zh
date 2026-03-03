# YannicKilcher【中英⚡AI经典论文领读(全203篇)(上)｜Papers Explained】 p19 P19 DETR：基于Transformer架构的端到端目标检测（论文精解） [BV1o3xLznExj_p19]

Hi there。 Today we're going to look at end to end object detection with transformers by Nicholas Carion France Coassa and others at Facebook AI research。

 So on a high level， this paper does object detection in images using first CNN and then a transformer to detect objects and it does so via a bipartite matching training objective and this leaves you basically with an architecture that is super。

 super simple compared to the previous architectures that had all kinds of engineering hurdles and thresholds and hyperparameters so really excited for this。



![](img/7f227b8033b60d6f6a87f44cc61a4de9_1.png)

As always， if you like content like this， consider leaving a like a comment or subscribing。

 Let's give into it。 So let's say you have a picture like this here。

 And you're supposed to detect all the objects in it。 And also， where they are。 and what they are。

 This task is called object detection。 So a good classifier here would say there's a bird right here。

 And so this is a bird。

![](img/7f227b8033b60d6f6a87f44cc61a4de9_3.png)

And then this here is also a bird。Right they can be overlapping these bounding boxes。

 So this is you see the first problem that bird， why is that green？Never mind。 Okay。

 and those are the only two objects。 So there's a number of， of very difficult things here。

 First of all， you need to sort of detect the objects。 You need to know how many there are。 It's all。

 it's not always the same in each image。 There can be multiple objects of the same class。

 There can be multiple objects of different classes。

 They can be anywhere of any size that can be overlapping in the background small or across the entire image。

 They can occlude each other partially。 So the problem is a very， very difficult problem。

 And previous work has， has done a lot of engineering on this。

 like building detectors and then kind of you want to classify every single pixel here。

 And then you you get like two detections right here that are very close for the same class。 you say。

 that must maybe be the same。

![](img/7f227b8033b60d6f6a87f44cc61a4de9_5.png)

instancet， right， So there's only one thing here and not two things and so on so。



![](img/7f227b8033b60d6f6a87f44cc61a4de9_7.png)

There， there used to be very complicated architectures that solve these problems。

 And this paper here comes up with a super simple architecture。

 and will kind of go from the high level to the low， to the implementation of each of the parts。

 So what does this paper propose。 How do we solve a task like this。 First of all。

 we put the image and the image here without the labels。 Of course。

 we put it through a convolutional neural network encoder。 Since this is an image task。 It's。

 you know， kind of understandable that we do this。

![](img/7f227b8033b60d6f6a87f44cc61a4de9_9.png)

![](img/7f227b8033b60d6f6a87f44cc61a4de9_10.png)

![](img/7f227b8033b60d6f6a87f44cc61a4de9_11.png)

Mostly because。

![](img/7f227b8033b60d6f6a87f44cc61a4de9_13.png)

CNN's just work so well for images。 So this gives us this set of image features。 And I think this。

 this vector here is not really representative of what's happening。

 So let's actually take this picture right here and throw it in kind of an angled way。



![](img/7f227b8033b60d6f6a87f44cc61a4de9_15.png)

And what， what we'll do with CNN is we'll simply sort of scale it down， but have it multiple。

 So here it's three channels， right， It's red， green and blue。Like this， three channels。

 but we'll scale it down， but we make it more channels。 So du du。Yeah， so more channels。Okay。

 but it's still sort of an image right here。 It still has the image form Okay。

 so the the CNNN basically gives us this thing which is sort of a higher level representation of the image with many more feature channels。

 but still kind of information where in the image those features are。

 and this is going to be important in a second。

![](img/7f227b8033b60d6f6a87f44cc61a4de9_17.png)

![](img/7f227b8033b60d6f6a87f44cc61a4de9_18.png)

![](img/7f227b8033b60d6f6a87f44cc61a4de9_19.png)

Because now this thing， which is this set of image features， goes into a transformer encoder decoder。

 And this is sort of the magic thing here， as， as a。



![](img/7f227b8033b60d6f6a87f44cc61a4de9_21.png)

![](img/7f227b8033b60d6f6a87f44cc61a4de9_22.png)

Component we'll look into that in a in a second。 But what they get out right here is this set of box predictions。

 So outcomes comes each of these boxes here is going to be。



![](img/7f227b8033b60d6f6a87f44cc61a4de9_24.png)

![](img/7f227b8033b60d6f6a87f44cc61a4de9_25.png)

Consisting of a tuple and the tuple is going to be the class and the bounding box。 Okay。

 so an example for this could be bird。Bird at X equals 2。 Y equals 5。 Okay， that that's an example。

 Another example of this could also be。

![](img/7f227b8033b60d6f6a87f44cc61a4de9_27.png)

There is nothing。At x equals 7， y equals 9。 Okay， so nothing。



![](img/7f227b8033b60d6f6a87f44cc61a4de9_29.png)

The nothing class is a valid class right here。 And that's also important。

 But safe to say there is this set of box predictions。 And then that is basically your output， right。

 These things are your output。 If you have those things， you can draw these bounding boxes。

 you can assign the labels。 The question is， how do you train it。



![](img/7f227b8033b60d6f6a87f44cc61a4de9_31.png)

![](img/7f227b8033b60d6f6a87f44cc61a4de9_32.png)

![](img/7f227b8033b60d6f6a87f44cc61a4de9_33.png)

Now what you're given is a database。Of images and these images， as you see here on the right。

 these images already have by human annotators drawn these bounding boxes in and also labels。

 So this here would be annotated with bird， and this here would be annotated with bird。



![](img/7f227b8033b60d6f6a87f44cc61a4de9_35.png)

But it doesn't have any of these like it doesn't annotate the nothing classes or and so on。



![](img/7f227b8033b60d6f6a87f44cc61a4de9_37.png)

So the question is。How do you compare the two， Can you simply say okay。

 if the first one here is the bird and then and the second one is this bird， then it's good。

 but then you know the ordering shouldn't matter you simply care whether you have the correct bounding boxes。

 you don't care whether you output them in the correct order and also what if your classifier does something like this。

 it outputs those two boxes we see here， but it also outputs this here and says bird or like one that is slightly off and says bird and so on。

 So how do you deal with all of these cases。

![](img/7f227b8033b60d6f6a87f44cc61a4de9_39.png)

![](img/7f227b8033b60d6f6a87f44cc61a4de9_40.png)

So the way that this paper deals with all of these cases is with their bipartite matching loss。

 this thing right here。 So how does it work， Let's say your where can we go。



![](img/7f227b8033b60d6f6a87f44cc61a4de9_42.png)

Let's say youre classifier， so here is an image。I'm have to wait for this to catch up。

 Here is an image， and we put it through this entire pipeline， right。

 and we get a set of predictions， right， And they're going to be class bounding books。

 class bounding books， class bounding books。 Now， the first thing you need to know is that there are always。

The same amount of predictions， right There are always this size here is fixed。 That's large n。 Okay。

 that is sort of， that's kind of a maximum of predictions。

 since you can always predict either a class or the nothing class in， in this case。

 you could predict anywhere from 0 to5 objects in the scene， right。Okay。

 and then the second thing is from your from your database。

 you get out an image with its bounding box annotations that are made by human labelers。

Let's say these two。And you also do class bounding box， class bounding box。

 But now you see we only have two， two instances。 So here we just pad with the nothing class so。

I don't know what the bounding box should be for the nothing class。 It doesn't really matter。

 nothing， no bounding box， nothing， no bounding box。No bounding box。So。



![](img/7f227b8033b60d6f6a87f44cc61a4de9_44.png)

Your ground truth labels， if you will， are also of size n。

 so you always compare n things here on the left that your classifier output with n things on the right。



![](img/7f227b8033b60d6f6a87f44cc61a4de9_46.png)

Now， as we already said， the question is， how do you deal with。

 you can simply compare one by one because the ordering should not be important。



![](img/7f227b8033b60d6f6a87f44cc61a4de9_48.png)

But also， you don't want to encourage your classifier to always kind of if there is。

 if if the one bird is very prominent， right， you don't want to encourage your classifier to say to say。

 here's a bird。 here's a bird。 There's a bird right here。 Hey， hey， there's a bird。 There's a bird。

 There's a bird。 And basically， just because the signal for that bird is stronger and basically ignore the other bird。

 What you want to do is you want to encourage some sort of your classifier to detect。

 If it has already detected an object。 It shouldn't detect it again。 in a slightly different place。



![](img/7f227b8033b60d6f6a87f44cc61a4de9_50.png)

![](img/7f227b8033b60d6f6a87f44cc61a4de9_51.png)

![](img/7f227b8033b60d6f6a87f44cc61a4de9_52.png)

So what the way you do this is with this bipartid matching loss。

 So at the time when you compute a loss， you go here and you compute what's called a maximum matching。

 Now， what you have to provide is a loss function so we can there's a loss function L and L will take two of these things。

 L will take。

![](img/7f227b8033b60d6f6a87f44cc61a4de9_54.png)

![](img/7f227b8033b60d6f6a87f44cc61a4de9_55.png)

The red， the predicted thing of your model。And L will take。

The true one of the true underlying things。And L will compute a number。



![](img/7f227b8033b60d6f6a87f44cc61a4de9_57.png)

And we'll say， how well do these two agree？So you can say， for example。

 if either of them is the nothing class， then I have no loss， like I don't care about them。

 that gives you no loss， but if if the two classes agree and the two bounding boxes agree。

 then it's very good right then we maybe even give like some negative loss or give loss。



![](img/7f227b8033b60d6f6a87f44cc61a4de9_59.png)
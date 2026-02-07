# mrdbourke《一天学会pytorch深度学习｜Learn PyTorch for deep learning in a day Literally》中英 - P11：9. Outline.zh_en - GPT中英字幕课程资源 - BV1kx4y1r79d

In this fundamentals module。 But I just want to reiterate the fact that going back to the last video where I challenge you to look up what is a tensor。

 here's exactly what I would do。 I would come to Google。 I would type in the question。

 What is a tensor。 There we go。 What is a tensor in ptorrch。

 It knows Google knows that using that deep learning data that we want to know what a tensor is in Ptorrch。

 But a tensor is a very general thing。 It's not associated with just Pytorrch。

 Now we've got tensor on Wikipedia。 We've got tensor。

 This is probably my favorite video on what is a tensor。 by Dan F F， I'm probably saying that wrong。

 but good first name and。😊。

![](img/bceedfa4f3ba10b5bbbfc11ac310e64f_1.png)

![](img/bceedfa4f3ba10b5bbbfc11ac310e64f_2.png)

![](img/bceedfa4f3ba10b5bbbfc11ac310e64f_3.png)

This is going to be your extra curriculum for this video and the previous video is to watch this on what is a tensor。

 And now you might be saying， well， what gives， I've come to this course to learn pietorrch and all this guys doing。

 or you're doing， Daniel is just googling things when a question comes up。

 Why don't you just tell me what it is。 Well， if I was to tell you everything about deep learning and machine learning and pietorrch and what it is and what it's not。

 that course would be far too long。 I'm doing this on purpose。

 I'm searching questions like this on purpose， because that's exactly what I do day to day as a machine learning engineer。

 I write code like where about to do。 And then if I don't know something。

 I literally go to whatever search engine I'm using Google most of the time。

 and type in whatever error I'm getting or pitorrch， What is a tensor or something like that。

 So I want to not only tell you that it's okay to search questions like that。 But it's encouraged。

 So just keep that in mind as we go through the whole course， you're gonna see me do it lot。

 But let's get into what we're going to cover。😊。

![](img/bceedfa4f3ba10b5bbbfc11ac310e64f_5.png)

![](img/bceedfa4f3ba10b5bbbfc11ac310e64f_6.png)

Here we go。😊，Now， this tweet is from Elon Musk。 And so I've decided， you know what。

 Let's base the whole course on this tweet。 We have learning M L D L from university。

 You have a little bit of a small brain online courses。 Well， like this one。

 that brains start to explode and you get some little fireworks from YouTube。

 if you're watching this on YouTube。 Look at that Shi brain from articles。 my goodness。

 lucky that this course comes in。😊。

![](img/bceedfa4f3ba10b5bbbfc11ac310e64f_8.png)

![](img/bceedfa4f3ba10b5bbbfc11ac310e64f_9.png)

![](img/bceedfa4f3ba10b5bbbfc11ac310e64f_10.png)

Article format if you go to learn Pytorrch。😡，Thatt I O。

 All of the course materials are in online book format。

 So we're going to get into this fundamental section very shortly。 But if you want to reference。

 the course materials are built off this book。 And by the time you watch this is going be more chapters here。

 So we're covering all the bases here。 And then finally， from memed。

 you would ascend to some Godlike C， I think that's hovering underwater。

 So that is the best way to learn machine learning。 So this is what we're going to start with M L。

 D L from university， online courses， YouTube from articles from memes。 No， no， no， no no。

 But kind of， yeah。😊。

![](img/bceedfa4f3ba10b5bbbfc11ac310e64f_12.png)

![](img/bceedfa4f3ba10b5bbbfc11ac310e64f_13.png)

![](img/bceedfa4f3ba10b5bbbfc11ac310e64f_14.png)

![](img/bceedfa4f3ba10b5bbbfc11ac310e64f_15.png)

Here's what we're going to cover broadly。😊，So now in this module。

 we are going to cover the pytorch basics and fundamentals。

 mainly dealing with tensors and tensor operations。

 Remember a neural network is all about input tensors， performing operations on those tensors。

 creating output operations later we're going to be focused on preprocessing data。

 getting it into tensors， So turning data from raw form images。

 whatever into a numerical encoding which is a tensor then we're going to look at building and using pre-trained deep learning models。

 specifically neural networks。 We're going to fit a model to the data so we're going to show our model or write code for our model to learn patterns in the data that we've preprocessed We're going to see how we can make predictions with our model because that's what deep learning and machine learning is all about right using patterns from the past to predict the future。

And then we're going to evaluate our models predictions。

 We're going to learn how to save and load our models， for example。

 if you wanted to export your model from where we're working to an application or something like that。

 And then finally， we're going to see how we can use a trained model to make predictions on our own data on custom data。

 which is very fun。 And how， well， you can see that the scientist has faded out a little bit。

 But that's not really that true。 we're going to do it like cooks， not chemists。

 So chemists are quite precise。 Everything has to be exactly how it is。 but cooks them more like oh。

 you know what a little bit of sold， add a little bit of butter。 Does it taste good。 I。

 well then we're on。 But machine learning is a little bit of both。😊。



![](img/bceedfa4f3ba10b5bbbfc11ac310e64f_17.png)

Little bit of science。 little bit of art。 that's how we're going to do it。

 But I like the idea of this being a machine learning cooking show。

 So welcome to cooking with machine learning， cooking with pie torch with Daniel。😊。



![](img/bceedfa4f3ba10b5bbbfc11ac310e64f_19.png)

![](img/bceedfa4f3ba10b5bbbfc11ac310e64f_20.png)

And finally， we've got a workflow here， which。We have a Pytoch workflow， which is one of many。

 We're going kind of use this throughout the entire course is step 1。

 we're going to get our data ready。 Step 2， we're going build or pick a pretrain model to suit whatever problem we're working on。

 Step 2。1 Pick a loss function and optimizer。 Don't worry about what they are。

 We're going cover them soon。 Step 2。2， build a training loop。

 Now this is kind of all part of the parcel of step 2， hence why we've got 2。1 and 2。2。

 You'll see what that means later on。 number3， we're going to fit the model to the data and make a prediction。

 So say were working on image classification for ramen or spaghetti。

 How do we build a neural network or put our images through that neural network to get some sort of idea of what's in an image。

We'll see how to do that。 We'll evaluate our model to see if it's predicting P S or it's actually going。

 All right。 number 5， we're going to improve through experimentation。

 That's another big thing that you'll notice throughout machine learning throughout this course is that it's very experimental。

 Part art， part science。 numberumb 6， save and reload your train model。 again。

 I've put these with numerical order。 But they can kind of be mix and matched depending on where you are in the journey。

 But numerical order is just easy to understand for now。😊。



![](img/bceedfa4f3ba10b5bbbfc11ac310e64f_22.png)

Now we've got one more video， maybe another one before we get into code。

 but in the next video I'm going to cover some very。

 very important points on how you should approach this course。😡，I'll see you there。



![](img/bceedfa4f3ba10b5bbbfc11ac310e64f_24.png)

Name， I'll be asking。
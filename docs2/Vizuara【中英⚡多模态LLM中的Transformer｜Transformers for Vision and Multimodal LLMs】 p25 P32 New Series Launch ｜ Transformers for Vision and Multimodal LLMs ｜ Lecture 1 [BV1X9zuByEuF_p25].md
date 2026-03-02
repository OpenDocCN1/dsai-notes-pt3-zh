# Vizuara【中英⚡多模态LLM中的Transformer｜Transformers for Vision and Multimodal LLMs】 p25 P32 New Series Launch ｜ Transformers for Vision and Multimodal LLMs ｜ Lecture 1 [BV1X9zuByEuF_p25]

Hi， welcome to a new boot camp， this is the first lecture from our brand new boot camp Transformers for Viion and multimodal LLMs。

My name is Dr。 Sriad Pant。I am a PhD from MIT and graduated from IET Madras。

 I am also one of the three co founders of Viura and I will be your instructor throughout this course。



![](img/11b94307bbfc0098e544640663b9ce7f_1.png)

🎼。

![](img/11b94307bbfc0098e544640663b9ce7f_3.png)

So I have a few agenda for today's lecture since it's the first lecture of the series。

 I want to introduce you to a few things。😊，I will first talk a little bit about myself for those of you who do not know me。

I will also mention a little bit about what exactly is this boot camp about from the name you might understand that it has got a bunch of things to do with the transformer architecture which has revolutionized the way we look at AI since the introduction of Cha GT。

I will exactly make you understand if this bootc is meant for you or not irrespective of what your background is or whether you are a student or industry professional。

I will mention about the prerequisites， the detailed curriculum。

 some logistics with respect to how the next lectures will proceed。

And then what all can you get out of this boot campm。

 I will also mention a little bit about that at the end of this lecture。



![](img/11b94307bbfc0098e544640663b9ce7f_5.png)

![](img/11b94307bbfc0098e544640663b9ce7f_6.png)

So I am Dr。 Sriva Panard， I did my PhD at MID from 2017 to 2022。

In the field of mechanical engineering， but it was a very interdisciplinary program。

 so I worked on a variety of high impact projects which had real world implications。



![](img/11b94307bbfc0098e544640663b9ce7f_8.png)

And had a bunch of interesting things that I worked on as part of my PhD。

 so this is a picture of me working in my lab at MIT。



![](img/11b94307bbfc0098e544640663b9ce7f_10.png)

And one of my thesis projects was related to autonomous solar panel cleaning。

And one aspect of this project had to do with computer vision。

 specifically with convolutional neural networks。So that was one part of my PhD that had direct application with respect to computer vision and with respect to AIMl。



![](img/11b94307bbfc0098e544640663b9ce7f_12.png)

But there were a few other interesting projects that I were part of even before my PhD。



![](img/11b94307bbfc0098e544640663b9ce7f_14.png)

So I just wanted to show you my work。

![](img/11b94307bbfc0098e544640663b9ce7f_16.png)

So I have a YouTube video that features my thesis。Work in MIT's YouTube channel。

 it has almost 300 k+ views now I will share this link in the description so you can feel free to open this。



![](img/11b94307bbfc0098e544640663b9ce7f_18.png)

![](img/11b94307bbfc0098e544640663b9ce7f_19.png)

Where they show the final practical embodiment of what I built。

 so it was a robotic solar panel cleaner which was actuated using a robotic arm and there was a high voltage setup and the quantity of the voltage you apply in kilotts will depend on the size of the particle。



![](img/11b94307bbfc0098e544640663b9ce7f_21.png)

Now this particle has a size distribution so you don't know whether it's 10 microns， 20 microns。

 30 microns， etc， so we used a computer vision system with a camera that could zoom in 4050x。

To collect pictures of the foul solar panel， and then I used a convolutional neural network to classify those images into different buckets of particle size in microns。

And now based on this particle size， I could decide what could be the dust removal voltage because there is a direct correlation between particle size and dust removal voltage and automatically I can change the voltage accordingly so this was the gist of what I worked on This has huge implications in real life you can。

Prevent the usage of up to 50 or even 100 billion gallons of fresh water which is currently being used for solar panel cleaning purposes。

 and this is only expected to grow exponentially as the installed solar base is increasing。



![](img/11b94307bbfc0098e544640663b9ce7f_23.png)

So this was a very interesting project and I learned a ton of things from that。



![](img/11b94307bbfc0098e544640663b9ce7f_25.png)

After graduating， I started Bijowarra AI Las with Dr。 Raj and Dr。 Rajat as the co foundunderers。

 so ever since we have been working on a mission to make AI accessible to everyone。



![](img/11b94307bbfc0098e544640663b9ce7f_27.png)

![](img/11b94307bbfc0098e544640663b9ce7f_28.png)

![](img/11b94307bbfc0098e544640663b9ce7f_29.png)

And the first time I had my。Research experience working in computer vision was well before MIT。

 so this was almost 10 years or more ago， sometime in the beginning of 2015 if I remember correctly。

 I was working at IT Madras on a problem statement for classifying rice grain varieties。



![](img/11b94307bbfc0098e544640663b9ce7f_31.png)

So the problem was we had。Pictures of different varieties of rice grains in various fashions。

 sometimes the pictures were like this， so here they are almost kind of sparsely located they are not forming a heap。

 Sometimes in the pictures these rice grains will form a heap so you will not see the background at all you will just see bunch of rice grains。



![](img/11b94307bbfc0098e544640663b9ce7f_33.png)

And we had we were working to create an algorithm， which can first。Click the picture。

 create boundaries around the rice graves， sometimes they touch。

 sometimes the boundaries overlap so you have to figure out different conditions and make adjustments to your logic。

And then finally fit ellipses around these rice grains and use the average length and average breadth of those ellipses to say whether this is pony。

 bamay， Jasmine rice， etc。

![](img/11b94307bbfc0098e544640663b9ce7f_35.png)

So the simple logic was you take a photo if they are sparsely located。

 you can easily get a nice thresholding。 So these thresholding techniques are。

Clasic computer vision techniques， you create filters which can perform thresholding or you define conditions where you eliminate pixels of values below certain number。

And once you have the threshold image， you can perform edge detection algorithm。

 which again are executed using filters， similar kind of filters which are also seen in convolutional neural networks。

 although these may be hand engineered。And then once you detect the edges。

 the logic is around these edges you could fit a least square ellipse and now I will use the length and breadth of this least square ellipse to characterize the size of the rice grade。

 this was the idea。

![](img/11b94307bbfc0098e544640663b9ce7f_37.png)

![](img/11b94307bbfc0098e544640663b9ce7f_38.png)

Now in this case， the logic was simple， but there were edge cases where you might have two rice grains touching so in this case the boundary is detected but the boundary is one single boundary where two rice grains are detecting。



![](img/11b94307bbfc0098e544640663b9ce7f_40.png)

Then we had to add a logic for drawing boundary between those two rice grains， something like this。



![](img/11b94307bbfc0098e544640663b9ce7f_42.png)

![](img/11b94307bbfc0098e544640663b9ce7f_43.png)

And then， we had to find。2 ellipses that was fitting in a least square fashion to those two rice grains separately。

 Otherwise， you may fit just one ellipse with something like this， which is not correct。 You have to。

 because there are two rice grains here。 Sometimes you could have three rice grains，4 rice grains。

 depending on the orientation。 It's very random。 So there had to be a robust。Hand engineered logic。

To detect the rice grain boundaries separately。

![](img/11b94307bbfc0098e544640663b9ce7f_45.png)

So this logic was a bit more nuanced， but you could see that until this point I did not mention anything about deep learning。

 I did not mention anything about neural networks， all of this was PR。😊，You know。

 human engineered logic。Now once we collect a lot of pictures。

 once we fit ellipses around these rice grains， we can plot them and when we plot so ignore these names and circles for a moment。

 ignore this you know region boundary， but basically what we will see is these rice grains will form clusters clusters where some rice grains will have more of width。



![](img/11b94307bbfc0098e544640663b9ce7f_47.png)

![](img/11b94307bbfc0098e544640663b9ce7f_48.png)

Clus where some raised grains will have more length and some were in between。

 so by looking at these clusters。We will know that okay。

 we have five variety of rice grains and here are the five clusters and now if a new rice grain is coming。

😊，I could perform a machine learning algorithm to maybe do K means clustering， something like that。

Or I can。Do some other simple machine learning algorithm， maybe can nearest as niBs， whatever it is。

So this was the crux of the problem statement that we worked on。



![](img/11b94307bbfc0098e544640663b9ce7f_50.png)

And。We submitted this paper into the ninthth international conference for Mach Vision。

 which happened in Nice in France， and it got accepted and we presented our work there。



![](img/11b94307bbfc0098e544640663b9ce7f_52.png)

It was。Three years after the introduction of Alexnett in 2012。

 Alexnett was the model that revolutionized deep learning as we see today。

And professors in different universities were still working on hand engineered features for identifying various aspects from teenagers。

 deep learning was becoming popular， but there were people working on hand engineered features also just like our group at dieting Mad us。

But it became very clear to me that during this conference presentation。

 deep learning is entirely taking over computer vision and this shift was very clear because it was extremely difficult to you know hand engineer features and logic。

 this would have been infinitely easier if we train in a neural network convolutional neural network with lot of data。

😊。

![](img/11b94307bbfc0098e544640663b9ce7f_54.png)

So from a rule based system which looks something like this， so our logic was completely rule based。

 no deep learning involved。

![](img/11b94307bbfc0098e544640663b9ce7f_56.png)

You could easily move to something like。

![](img/11b94307bbfc0098e544640663b9ce7f_58.png)

Input to output mapping， so you have input images corresponding。



![](img/11b94307bbfc0098e544640663b9ce7f_60.png)
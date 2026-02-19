# UCB《计算机视觉与计算摄影学｜CS 194-26 Computer Vision and Computational Photography 2022》中英字 p05 -P05-5-The Frequency Domain-9_12.zh_en -BV1w7UfBdELA_p5-

啊啊嗯。Check， check。We have， we have two more minutes until Berkeley time。

 but I invite you to look at this picture by going up and down。😊，This aisle。

 if you're interested in the two minutes that we have until we start the class。

 if you're coming down， look at this picture。 Look at this picture as you move down from the entrance to down。

😊，Nobody interesting。To， to go up and down， this is like， you know。

 you go to this mirror house or something you already did，😊，喂。You see it， but you got to do both。

 Yesly， you got to do both。You're gonna de both to see the effects。对。对呀。Okay。Oh，我给 people coming。

Okay， let's get started。Okay。Let's get started。啊。Alright， I'm super excited about this class。😊。

Because it's going to be a very interactive one。And I even have a live coding demo in the end I prepared。

😊，Hopefully， we get to it。And it's just a really cool content。😊，That you probably have seen。

But hopefully， this would be more intuitive。Okay， before we get started。Project 2 is starting。

 I see some questions。 I really do encourage you to start early。😊，And you know what。

 The wait list in this class has cleared。So you guys are survivors， okay。So to those of late joiners。

 if there is somebody who happened to be in this class， because all it happens to be open。😊。

Unfortunately， we can't give you an exception to the project because that's what we said from the beginning。

 The plenty of people who are waitlisted still that they project 1。 Okay， and so submitted。

 So this is this class is a real life rules。 You know， in real life， you're late。

 You don't get extensions。😊，In real life， rubrics are big， okay。All right。Okay。

 so any questions on logistics。Okay， good， good。 The presentationation also happens again this Thursday。

 So please make it。 There wasn't any recordings， but they want to record it。 Okay。

 so they're open to it。 Hopefully， they'll remember next time。😊，Okay。

 before we jump into this super cool picture。😊，I just want to recap a little bit last week。

 in the end of the class， I was talking about how when you do convolution。

 youre having to do with the edges。 And in many of these examples that we've been doing by hand。

 we've been using0，0 edges。 right， So like this， this filter G over here goes out of the frame。😊。

But over here， I'm just gonna just pad it with 0。 That's one way。

 But another way to do this is to do a wraparound where you just repeat this inside across that way。

 Another thing is to just copy the edge or reflect the edge。

 So there are many different options that you can do。 So that that's like 0 pad。😊，You know。

 the zero pad has its own problems because the zero is really see in here。 If you look here Cor cute。

 you know， you know， because you pat it with it， the edges do and neural networks do this too。

 If you pat it with the zero， they know that， oh， you know what， I'm like on the top。

 So you know what， if I'm doing semantic segmentation， it's likely it's sky。😊，It really does happen。

 So you can do all these different things。 I mean， it's a problem。

Best solution is just to have a big image where you can just crop out the outside。 Okay。

 so that's like repeat。None of them really look naturalural either。 But， you know。

 maybe they don't have the black bleeding。 Oh， this is the reflection。Maybe， you know。

 so you can play around with this when you do your homeworks。 Okay。

 so that's one slide I didn't get to last time。Okay， so today we start with the psychophyic test。

 which I offer to some of you， which 1% of you guys did。 I think， okay。

 maybe you guys already know this。 You can stand up right now and then go back and forth and look at this picture from different locations。

😊，And it's a the psycho physics test。So people in the back row， what， what， what。

 what does this look like。What image does this look like。Some famous person。Okay。

I hear this in the front of look。You had Lincoln。Right， yeah。Good， background girl。Okay。

How about the front rows。What do you see。It's a nude lady。 nude， lady， nude， okay。So。

This is the painting by Salvador Delhi。It's called Gaa， contemplating the Mediterranean Sea。

 which at 30 M becomes the portrait of Abraham Lincoln。😊，は。😊，So， it's very verbal。Gla is his wife。

Okay。So you can kind of discuss what's， what's。Really going on。 Can somebody tell me。What。

 what is happening。I feel like if I still take off my glasses， that works。Lady。Yeah呀。我二。Right I。

Very good。 Very good。Okay， that's perfect。 So you， you said that。

It's Gaussian filter when you take it off。 So what does that mean。Anybody else。

What's happening when you， when you take off your glasses and it's Gaussian filter soul。😊。

You're seeing the。Yes， you're seeing the low frequency component， exactly。😊，Okay。

 so that's what you see if you take off your glasses or you' far away。

 which looks like Abraham Lincoln。😊，Okay， so then what's the other part of the image。Yes。

 the high frequency。 Now， we haven't really talked about how to compute the high frequency filter。

 And we're going to next or maybe at the end of this lecture。 But can somebody just suggest like。

 that's， this is low frequency。 That's the original image。😊。

We want to see the high frequency component。What， what could we do。That's high food。 That's original。

 That's low frequency。 If I give you these two things， what could you do。😊，Yes， just subtract。

 So you can be subtract away the low frequencies。 Yes， exactly。 subtract this image。😊。

From that image。Okay， then you get this image。Yeah。And now you can really see the gala， his wife。

 contemplating the Mediterranean sea。😊，So 30 m away， you should be able to see this。Okay。

 so we're gonna get into this。How we're gonna make this。 And this is actually one of your project。

 too。 You're gonna make this hybrid image。 But， and then we're gonna figure out how。

 why can't we see these both， these paintings， You know， this。

 this has high frequency and low frequencync components。 and how does it work。Okay， alright。

 so we're going to start with this really cool curve called Campbe Robson Contra sensitivityivity curve。

 which I think is done by psychology people as a psychoanalytics class， okay。😊，So on the X axis。

 you see。A sine wave。 Okay， sine wave in 20。 Okay， it's like really like not like so this is frequency。

 This is super， super high frequency。 And as you go left， it's like very low frequency。 Okay， big。

 big curves goes， very， very fine curves。😊，And on the Y axis， you have the。

The contrast gets lower as you go up。 as in like， this is amplitude is highest here。

And it's like one minus amplitude。 as you go up， the amplitude of the wave， right。

 gets like smaller and smaller。 Or you can think of it as a contrast。 Okay。

 so if all the way up over here， you can think of like， you know， think about the sine wave。

 which we're gonna see a lot。 You can multiply the amplitude， which is like this height of the wave。

 right， You can multiply that to be really small value。

 then it's gonna be just like really flat flat line。😊，So， that's what we see。

And you should be able to， kind of。See a boundary of where you see the patterns and where you see the gray。

 If you look up this carefully。😊，So what kind of， what kind of pattern do you see。Yeah， okay， okay。

 How about in the back。What kind of pattern do you see or like， where is the what。

 what's the boundary between gray and like this black and white thing。Right。

 there's at one point where you stop seeing the。You know， it's different for everybody。 But here you。

 obviously， you see the sine wave all the way over here。 It's like all gray。Like。

 there's a boundary when it becomes gray。Right， what is that。呀。Yes， yes。 Okay。 So everybody looking。

 so it looks like this。😊，Okay， so this is basically。

Our sensitivity to the contrast as a function of the frequency。😊，And this is a very， very surprising。

Graph。Because you would think， you know， like， wouldn't it be a flat line。Right， you're just saying。

 like the contrast。Of you， color is like。哦。s good the contrast。😊，Is like， you know。

 isn't it like a flat line because you say， you know， brightness， basically。

 I'm gonna say brightness， like， you know， say like， you know， close to grade 0。3 or something。

 You can't see it。 but it's not。 It's actually really sensitive， so。😊，This is also probably。 so。

 so okay。 So look， we're really sensitive to the middle frequency。

 We can see it although I can see it like our own hill here。😊，Okay， but in the high frequency。

 I stop seeing like around here， maybe here。Cause I'm closer to maybe。 And then a lot of frequency。

 we also don't see it here。O， anybody， it's a question。

 Ask me questions becauseuse when I first saw this graph， I was like， what am I looking at。

Good question。 by frequency。It's gonna be something like。Like this， you know。I。

 I'm gonna leave out the face for the moment。 But remember this like sine curve。

 which is a multiplly by sine omega X， X is like the input。 so omega is like the frequency。😊，可。

Exact thing。Okay， Oomega is the frequency。 So as higher than， higher the frequency， like more， like。

 you know， the wave becomes like really， really choppy。😊，Right， like in audio。

 if you hear like somebody very high pitch tone is like a very high frequency sound and like a base is very low frequency sound。

 Okay， that's just visualized。 Like， look just think of if you just looked at this as one D。

 this would be like， you know， like， this would be like one to 0 to one to 0， right。

 you see the curve。😊，Okay， other questions about this。 Like does this make sense what you're seeing。

なぜせか。啊全。Okay， yeah， yeah。 So over here， the contrast， like the Y axis。Is this1 minus a。 So like。

 as you go on the top。A is like， say 0。Okay， so like， this just becomes like a 0 line。

 You don't see anything。Okay， and then you can think of this as like brightness or like， you know。

 strength。As， as you go down， the amplitude is like， say， hundred。 So you。

 you get to see that curve curve a lot。So that's why it's kind of like， this is a contrast。

I think we zoomed in。要。InLi sense。はいす。It's a good question。 If we zoom in。

 if I can I see if I can zoom in， I guess I can。 if I was able to zoom in。

 it will still be the same because it's a function of frequency。 But I guess if I zoomed in。

 the frequency changes a little bit， too。 Yeah， so if you， like basically， if you walked closely。😊。

I think it， but there's a point in which you can't see it。呀。呀。对。对は。We are。No， no， It might just be。

What that you see。It's， it's different from everybody。 I， I， I kind of see what you're saying。 Like。

 if I look at it， it kind of looks like this， you mean， right， Like for you。

 you actually see stuff here， too。😊，And this is different to every single person because your perception is different。

 So this is a really crazy thing about。😊，Vision， human vision is that like this is you would think like this is same information。

 right， It's multiplied by the same constant， but different wave。 But we see different things。

 according to how fast that wave is going。Okay， so that's kind of supernllling or crazy thing that our brain is doing。

And。This is why vision is very difficult。 And then。

 computer vision is also really interesting or difficult。 So let， let's see， like。

 maybe let's go back to this example and like try to explain。 Okay。

 any more questions about this particular curve。😊，Like， what the plot you get what's being shown。

Good， it's okay to ask questions。😊，If you， yes。😊，けてそだ。Yeah， yeah。 I think so。 Yeah。

 it would be like over here， I can't see anything。 but if you looked at the actual values。

 it would be alternating up the frequency of this width。这拿证明了吧。呀。😡，Yeah， it's actually。

 actually the information is in there。 Comp can see very different things。Yeah， okay。

DoThe pixel values come closer and closer？At the very。At that very top， like。

 I think it's the first row is all the same because say the amplitude is like 0。

 then I think it's all the same。 But like around here， like， it's gonna be like super fine。

 like maybe one pixel difference or maybe subpix difference or depending on how big this image is。😊。

But it's like that。Okay， good。 So I think you get this point is that you， you really don't see。

 you up here， you kind of see the differences here。 You still see the pattern。 But over here。

 you really don't see the pattern。Okay， so can you use this to describe what what's happening in this image。

Anybody。Wants to take a pass， try。quite。Being on the。Yes， yeah。You're able to see the。Take a part。

Right， okay， so。Yeah， exactly。 So if you're in the back， you see this basically。

 or if you take off your glasses， you see this。😊，And that's because。And then you all see the gala。

 Okay， the gala lady is not there anymore。 And the lady is not there because lady is super high frequency。

 And lady is like here。😊，Okay， if you're in the back。The lady is basically around this regime。

 and you don't see it。Okay， and the， the Abraham Lincoln is like around here。Right。

 so like if you're in the front or if you have your glasses on。Where is Abraham Lincoln。呀。他他不。

Above the curve。 Which curve。 top of the curveb。The flat one。Para， oh， parabola。

 So this is where the Abraham Lincoln is。 if you're in the back。😊，If you're in the front。

You don't see Abraham Lincoln。So yeah， you're， you're over here。

 So Abraham Lincoln is like over here。 It's like too low frequency。 so you don't see it。

 But if you're in the。Since you're closer， now， gala is in like this range of frequency。

 And then you get to see her。Okay。Why do you think， Okay， how about this， a good。

 about another interesting question。 What do you think this curve looks like for an eagle。

 Because this is for humans。Could you So， so if you think about this， right。

It says that humans are not that sensitive to low frequency changes。Right， so it's like in the dark。

 things move。Like， it's， you know， slow move， slow moving chains。 We're not very sensitive to it。 So。

 for example， like this one， okay。Like， there's like a blue sky。Okay， it is a picture。

 so you can kind of see it。 But like， if you're seeing the beach in your own eyes。😊。

This color and that color probably looks the same to you。It's a very slow changet。

We're not sensitive to it。 It just all looks like the same color， right。

 because that's like in this regime。And we're also not sensitive to super high frequency stuff。

But maybe we're high we're sensitive to this mid frequency， because。I don't know。

 Maybe that's like the frequency size of where the berries are or something， you know。

 when we have to eat。Yeah。Well， I guess that's， if you can。

 maybe you see it because we told you now that。I mean， you can。see it。 I mean， I think， you know。

 look， it's 30 M。 I think 30 M is a little bit further away。

 So I think the example of taking off your glasses is a really good one。😊，Depending on your eye。

 maybe you don't have a glass。 but if your eye is bad， it's a very， very strong low bus filter。

 So eventually， as you go further enough。Like， you wouldn't really see it。

I think in that in this class， the range is basically like around here。 So we kind of see everything。

In this question， Okay， so what do you think The e， e。Contrast。

 Campville Robson sensitivity curve would look like。Yeah。

 they probably can see this part a lot more because they have to fly and like， look at it。

And I also heard the cat。Hun in the dark。So they're actually pretty sensitive here。Okay。

 so this is an interesting。 I think if you take a cogsai 10 something， they tell you more about this。

😊，O。😊，So any questions。Why is。Good glasses。 So the further away you move， the amount of pixel light。

😊，That reaches your eye， covers a larger area。Right， so then it's down samplingling。 Yeah， Yeah。

 yeah， yeah， good question。You said， like。我一个。Oh， I I， I meant doesn't oh because at night。

 because it's so dark when things move around， it， it's like it。

 it's low more low frequency change because it's like you can't really see So the changes are gonna be like softer。

 you won't really see it so high contrast。 Yeah， but it's not really about the contrast。

 but it's just things are low frequency in the dark。😊，Good。Yeah。有没签字。Yeah， okay。 I think it's so， so。

 so you're saying like， in order for you to not see it， do I need to like lower the contrast。Yeah。

 I then you could lower the contrast。 like， but then I think it's more like fixing the contrast。

Constant， like， suppose like you draw a line over there。O， the contrast is same。

But then you still don't see the low frequency。 And then you'll start to see a lot， right。

 So that it's kind of like saying that。 you don't really， it's not really。 I mean。

 this is just doing this to kind of show that the pattern has is sensitive to the frequency values。

 But like， if you were to make these images， you will kind of fix the contrast， fix the amplitudeed。

😊，Does that make sense。I reallyally how you sat in the dark。Yeah。😀啊哈。😊。

Or it's more like it's just anything is listed。 So suppose you like。

 suppose somebody walks with a white。White paper in the dark going like this。 Like if it's bright。

 you will see the white thing move a lot， right， But then in the dark， you know， you don't。

 maybe don't even notice that that's a white thing。 So when it moves around。

 you don't really get to see。 Basically， just don't see。Yeah， so give you。Yeah， if you， yeah。

 just in the， in the darkness， you don't really get to see And therefore first。

 don't get to see means like， you don't get to see things clearly when things change a lot。

 that's like low frequency。Or like， smooth changes。 Everything becomes smooth。

It's like adding a darkness filter to， you know。生。I would imagine the artist is like。Yeah。

 so maybe that's not a good that's not a good example。 I guess it's。😊，Yeah， but like， I bet like。

 you know， we won't really notice if like rats are moving around in the dark in the corner of our eye。

 you know， and if it was during the nu， during the day， you will see it。Okay it then it's。Yeah。

 it's also the darkness thing is that the contrast。 So this is why I think that's one example。

 But it's compounded by the fact that the amplitude is also lower because it's night。

 But then this is like a good example because it's like same brightness。

 But because the changes like if you cut this blue here cut that compared to this patch。

 it's actually quite different， but we don't really see it。😊，We're not that sensitive to。Good。Good。

 okay， great。 This is very important。Okay， so today， what we're going to talk about is that， okay。

 let's see。😊，Okay， let me see， yeah。我我有有。呃。Okay， yeah， perfect。 Okay， so today。

 what we're going to talk about is that。😊，We can describe an image with this frequency basis。 Okay。

 so with that knowledge in mind。😊，啊。We're gonna talk about。Representing an image。

 How to represent an image using different set of bases。So， let's， let's just draw。

An image right here。 Let me just draw the basis for the Cartesian image or like the usual image that you're used to。

 Okay， so this is like an image of a cat。O。😊，나お。This is。Can be represented as。I'm gonna。Okay。

 so this is like。End end by end。I为。Okay， I'm going to find this image into n square。By one vector。

Okay， I'm gonna say my first basis。Is the one where the first pixel。Is one。O。😊。

And then you look at the first pixel value。 say this in this picture， it was 58。😊，Right。

 then you can say58 multiply by this pixel。 That will represent that one first pixel 0，0。😊，有。Okay。

 and then so you can do it again。 And then， and then I'm gonna this whole image is represent。 I mean。

 you don't need to make it into a vector。 It's just like hard to draw it。

 So I'm just making it into a vector。 But you can， you can think of it as like an image that's like where where only one pixel is like lit up 1 and everything else is 0。

😊，Okay， so you can keep on making this basis。Where like， you know， only one pixel。Is  one。

 and everything is 0。Everything is 0。And then you can just multiply it with whatever pixel value that was there。

 like 9，0， I don't know， whatever it is。Okay， so you can see， right， like the image。That is N by N。

 gray scale。 You can always represent it in this linear algebra， like basis method。

 or like where these are your basis。 and these are your coefficients。😊，Good。

 so then how many bases do I need in order to represent this image。Or like。

 in this particular way of writing it， How many bases do I need to use to capture the entire image。

In squared， exactly。 So I need it two。 I need every single one all the way until every single pixel。

 that's usually how we store the image。 And that's called。

 we're gonna call that spatial domain because you're like saving very spatially， right，1，1 pixel。

 you know， is that on or not。😊，Today， we're going to talk about。

A different way of writing this basis。It doesn't have to be this basis。 It could be another basis。

 And youre going to use this basis that are made out of ss and cosines。And hopefully。

 this is a topic that you've come across。 or， you know， if you're from signal processing background。

 you may have seen this。This four year transform。And were in this class， we're gonna give a very。

 very intuitive computer vision， like way of thinking about this。😊，O。All right。Okay， so， yeah。

 So like that thing is not the only way。 And this is the other basis that we can write it as。

So we know this as So okay， so。What am I talking about， I'm talking about a four year transform。

This change of basis， which was。Invented by John Baptist Joseph Poyer。 I can't say that。But， okay。

 this this is not a crazy idea。 It'd be like， you know what。Any function？

Can be written as a sum of sign。And cosines are different frequencies。Okay。

 this is a pretty crazy idea。 I'm like， I don't know if somebody told me that I would be like， oh。

 really， I wouldn't know if I would be like， okay with it in the beginning， actually。

 people didn't believe it。 This is that if you write papers。

 you have to submit your paper in academia。 You write a paper。 You have this new idea。 You know。

 every function can be represented by some of cosine and sign。 You write a paper。

 and then you're gonna get a referee。 There's like reviewers。 There's three reviewers。 Okay。

 they look at your papers and say this is novel concept。 It's good experimentation。

 This like reviewer number two。 It is like the manner in which the author arrives that these equation is not exempt of difficulties。

 And his analysis to integrate them still leave something to be desired on the scope of general generality and even rigor。

😊，Or it's a very sharp criticism that basically is reity doesn't understand。This idea。

 And I was like， reject。I don't understand it。Okay， so people didn't these are famous people。 Lovela。

Like Ras and all these people。And。啊。They didn't really believe it。

 And then it wasn't even translated into English until 1878。 But this is true， mostly。

 And it's called a four year series。Okay， and it says that the。

 any signal like this one can be built of sums of signsines and cosines， but it' just say signs。Okay。

Alright， so let's see。 So this is a target signal that you wan to reconstruct。

 This is a step edge function。😊，Okay， you first have like one close。 Okay， you just say。

 let's just have everything of one。And then you add this sign curve to that。

 And then it looks like that。Okay， it got shifted a little bit up。 like， you know， okay。

 and then you add this time curve。Oh， no， no， no， no。 This is a sign curve。 this sign curve。

 you add to that to that。 and you get this， you add this sign curve to that one。

 and then you get this， and you get more finer and finer sign curve。 And then you get that。

 you get added to the previous thing。 And then you keep on doing forever。

 And then you're gonna get this function。😊，Okay。😊，So， then tell me。We talked about this。 But。

 what is this omega。Yeah， can you like do it with your hand。Yes， it's this dish。Okay， what， what。

 what is amplitude， What is it。okay， let's do hand。 Yes hand。 this thing。 Okay， what is the。

 what is the fee。😊，Yes， yes， it's like this。 Okay， got done。 Okay， so how many。😊。

Degrees of freedom is this。3， exactly。And then it turns out that frequency is one of the more important things。

Okay， so we have three degrees of freedom。😊，Omega is what we're sensitive to。

 That's what we were drawing over here。Right， so that's the omega。 We。

 we're not drawing any phase here because it's just shifting this thing。 That's the amplitude。

 We're sensitive to omega。 So we're gonna talk about the omega。😊，Okay， we did this。 We did this。

 What does each control。 We did the hands。Okay， and。Which。

 which one encodes the coursese and fine structure of the signal。Frequency， yes， frequency。 Okay。

 because this is， you know， going doing this fast is like fast。 Okay， and like， okay。

 you could think of low frequency as just low， slow changes。 High frequency is like high changes。

 Okay， sudden changes。 Okay， so like in this picture。😊，Over here， you're like 0。 and you're like。

 suddenly， you're like 2。Okay， that's very high frequency。 It's actually called a step function。

 And in order to represent something that is as discontinuous as like going from 0 suddenly to some other number。

 you， you actually need infinite number of signine curves。😊，But we will see。Okay， and then。

So you hear about this thing called four year transform， which is just a change of basis。 Okay。

 so this is like， you know， math mamble jumbo。 You have a signal F of X。 Okay。

 you send it to this thing called four year transform。 And now you have a function。

 that is a function of frequency。😊，Before it was like space， like spatial， like0，1，1，2。😊，Okay。

 it's because like， you know， look， pixel 0，0 and that cat image was 58， right。You look up by 0。

0 location。 You look up by spatial， but now you're gonna look up by a frequency。And啊。For every。

frequencyequency。S omega holds the amplitude and phase of the corresponding sign。Like， okay， so like。

啊。You have like X， X， Y， right， X， Y， R column， Okay，0，0。 If it's an RGB image， what， what does this。

I function肯。3，3 numbers， RGB， right， RGB here it's like omega is the lookup。Right， and it has。

I I put didn face。Okay， just so it's just a change of basis。

 You're just saying that representing the same thing， but with different representation。And呢。

Its where it kind of gets complicated or it's not that we don't really need to worry about this too much。

But like， right， So this if of omega is a lookup function， right， and it has two， two dimensions。

 alpha and amplitude and phase。😊，And if it was RGB。

 would have been X to RGB or X to some if it was 1 D， great image， it was just the intensity。

 But this is you know， where like the math people in order to do their proof wanted to make it a little bit more complicated。

😊，Because instead of having like a two dimensional array where like at every omega。

 you store like amplitude and phase， like a simple thing。

 They did it with this like a complex number， which still needs2 bits because you have the real in the complex value。

 Okay， instead now I'm gonna store this thing as this the real complex number。😊，Okay。

 then you can take the。Absolute value or like the absolute value of magnitude of this complex number。

 If you recall from long time ago， Apple magnitude of the complex number look like this。😊。

And that's how you encode the amplitude。Okay， and then the， the。

 the the arcton of like these real in the im imaginary in the real numbers， give you the face。😊。

This is just like technicalities。Okay， you can always do this。 Go back。拨的。I we know， it's， it's。

 it's a， it's an invertible process。 as in like once you have an omega， you have this complex number。

 If you have a complex number， you can get to this amplitude and days。 and you can， you can go back。

😊，Any， any question。About this。any question about F of omega。Now we're gonna write this is a me。Okay。

 it's just， it just， it， it's just a function that goes from。Very， like before。

 F of X might have been。You know， RGB。Now it's a F of omega。B。You know， amplitudeitude and faith。

 But instead of writing this it like this， you're gonna write it like。The三。三三咩。A some。

 a some complex number where like this magnitude is， you know。I think hopefully。

 you can see that or like。I can put turn on the light so that you can see that and take any question。

Good。Okay， well， let just is an example。 This is just kind of a。And then you can always go back。Okay。

 let's look good time。 Okay， so。So， for example， this signal。

 this is the original one that we want to represent。Okay， and this。

 you can do it write it as a sum of this and that this， this frequency plus that frequency。 I mean。

 we actually have the answer here because we that G T is actually out of this。😊，Okay。

 and you can write。So this is what I'm saying， like F of omega as a function of omega。Okay。

 I'm like at omega 0。 what do I have？ Nothing at omega F。I have value 1。Okay。

 because the amplitudeted here is one。Alright， at omega 3。This is just pi。 This is a period thing。

 is one over3。O。😊，So。This summation of sine waves can be succinctly described just the amplitude part。

 I'm not talking about the face with this kind of， this is a lookup function， basically。😊，呀。😮，Good。😊。

Okay， more examples。Yeah， this is just like we have this。 Again， it's a sip function。 It's a very。

 very strong high frequency over here， the edge。You add this low frequency， You add more frequency。

 You add more frequency。 You add more frequency。 And then as you add more。

 it becomes this kind of thing。😊，And as you can see， if you kept on adding this forever。

You're going to get to。You're gonna get this some。 this is， this is the frequency response。

 So so you call this frequency spectra， which is like the amount of magnitude or amplitude at that frequency。

😊，Yeah， so this is really just like the coefficient。 Okay， over here。

 the coefficients or like theo actual brightness values multiplied by every single spatial。😊。

Value over here。Iletted is like the coefficient because you take like one sine wave。

 I multiply by that amplitudeted， and then you sum it。 Okay， if you don't need that sine wave， you。

 you just multiply by 0。That coefficient is 0。Right。

 so your basis are your sine functions and your coefficients are your amplitude。😊。

And then there's also phase。 But you， we visualize the amplitude。 I can show you face later， but。

Question。Yes。Yeah， you have to do it for RGV separately。 Yeah， yeah， yeah。Yeah。

 so this equivalency is like only for R。 I mean， or it's not an equivalency。

 I'm just like showing as a different type of ways of thinking about this function。😊，嗯。Good question。

I think it's unique。 Any from analysis 2 that recently took analysis  too can tell me this。

 I think it's unique。😊，I I think it's unique and you can write it as a proof。Useual unique。意思是由你个给。

Nothing as always， always a dangerous serious。学生。Good question。 If they don't。 Well， it depends。

 right？ I mean， like with this， the other spatial basis， you have to have n squared numbers。 I mean。

 you you store an image of n by N， you have to store n squared numbers。 But you'll get to。

 this is a good question。 Like， if you wanted to represent this image。 and say it was 2D images。

 But you only needed these two。 then you really don't need to hold so much numbers or you have lots and lots of zeros。

 And this is why。😊，Change of basis is like a nice thing to do， because in linear algebra。

 maybe you learned that， like， you know， the more compact or expressive your basis。

 the less you don't need to， less you have to hold on it。😊，So it's just like a better basis。

 And there's other basis that we're gonna see later， like PC A， but it's just one kind。😊。

And that's one of the properties。Okay， I， okay， I feel like you could ask questions。

 If I was a student， I would look at this， and I have like a very glaring question that。😊，Like。Like。

 what do you have any questions about this， this， this， this thing。对啊。Why does it look like a。Gusian。

 it's close。 I think my question is like， what is this negative。Right， like what is？😊，だげれ。是喂。😊，It在这。

0， it issymmetric around 0。 but this is just this。 There's no such thing as negative frequency。😊。

Right， so what is this negative mum jumble。 And it just comes from these mass people wanting to write this as complex numbers。

 And if you go in that route of complex numbers， maybe you remember that cosines can also be written as some of like。

😊，Like this exponential form of cosi， which has a negative frequency。

 You don't really need to worry about it。It's symmetric。 It's symmetric。 It's mostly symmetric。

 It's because it's just this complex number thing， yes。😊，是工上是。Since we're doing only wood。Re numbers。

 like real。It's always the metric and we can just cut it。Yeah， with images。 Yeah， yeah， yeah。

Po than那 might be。要。Its goodness。 Yeah， so the signal processing。

 I think if the signal is like moving also， it's also useful or something like that。 too。

 And there's this is a super deep subject。 I mean， for your transform。

 you learn and like many different classes， right， like analysis， you just like， prove it。

 And I I'm like， okay， And then in like signal processing， you get into this kind of like， you know。

 complicated things。 And then finally， when they came to computer vision， I was like。

 it's just linear algebra or just like cos， it's like a basis， it's just multiplication。😊，But okay。

 so if you look at this， Okay， let's go back to the thing that you don't need that many numbers to represent this one。

 because it's like a pretty simple curve。 there's no hard changes。Okay， but look at this one。

 There's lots and lots of high frequency changes。 Sudden changes。 Okay， sudden fast changes。

 So then this is why you need like many， many， many， many sign。😊，Over there。

 And that's this like another one。Okay， so this is what I mean by this is just a change of basis。

Okay， so。Suppose。The length of the sma。 So this is your basis。Okay， and this is your signal。Okay。

 that's like the ultimate。 This is like the coefficient。Okay， suppose your signal was length n。

What is this matrix， What is the size of this matrix。As a basis。 And then there's like F many。

 F many frequencies。This is in。N by one signal。So this， this would be。If you had as many frequency。

If by n， exactly， F by n， right， n by one。 And that will give you F by n， F by one。Right， like。

This is a lookup at every single frequency。 What is the value of the amplitudeted。O。😊，야。Right。

 you take this matrix multiply。 Does it actually match a lot。 Then you hold that value。

And then that's how you just compute your four year transform。And then you can do the opposite thing。

Which is to go back to the frequency。You can transpose that matrix。 You can take your forear。😊。

Fll function， which holds amplitude at every single frequency。 and you multiply this value。

 and then you get that signal back。Okay。Yeah。还有这两份。N is the number of length of signal。 The other。

 F is the number of frequencies。 you have S many basiss。

And then the image the signal is indimensional。Right， and then。This is， like。remember。

 we're gonna write it as a sum summation of amplitude。Let's just think about the amplitude。 right。

 summation of some sign curve multiply multiplied by some strength that I want。 Okay。

 so then if you take this， you're gonna be like the first value。😊，Over here。

 for all the different sign curves， I'm gonna multiply with this this amplitudeted。

And then you're gonna sum this。I think。Yeah， then you get the number back。But， I mean， it's not。

 It's only an intuition。 I'm just saying the scary ma。O。This is what it's exactly doing。

 Look at this。 This is the basis of that frequency。 Okay， you multiply with the signal。Right。

 that's kind of what's happening here。 right， Like you， you did that here。 You have a。

You have a basis。1，0，0，0。 You multiply that。 How did I get this is a 58。 Well。

 it's because I multiply this thing with this image。Right， and it's because it's 0 everywhere。

 Only one over here。 And this value is 58。 They got the 58 back。Yeah。

 and then you do that every single time。 That's how you get。 It's more like。

 how much does this basis explain my signal。And if it's like a high match。

 then that's the amount you want to keep it。 So that's what's happening for that omega。

 You multiply that signal。And then you just sum this up。 And that's your final， final basis。

 That's kind of like this part， right， becauseuse if you write it in。It's， it's in， you know。

 if in continuous space， it's like infinite。But。You know， it's a computer。 So you were gonna do it。

 So anyway， so this is like a scary mass that you see in your class。

But it's not that scary because this ex exponential of this negative number or imaginary。

 negative imaginary number， Oomega thing is just this cosine。 It's just this。

 it's just this complex number， real part and the complex part。😊，And it's hiding our old friend。

Which is that， you know， you can take the magnitude of this thing to get the a and you can take the angle of this。

 the arcton of this to get the to get the face。 This is basically the trick that I was talking about that math people like to do for their proof and other nice reasons and different and all the other parts。

😊，O。😊，It's really just our signal Time the sign at frequency W。 It's like， if I have a signal。

 how much of that signine curve should I use， right， And I multiply it， And if it actually。

 it's like convolution， right， you have all these pattern， you multiply it。 And if it's the same。

 you get very high pattern， high reaction， that's important because we're gonna implement these you can implement these as convolutions。

 you think about it。😊，Questions。诶。可是。It's， it's okay to ask questions， but the。有。You're kind of。Okay。

 okay， well， okay， okay， Well， let's look at it in images， images， okay。

Because images can also be seen as addition of signs and cosine。😊，Believe it or not like this image。

 for every single channel， you can just sum up all of these bases。Right。So like， what is this。

 This is 0。 This is constant。Okay， you take the average of this image and you first add the average。

Right， and then you add this sign and you add that sign。 this is this， this sign curve tilted。

 tilted different ways。 This angles。today。So。You can。 So， so it just， it now it's 2D。

 So the frequency can change in x。Right， this is like exactly like we've been seeing like over these。

 This is like， you know， getting more， more and more frequent。😊，And then you can also do it。 And why。

And because it's a， there's a combination of the po。Okay。So you can compute your four year transform。

So like this image。A lot of this thing is going on。 But like， so， for example。

 if I had a non zero value in this image， it means that I am using this basis by that amount。No。

 okay， question。Okay， if I have。Let's just focus on the， on this， this part。Okay。

 if this pixel is on， that means I am using this basis by this brightness amount。😊，Like this。

Probably corresponds to there。This is exactly the same as this。This image that we've been seeing。

Right in this image。You know that this girl。Is a summation of this frequency in that frequency。O。

That made in 2D looks like an image。Like this。Okay， maybe it's simpler if I show an example。

So this is， this is suppose this is an image that I want to encode using four your transform。😊。

Its pretty low changing， low frequency one。 So if you look at the four you is。It's very tiny。

 There's like a three dot。Because there is one for like the constant。 and then one。

1 sine wave is fine。I， I'll wait for questions， yes。いす。嗯。This is just the amplitudeted。

 I'm not showing you the phase image， Just the amplitudeted。

As in how much of this each s sine wave am I using。Yes是 when。雅雅。It's not that the face is different。

 It's just the basis is rotated。Like it's not a phase shifts。 So you can also shift this one， too。

 but it's just because it's 2D。 There's a component that， you know。

 there's a vertical sine wave and there's a horizontal sine wave。

 And there's also this like fled sine wave。😊，嗯。That's your basis。 Like， yeah， like you're gonna add。

 you're gonna add some amount of this image。 You're gonna add some amount of that image。

 You're gonna add some amount of this image to make your final image or like in all of these bases to add your final images。

 So no faces involved or like， even in amplitudeput domain， you want to add this one。 So like。

 for example， we will see later， if like an image has a lot of diagonal component。😊，Right。

 then you want to use this basis a lot。And you w to use the face to like， shift that。

Rotation analog rotation， analogous to frequency。 So I think it's it's more like it's just like。

 it's just like you take this one and you rotate it by 45 degrees because this is like equal amount of like horizontal and vertical。

 But if you went down， you like you approach you， you know， you do more， more of this。

 It's just like a weighted， weighted sum of these two。😊，You。

 you see what I mean that So diagonal of this image is always going to be like the 45 degree diagonal。

 And as you go like down， it's gonna approach or it's gonna， it's gonna be like more and more of the。

😊，Horizontal side。 And then if you go this way， you， it's gonna be more and more of the vertical。

It is a weighted， weighted combination of the X and Y， because it's a2D image。Yeah， please。Oh， you。

 you don't need to rotate them。 They're already rotated for you。 The basis is already rotated。

They are representing the frequency， which is your basis。你说。You know， so because over here。

 your basis was ones and zeros， right， And in one these signal， your basiss are one one sign。

 one type of sign curve。😊，And more in intense than I。So these are just your basis in 2D images。

 This is， you know， one sign curve， but oriented in this horizontal way。

 is we got get more and more and more high frequency over there。😊，And then these are just， you know。

 rotated bases。 Ims are rotated。 It's just， it's， yes。Exactly。

 this thing is telling you how much of that。Yeah， so like this image is saying how much of that particular locations basis。

I want。あ、開げていた。Yeah， yeah。 Okay， good。 in four your in is is the response of the amplitude。

 like how much amplitudeted。At every single frequency you need。

 So this four year image is exactly the same as this frequency spectra， but in 2D。😊，Yeah。

 it's this image in 2D。Is this for your image。电动。Yes， exactly。

 The intensity of the white is the height of that particular sine wave image。That you're gonna add。

 perfect。う実際。三只。Exactly， exactly。 So the higher you go， the more high frequency it is。😊。

The Xs or like the， the， the， the， I think in this case。

 it just makes sense to look at the fourth quadrant。And then every other quadrant is imaginary。

It it's like in， in this， in this 2D， we talked about how like， you know， it's。

 it's like's like an artifact of using complex numbers。 There's no such thing as negative frequency。

 But we have to represent it this way because we're writing it as a complex image。5。Yeah so。嗯。

Is there some sort of。W to tell which。They see have the same frequency， but I just wrote。Good。

 I think everything。Like over here， like everything on the row or the call like everything。

 everything on the column。Is the same， no。I think it's every。

 this every like square access is a good is， same frequency。可以。Yeah。

 I think it's like this this is why this is like 45 degrees。

 So you take this much and that much and you get this like。Like， it's like a s。Function。

 this is like the identity。 But then like， as you go more and more this way。

 the frequency in gets stronger and stronger。 You're just rotating always by 45。😊，If I wanted to。啊。

The very first one on the top。But I wanted to rotate some numbers in you。

How could I do that because I don't know。I don't have any。命電の時態。I think it's this。

 this is this is this is this these two， I think， are the same frequency。

 It just doesn't look like it。Yeah， yeah。 I think these is。哎呀。😊，Yeah， I think like。

 if you looked at this image is the basis corresponding here。

 it might be like something in between here because this isn't really exactly X。 Yeah。

 because this is like dense image， dense yeah。😊，O。Pop left the bottom right。Oh yeah， yeah。 I mean。

 yeah。 I mean， this is why you look at this。 This is why you're gonna get this like weird shifting thing that you need to do because everything is kind of done in this like fourth quadrant。

😊，So you gotta like shift your images to get to that quadrant Europe are mostly thinking about it and that。

So， so if you see more examples， hopefully we will see。Okay， so like let's combine this like。

 so this was the four year， four year image。 You say four year image because that's the response in the four year spectrum。

 Four year four year series， right， So， so this is this is called like the frequency domain。

 spatial domain。 We'll see more。 You can add them。 So you can simply add the amplitude be like this image needed that those amplitude。

 This image needed those amplitude。 They're not the same。

 But I'm just gonna combine those amplitude in a single single image。

 I'm just gonna add these things。 And then read it back。 Then you can actually combine these signals。

😊，Would start to think about like， you know， how we were making the Dali image in the be。

So let's look at this picture， just as an example。Wah， okay， so this is amplitudeted spectrum。

Can we describe。What these， you know。What that， what， what， you know， like。

What each thing corresponds to what。big。Yes， exactly。 There's this like very strong edges， right。

 And again， the edges is super high frequency。 So you need lots and lots of numbers all the way over there。

😊，Yeah， and then like this horizontal， too， you see some maybe not as strongly as the。This one。

 but you see some， you see some horizontal line。How about this， this vertical， this。

 this kind of line that's like negative， negative slope or this line。 What。

 what does it correspond to an image。Like this one。Yeah， exactly。 And then maybe there's like 2。

 two slopes， right， Like， there's this the oriented line and that oriented line。

 Maybe those are captured by these two things。😊，Okay， yeah。我的。Or like over here。Can you point。top。

Top right。To the bottom left。我的我的就是。We so we should really only be looking at this this quadrant。

 Yeah， they they don't really exist。Yeah， yeah。 the， the the the useful analog really is in this。

 this， this this quadrant。So， you。Could have that， too。 It's a little bit of a weird image。

 but those could be the responses， too。So this is the， this is like the magnitude。

 this multiplied by this sets of bases， create the image。😊，You see， I mean， not the negative。 not。

 You mean， like not the other way around。I see。大着。Good question。Somebody can answer。

 how do we represent the lines in the other way， I guess it。Like。

 you would think that that direction would be that。

 So maybe that's where the negative uned actually comes into play。Not a quadrant。被告。关键。long white。

Yes， yes， yes。 You're right。 You're right。 You're right。 You' right。

 because we're really kind of looking at this way。 But if you started looking at that way， that's。

 that's the oriented version that you want。😊，Yeah， yeah， yeah， yeah。 Yeah。

 So I think it is also the half。That's kind of what you're saying， right？ Yeah， I agree， I agree。

 I agree。 Yeah， yeah， yeah。Yeah， you， you do， you do look at that whole like half of it。

 It's symmetric in one direction， but yeah。これ学会。what。If you。So technically。

 whenever you have like hard edge， you should be using infinite。Yeah， so you could go outside。

And like， if you， you can specify in your F50 that I really want high resolution so you can actually use the number of bases。

 like many， many， many number of bases。😊，But in， in general， because computers are discrete。

 you're not gonna use infinite number of bases。 And so there's some cutoff。周位。took one of that way。对。

Yeah， exactly hardline。 And this is kind of close to that hard line。Like a step function。

 like whenever edge， any edge， basically any edge in the image will require this month。他不去。对。Right。

Right， exactly， exactly。 we're running out of time。 But because I have some demos that we want to do。

 nobody is asking a question which is like， what what， what does phase look like。

 Where did the face go。😊，Okay， if you have that question， it looks like that。Okay。

 it's not that visually informative。 It's important。So phase really captures like phase， you。

 how did I get this you got this as an angle of like， you know， arc town of these complex numbers。

 And phase is important， too。 It's like， it is very important。😊，So you can actually take this image。

 compute magnitude and face and swap the magnitude。😊，Impled。 okay， of these two images。

 and then we render it out， but using the same face。And you will see that， this image。

Still looks like that input image because face is what captures this kind of like spatial information。

😊，Okay， but the amplitudeplted is what has the frequency information。

 So that's what we're going to have conversations about。But， you know， it's， it's also important。

Okay， so。Now that we kind of understand this picture。

 you can start editing it and get different kind of things。😊，Okay， so like in this picture。

 everything in black means 0。I took this shape， and I zeroed out this amplitude in it。

 and then reconstructed it。 like， what， what happened。What's happening when I get rid of like。

This part。有。I heard something。The columns are removed。 Yeah， they're removed。 They're turned to 0。

 What does that mean。呀。Exactly the horizontal amplitude went to 0， which means。

What did I do to those。You know， those frequencies are 0。呀。Yeah， you remove， you remove that basis。

 So this is why when you reconstruct it。Horizontal direction corresponds to vertical basis。

 And I got rid of all of these。 I turned them all 0， even though I needed to use。

 use that to reconstruct this image。 So you can see the horizontalal stuff went away。😊，Right。

So you can do this kind of a very， very like， you know， rogue， it means processing。Like this one。

 too。So what， what does this get rid of。Yeah， diagonal mine is exactly。 So then this one is gone。

And then that one takes away this one， and so forth。So。If you wanted to do low pass filter。

 now that you know， what shape would I multiply this amplitude with。Orally， yeah。Exactly。

 so if you take this image and if you take that， if you zero out everything outside that circle。

 I'm just saying all of those high frequency components。 I'm just gonna remove them。

 Then I get to this， like， blurriier image。😊，Conversely。

 you can do high pass filter by getting rid of all of the low frequency information。😊。

In this amplitudeputed domain and do this kind of surgery and then get this image back。Question。

So the spectrum。It's the strength， amount of coefficients you need for every single。

Sine and cosine basis。Yeah， so it's not It's no longer about RGB。

 but it's about which frequency do you need。Okay， and I want to get to the demo。 I mean。

 I think we have some， okay， more any questions before I move on， because this is kind of important。

 yeah。すい税じ。3。Yes。😊，Yes， yes。 good。 Yeah， everything right now is like gray。 Yeah， So this is just1。

1 great，1，1 thing image。😊，Yeah's basic。 Yeah， Yeah， okay。😊。

So the key thing is to remember that this is the coefficient。 the0 means not using the basis。

 One means using the basis。 And this is high frequency regions。 The further away you go。

 it's high frequency。😊，Okay， so now then we can finally get to this convolution theoryorem。

 which is kind of what we've been seeing already， which is that。😊，This is。

 there's lots of all of these math。But basically， what we say is the convolution in the spatial domain。

 The spatial domain is our usual， usual image， like X， Y。 Okay。

 the convolution in the spatial domain is equivalent to multiplication in the frequency domain。😊。

Okay， so what does this mean， which means that you can take an image。Convolve it with a Gaussian。

 like we've been doing this， this line。 Okay， it blurs image。Instead， you。

 you can go to the fourer domain， which looks like this。

 This image is now looked like this or represented by this， you know， representation。

 which gets multiplied by all the signs and cos and basis。Im nothing to multiply it with， with the。

 with the for your transform of this Gaussian。 and Gaussians are nice because Gausians。😊。

In spatial domain， is's also Gaussian in the frequency domain。

 except it's just the width they're different。 And then you multiply theses like we just use the circular thing to cut it out。

 And then you can like， get rid of the high frequency component。 And if you read it。

 if you did inverse FFT， youll get this image back。😊，Can somebody describe why this is， this。

 this Gaussian is pretty peaky， right， It's kind of small， right？ Why is it kind of bigger。

In the frequency domain。Why does that make sense。Like， think about。What about as I， as I like。

 as I make the sigma approach 0。This thing get peaky and peakier。

 What's gonna happen to its four year transform。あ了。Okay。

It's it's good that you're thinking about it this way。 But let's try thinking about what does。地きが先て。

Or like， if they become super， super peak， right， then it's unit impulse。

 unit doesn't change anything。What do I need to do to not change anything in here。

It's kind of maybe that's what you mean， maybe by using a lot。Anybody。呃，Yeses。The is like a higher。

はる。Moer。More。啊。It's yeah， oh yeah， you exactly。 So， so super， super small dot。 Okay。

 there's no smoothing at all。 right， So the image is exactly the same。 right。

 So then this should be really all once because you don't want to change anything。😊，Right， now。

 like a really， really big Gaussian is gonna smooth a lot of the things。

 which means it cuts a lot of the high frequency。 So that means you really don't want。

 You only want to keep tiny， tiny circle。You， you， you you see that relationship。Kind of here。 Okay。

 so now with this analysis， we can get to this like really cool thing about how。

 you know how we with the Gaussian， we didn't see any kind of like weird artifact。

 But with this like box filter， you saw all of this like weird stuff。

 we can analyze this using this kind of same intuition or using this toolbox。

 It's not inition anymore。 So if you use this box filter。 again， yes， so represent this box filter。

 you need the frequency domain representation of this box filter， this sink function。

 which is as like infinite response because the edge needs infinite number of signine waves。😊，Okay。😊。

啊。But that's not really good because it this thing， when you multiply this thing with a signal， it。

 it's keeping the high frequencying component。Right， this thing function。

Right because like the high frequency component is somewhere like non like， you know， positive。

 right， So this is why you kind of see this ringing artifacts when you use the box filter to see。

 to filter this image。😊，Gaussian is nice because like， you know， this flat Gaussian， as we said。

 is a tight Gaussian in the， the more low path the smaller it is in the frequency domain because you only want to keep those frequencies。

 low frequencies。 But these are same numbers。😊，Or similar， it's the same Gaussian。Or it's like it's。

 it Gaussian just different width。Now， the box filter is actually the ideal lopz filter。😊，Right。

 because it's like， I'm only gonna keep this much in the frequency domain because because the best thing I can do is just look at this image。

 and this is circle， but actually it could have been square。

 as just square is best because square only keeps the frequency at that， at that range， okay。😊。

But that perfect lous filter in the frequency domaint like right。

 because I'm setting everything0 outside this， like all the high frequencies or0。

 only the inside frequencies are positive But this box filter in a spatial domain。

 If you were to implement this as a kernel， has to be a sink filter， which you need infinite kernel。

 and you can't really do that in like a call convolution because your kernel is not infinite right。

 And so this is why Gaussian is such a nice representation， because it has， you know。

 you can cut these things off here， you can still use it。 unlike the sync function。

 where you have to have like infinite stuff。😊，So， that's。Really。Question。呀。楽しで大。呀。

You can't cut off the thing。 But then because this does need this infinite thing that。

 But then it actually has this kind of impulse thing that you。

 you're gonna either overshoot or undershoot。 Then that's gonna lead to artifacts。

 as opposed to Gaussian is like， you are also cutting it off。

 but they're like infinite going to infinitely 0。6十八。You can。 You can。

 So that's the one way of doing lowpa filter， which you can implement it in your thing。

 And maybe I can do it in the demo。 But the problem is。

 then you have to compute the Four you transform。 is it just expensive。It's just， if you had compute。

 you can do it。Okay。So。That's kind of being described over here。 But maybe let's just go to the。

 let's just go to my demo。O。Alright， let's do this。How do I display now。Mirrred。

And then I hear all of you guys use V S code or something like that these days。But I am a。

You can see how Emax works。Vim， did I hear that right now。Or okay。So this is今。Okay。Okay， so。

 so above here is my show。😊，Okay， I'm just gonna run run this for year。4 year thing。That I wrote。

And I'm gonna。 we're gonna use this as a cat total。We're gonna convol。

 We're gonna look at the four year transform of his faith。Okay， here you go。 See this is。 I。

 you see this， right。 I I， I， I put the PDB here。 So right right now， we're here。😊，Okay。

 this is why I'm doing。 Is this big enough。Yeah you see， right。Okay， but now everything is。

 everything we do is in gray scale。 So I'm just gonna run this。😊，To make it great skill。All right。

I don't really like this color map。 So I'm just gonna make it gray。Okay， okay。

 now I'm gonna compute this FFT。 This one is in your homework， too， But because FFT assumes that the。

 what the center is that the 0，0， you have to do this like shift thing。

 You can I can play around with it later。 but you can just run this。 So there's a shift over here。😊。

Okay， and then there's the FFD over here， and then you shift it back。Okay， so now what is F。

If he has， if this is an image that stores these complex numbers。Right。

 and I'm gonna compute the absolute value of this。That's gonna take make it into an amplitude in the phase。

let me just run this reconstruction thing， too because you're now going back now I'm doing I SSSD。

Okay， but if I visualize this。嗯。So that that's， that's the that's the amplitudeted。

And that's the image。And that is the reconstruction， lossless， perfect reconstruction。Okay。

 that's the phase。And that's that amplitudeted。 I mean， like， you know， you。

 I think he has some vertical lines over here。So you see this very good yeah question。What with like。

周way。okay， you're right。 technicalically， if this was super high frequency。 like over here。

 I even need infinite。 So there， there is some loss in frequency。 but I I we can't visual。 we can't。

 We're so not sensitive to it。 It's like the the first curve that we started with。

 So this is why we don't really see it。😊，But good point。Okay。Now。

 I am going to do a robot bus filter。By drawing this mask that is colored。So。I just made this thing。

ThatThat looks like that。O。😊，And I'm going to multiply that， withoutva。And then you which。

 which looks like this。You need the log scale because it's otherwise it's like， you know。

 the high high dynamic range is just so hard to see。And then you can combine it。

 And then the way you combine it is that every complex number can be written as this R multiplied by like the exponential of this inverse the theta thing。

 So you combine it into a complex number again， using the exact same phase。😊。

And then you run this back to I FFD。And then you're going to get this。Low bus filter。

 So now you can see that it's a little blurry。Oh， I made a mistake。 It's not correct。 This is。

I'm just， it's not phase。 This is the low past filter third phase。And I feel there uned。In this one。

O。This one， because everything else went to 0。 It's now shown ass white。 Okay。

 I can change this radius to like 10。😊，Run this again。T this again。

And it's gonna get even more blurriier。ok。Alright。One more thing。I have this。 My friend has this dog。

If you're a dog person。啊。It's called Rady。Riding such a cutie。And。


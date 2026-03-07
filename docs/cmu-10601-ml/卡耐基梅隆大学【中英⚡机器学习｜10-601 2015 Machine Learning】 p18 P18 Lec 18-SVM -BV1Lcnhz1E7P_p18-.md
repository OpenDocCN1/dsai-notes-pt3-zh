# 卡耐基梅隆大学【中英⚡机器学习｜10-601 2015 Machine Learning】 p18 P18 Lec 18-SVM -BV1Lcnhz1E7P_p18-

Alright， cool。 So as I promised last time today， we finally talk about S VR support vector machines。

 which is one of the。😊，Cooler algorithm machine learning。 It's by our classic algorithm。

 It operates under the assumptions。 it operates under the usual supervised distribution or supervised learning setting。

 So under the assumption that all the data is fully labeled for us。

 So all the data assume that all the training data is fully labeled for us upfront。😊，And。Right。

 so it' is motivated by margins and kernels。 as we discussed last time。 Okay。

 so go for it in detail today。 but we'll also start talking about more modern approaches to supervised learning。

 where the data is only partially super we only have partial supervision as opposed to full supervision and I mean。

 as you as you see。 I mean， this is super well motivated and very important topic in modern machine learning in the age of big data where you have so much data that is basically hopeless to label it or。

 Okay， and we'll start talking about semi supervised and active learning。 And actually。

 in particular， we're gonna talk about one of the elements we're going talk about today。

 semisvised SM。😊，Okay， so everything fit's all together。Great。

 so let's go back to the classics for now and talk about SVMs， right。

 So SVM is one of the most theoretically well motivated and practically most effective algorithm in machine learning and。

😊，It is directly motivated by the concept we've been talking about in the last couple of lectures。

 namely by margins and kernels。😊，Okay， in particular， just， just a very quick recap。

 because this will be crucial for the class today， The notion of margin I've been thinking about is geometric margin。

 Okay， and you guys remember what is a geometric margin。What is the dramatic margin？

So if I have a separator given by normal vector w and the point x。

 what's the geometric margin of x with respect to that point。I'm sure you all know。

It's just a too simple of a question to answer。Yeah。食。Yeah，所以。So if you had the， okay。

 so you're answering a complicated question。 Theyre answering。 if I have a linear separator。

 give what is the margin of a linear separ to a set of points。

 What is the distance from the closest point is a separator to what separator。 Okay。

 so answering that question。 Okay， yeah。The mic is not on。It should be。You guys can hear me。Strange。

Maybe the batteries are running out。啊。What's going on here。Okay， now I need some tech support。

So let's see who is helping me Tom to help me put new batteries。Okay， great。 So， okay。

 speaking loudly。 So what is a margin。 So is just a quick recap。 you guys know。 So right。

 just even going from a even simpler concept。 So if I have a separator given by a normal vector W。

 the margin of an example X respect to a separator is basically how far my example X is from that separator。

 right， And we argued in the class previous， we can always think about separators that go through the origin because we can only translate the origin。

 right， So this I'm gonna be thinking about today， separator that go through the origin。 Okay。

 and so in that case， if I'm think about the separator that goes through the origin。

 And if my separator is specify by normal vector W， right， then the margin of an example x。

 respect to a separator is exactly the distance from the example x to the separator。

 and we seen this last time， this is mathematically the same as。😊，What's going on with the。

Connection here。ForBut reasoning law。 Okay， all sorts of technical problems today。感です。Okay。

 but luckily， I got。This surrounding but that me。ItGo here。Great。Thank you。Hi， okay。

 that's much better。Thanks， Tom。All right。Right， so we are thinking about separators that go for the origin。

 and we are thinking about geometric margins。 So if we have an example。

 if we have a separator given by normal vector W， the margin of an example x respect to a separator is simply the distance of example x to the separator。

 And if we normalize the normal vector to have norm one， which is we can always do all of generality。

 when mathematically， the margin is exactly the absolute value between that example。

 the absolute value of the dot product between that example and the normal vector。😊，Okay。

 now we will become important you put down the S VM algorithm， right。

 So you is an attack to remember。 Okay， and it's something that you learn in the 11th grade or something like that。

 Okay， so geometric fact。 good。 So that's the margin of an example X with respect to a separator given by normal vector w。

Is the absolute value of the dot product between W index。Okay， now， as your colleague said。

 and your name is。Peter， yeah， as Peter said， right so now。

 so I just defined the margin of an example X with respect to a separator。

 But now if I have a set S of examples， the margin of a set of S of examples。

 with respect to a separator is simply the minimum is the smallest margin of an example X with respect to that separator。

Okay， and now I can also talk about just the margin of a set S。

 which is when just the maximum margin of a separator of within a separ respect to what set S。

So I search for all possible linear separators and I take the one of maximum margin。

 the margin of a separator of my set is exactly the margin of the set。

 Okay And we've seen last time that margin is an important concept in machine learning。

 it has interesting simple complex algorithmic implications。

 So we've seen that if the data truly has a large margin or nearly a large margin。

 the number of mistakes that the percept algorithm makes depending entirely on the margin and it's independent of the dimension of the ambient space。

 and it's also independent of how long the synco of examples is right So if we have a large margin。

 It's a great tool for perceptron， right。😊，And so right， if we have a large margin。

Then the perceptioncept algorithm behaves well。 But we've also discussed that actually。

 if we do have a large margin。 this perceptioncept algorithm is in the original form。

 it's an argument in the online learning scenario， right。

 But we've also discussed that people analyzed the implications of margins in the more classic distributional learning scenario or the data is all labeled for us upfront right。

 And weve discussed that intuitions behind the following type of statement。

 So we said that it was proven actually by Pk in the 70s and very proven in the forms by various people。

 including Peter Barlet and Josh Taylor， So it was proven that if Man distribution truly has a large margin or nearly a large margin。

😊，Then and if I have an algorithm that is able， given a set of examples that algorithm is able to produce a large margin classifier。

 which one exists now， because I know that the underlying distribution has a large margin。

 So any sample， gonna have a large margin， right， So if my algorithm is able to produce a large margin classifier。

 When I know that the number of labeled examples I need in order to achieve good generation guarantees is small。

 it depends only on the margin。 And again， this is independent of the dimension of the MPn space。😊。

Okay， so this is a very interesting simple complexity statement。ItKind of cool to， to know。

 And actually it has immediate algorithmic implications。 So this simple complex system and this。

 this type of guarantee actually directly motivated the support vector machines algorithm。

 the SG M algorithm。😊，And basically， what this simple complexity statement implies or this statement implies that somehow it's a good idea to search for separators that have a large margin。

 right， because we know formally， but they are less prone to overfitting。 Of course。

 we can come up with some intuitive argument， too， and people do this all the time。 you know。

 somehow。 But this is a totally formal sense in which is a great idea because formally， you know。

 they are less prone to overfitting。😊，And also， it makes sense intuitive， if you want to。

I typically attach to formal facts。Okay， cool。So。But this is vacuum movement。

 also gonna go through the deri of the support based machine algorithm。

And what the algorithm just does， just search would search for a class of a large margin。

 given a set of examples。 we' are gonna search for a class of a large margin。Okay。

 we're gonna go like slowly through the actual， some of the actual derivations。

 because it's a super important algorithm。 Its another that you definitely want to know。

But all the details will now be simple because we've spent a couple of lectures talking about Martins。

 So hopefully， you'll be able to follow。I think we keep could be。

 the details could be a bit scary at first。 if we have not seen margins and we have not be thinking what they mean。

 But after our preparation， I think we should be able to。Girf。Alright， so what we're gonna do， right。

 exactly， we're gonna try to find the classifier with is a large margin。 Okay， and for simplicity。

 just to start simple。😊，Let's think about the case on the data。


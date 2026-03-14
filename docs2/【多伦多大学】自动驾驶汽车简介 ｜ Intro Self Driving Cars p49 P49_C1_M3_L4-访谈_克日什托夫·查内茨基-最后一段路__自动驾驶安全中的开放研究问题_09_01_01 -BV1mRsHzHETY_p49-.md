# 【多伦多大学】自动驾驶汽车简介 ｜ Intro Self Driving Cars p49 P49_C1_M3_L4-访谈_克日什托夫·查内茨基-最后一段路__自动驾驶安全中的开放研究问题_09_01_01 -BV1mRsHzHETY_p49-

![](img/32c479dd9effd8a43d9a84e12f9eb133_0.png)

So now that you have this car， this Saana Moose that's been on public roads for over 100 kilometers。

 what are your plans for the next few years， what do you think are the key research questions that you're hoping to answer？

So the key research questions are， well， first of all， in terms of safety。

 safety of machine learning， that's a big， big topic。 And we don't really have yet enough experience。

 So theres actually some fundamental。Work that needs to be done to address this。But also。

 behavior in traffic。 it's a big topic。 So， you know， we， we know that。You know。

Today it's challenging because you have human driven vehicles and you have to interact with these vehicles in traffic in crazy traffic that's maybe not structured and so on。

 but even if we had all automated vehicles， we would still have pedestrians we will still still have bicycles and so these things would make it difficult in terms of prediction what they do there's。

Ideas such as。Robot bullying and pedestrians， for example。

 getting just taking away from autoous vehicles because they can。

 and we assume that these vehicles would stop for them。

 how do we address these problems that's a challenging。And so is it these super complex cases。

 have 20，30 cars at intersections and pedestrians walking in all directions。

 is that what's holding back the release of autonomous vehicles。

 or is it something more fundamental about how we design these systems or I guess the infinite variations that they can come across。

 is it just the last edge of the capabilities or is it really just that we can't actually determine if we've done enough or if we have all of the situations covered？

Well， we do see that the last few percent， if you want， of。

 the required performance are the most difficult to get， right。

You can get it to a point where you might。Right，10000 km between disengs。 but there will be always。

New cases， right， and in a sense， we sometimes。Talk about this as de long tail distribution。

 meaning that there might be actually 50% of the。U。Critical cases can be in that long tail。 And。

 and so it's really the question， where do we stop， So we have to work on。

 on methods such as accelerated testing， which through kind of robustifying or robustness testing。

Or searching for these credible but still difficult scenarios。

That we can go and address them so and you know humans as the drivers bring with them an entire representation of the world。

 they've lived in forever， they know how people behave。

 they know how vehicles are going to drive to an extent that doesn't seem that you can encode entirely in software I this a machine learning problem that we can solve is this something where we simply just seeing enough examples and filtering out for the ones that we haven't yet addressed correctly are we going to get all the way there or always going to be new variations to keep us from finishing it's a great question and it's an empirical question so you know I cannot give you an answer until we actually have done it right it's going to be in the testing we do see that with machine learning we can get it pretty far we also know that。

In some of these cases where machine learning fails or today's machine learning。

 that it's sort of brute force pattern matching， if you want， pattern learning and matching。

 and whenever it fails，Humans usually deploy some kind of a higher level。Thinking， right。

 So we just recently on our。Test track， we were testing object detection and avoidance and so our engineers just you know they had to set up a static obstacle and what they did。

 they just took a table and two cheers and they set it up in such a way that actually accidentally。

 looked like a car and so our classifier said， well， this is a car right and。You know。

 in terms of patterns， you know， with low relatively road resolution。Lar， it kind of looks like that。

 and it really would be very difficult to avoid that。

 A human would would have a different hypothesis。 would say， well， this looks like a chair。

 This looks a table。 that cannot be a car。 So you know the sort of common sense is lacking。

 And I don't think that will be addressing this anytime soon。

 So so it's going to be sort of the kind of brute force lots of patterns。

 And I think that we will be able to address a lot of the。Functionality need。

 but it will be always these cases， which we will have to address kind of。Perhaps by， you know。

 cuing the。Traffic control， and this has huge implications for the safety assessment for these vehicles。

 So machine learning systems only really can represent answers or identify answers that they've seen data from previously。

 right， They can't necessarily extrapolate and make common sense inferences based on things they've never observed。

 So how how do you address that。 How how do we make a safety case about a machine learning system where we can't necessarily explain how that system is thinking。

So making a safety case。 and that's a great term。 know this is I the approach taken to safety critical systems where you think about the overall methodology。

 you think about the architecture。 but in the end， you come up with safety argument safety cases or safety argument where you say。

 I thought about all the things possibly it could happen。

 and I have evidence that I've just addressed all all of these cases。

 So safety cases for any complex systems， particularly when when it involve software and data in the end。

 rely on rigor。 So you have to show that ir rigorously。Addressed all the aspects that could have。

LED to hazards。 And so for machine learning。The the key is， is the design of。嗯。Training data set。

 making sure that it actually covers all the relevant cases。

 And that's where the validation comes in。 That's why you need those thousands of kilometers to understand what the real world distribution of data is。

 And then essentially， you have to make sure that。Your， for example。

 perception has satisfactory performance。 And here we basically take a subset of that and say。

 well that part of the performance is critical to safety。 and you have to show that that safety。

 critical performance is actually given。 So then you have to look at all the factors that could influence that safety critical performance。

 and this could be things like not just maybe insufficient coverage of data。

 but it could be changes in sensor， calibration， for example。

 it could be something that impacts the scene， maybe visibility， can be also errors in data labeling。

 So we have to look at all these factors in how they influence the uncertainty that the machine learning is in the end。

That's something thing they do well with。

![](img/32c479dd9effd8a43d9a84e12f9eb133_2.png)
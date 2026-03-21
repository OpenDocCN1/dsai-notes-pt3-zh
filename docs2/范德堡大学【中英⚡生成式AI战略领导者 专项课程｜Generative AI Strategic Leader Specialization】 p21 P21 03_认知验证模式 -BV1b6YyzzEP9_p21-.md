# 范德堡大学【中英⚡生成式AI战略领导者 专项课程｜Generative AI Strategic Leader Specialization】 p21 P21 03_认知验证模式 -BV1b6YyzzEP9_p21-

An interesting property of large language modelss is that in many cases。

 they can actually reason better if they break a problem down into a bunch of smaller problems。

 so sometimes they can even reason better if they explain their thought process。

Now there's a number of sort of hypotheses about why this might be， but I think intuitively。

 if we can think about， you a large language model may have seen particular problems broken down into a series of steps。

 so if it can go and follow the individual steps， it will know what to generate next in order to produce the output that's needed to solve a particular step。

Now that's going to be discussed later in the course these ideas of breaking things down。

 but right now we can actually tap into a simple technique。

 a simple pattern to help us with automatically breaking things down to try to get better answers out of large language models。

And a simple way to do that is just to ask the large language model to always take questions or problems and subdivide them into a series of individual questions or subproble that could be useful in answering the overall question or in solving the overall problem so we can simply program our large language model to do this。

 Now， the cognitive verifier pattern is exactly for this purpose。

 What we're going to do is we're going to tell the large language model whenever you ask a question。

 follow these rules， generate a number of additional questions that would help more accurately answer the question。

 combine the answers to the individual questions to produce the final answer to the overall question。

Now， again， sort of intuitively， we can think about this。

If we have a generic question that we or some particular question that we ask a large language model。

 it can go and tap into what it's seen， the patterns it's seen in the training data to see what are other questions that are often related to this question so one it can help it sort of think about you know or collect from its knowledge base。

 other questions that would typically be associated with that question and when it's fine in these other questions。

 there are likely to be other questions that are relevant to that question will provide additional details or context answer the question。

And then when we go and give answers to all of those individual sort of sub questions。

 it's then going to have additional context to give us a better overall answer。

And it also helps us as the users to structure our thinking。

 because when we go and ask and it begins breaking questions down。

 it'll help us sort of realize what are additional dimensions to the problems。

So let's take a look at this in practice， so here I am I'm saying when you are asked a question follow these rules。

 generate a number of additional questions that would help more accurately answer the question。

 combine the answers to the individual questions to produce the final answer to the overall question。

And chat GT in this case says sure I can do that。 Just let me know what the question is。

 and I will generate additional answers。 So let's see what we can start with。 Well。

 I thought of a question that I have no way that easily answering。

 And I don't know a whole lot about it。 So I figured by asking a question that's sort of I'm guaranteed probably to ask a question that's too generic and doesn't have enough information。

 This will be helpful to me。And so I asked Cha GT how many mosquitoes probably live in my front yard？

I don't know the answer to that question， I didn't think too hard about it。

 but I'm kind of interested what is the answer to this。

 how would I even figure this out and so I asked Cha GBT that question and so here's what it says。

Well， it follows our prompt pattern， it follows the cognitive verifier pattern and it generates a bunch of additional questions。

 let's look at those questions。 What is the size of your front yard Well。

 obviously that's really important if I have a bigger yard I'm likely to have more mosquitoes probably it's probably related to the square footage in my yard。

What is the climate like in your area？That's obviously really important。 You know。

 if I live in the desert or if I live at the North Pole。

 it's unlikely that there are going to be any mosquitoes。

 What time of year is it Another great question， you know。

 I didn't think about that dimension to it when I ask the question。

 but I'm probably asking the question when I'm in the spring or summer when there's a lot of mosquitoes floating around in my yard and it's driving me nuts。

 but I'm not thinking about I need to include time in my question as well。

 Are there any bodies of water or standing water sources in your front yard or nearby and obviously that's an important whenca mosquitoes breed in water。

 and I actually knew that， but I didn't include that information in my original question。

And then are there any plants or vegetation in your front yard that mosquitoes are attracted to？

That's another important one， so we see now it's taken my original question。

And it's broken it down into a bunch of sub questions that are going to help it answer the original question。

 This is really useful。 And I've also learned something。Now to answer this。

 I'm just going to go back to it。 if you'll remember it had a series of questions went through five。

 I'm just going to go now an answer with one about 2500 square feet。 I honestly don't know。

 but I'm just sort of guessing my yard's not that big in the front yard。

 This is probably actually an overestimate of the size of my front yard。

 I live in the southeastern United States。

![](img/83ce094cc625bf4f6e6f0cc06fe34cb2_1.png)

![](img/83ce094cc625bf4f6e6f0cc06fe34cb2_2.png)

![](img/83ce094cc625bf4f6e6f0cc06fe34cb2_3.png)

![](img/83ce094cc625bf4f6e6f0cc06fe34cb2_4.png)

It's April， I'm not telling it。

![](img/83ce094cc625bf4f6e6f0cc06fe34cb2_6.png)

You know， seasons or things I'm just going to give it the month。

 which probably isn't specific enough。 There's probably a difference between the date and different times within April。

 even within where I live then I tell it no there's no standing bodies of water in my front yard and yes。

 there are you know plants that likely mosquitoes would breed in and so then it goes and says based on the information provided here's an estimate of how many mosquitoes living in your front yard and it gives me a number of things it says with a front yard size of 2500 square feet according to some estimates。

 a single female mosquito can lay up to 300 eggs at a time but it says in another things and it kind of goes on to hedge its bes。

 which is a good thing right it says in general a typical mosquito population density in an area with standing water sources can range from 10 to 100 mosquitoes per square meter。

 however since there are no standing water sources in your yard or nearby the density。



![](img/83ce094cc625bf4f6e6f0cc06fe34cb2_8.png)

![](img/83ce094cc625bf4f6e6f0cc06fe34cb2_9.png)

![](img/83ce094cc625bf4f6e6f0cc06fe34cb2_10.png)

![](img/83ce094cc625bf4f6e6f0cc06fe34cb2_11.png)

![](img/83ce094cc625bf4f6e6f0cc06fe34cb2_12.png)

It could be lower。And then it goes on to say it's difficult to provide a precise estimate。However。

 it's possible that there could be anywhere from a few dozen to a few hundred mosquitoes in your yard。

 depending on various factors， ass a species climate in the presence of vegetation。

 That's pretty good。 The fact that it's gotten this down to a few dozen to a few hundred。

 That's a tighter range than I would have expected。

 and also just sort of sets my expectation in the middle of summer when I go out in my front yard。

 I would swear it was in the thousands。 I'm absolutely dying as I'm eating alive my mosquitoes。

 and so I typically think it's a much higher number but you know based on this， it may be wrong。

 It may be erroneous， but it actually gave me from fairly good reasoning。

 One of the things that's also nice about this is I'm less skeptical of its answer being completely wrong because it asked me a bunch of reasonable questions to drive its answer。

 It also gave me a bunch of facts， which I could go and follow up on like how many eggs of female mosquito leave will lay the density of mosquitoes in areas with。

Wat， but it gave me a kind of a pretty good answer and it gave me a bunch of of questions that I could ask to improve that answer。

 Now， I'm gonna go back。 I'm going to actually qualify that。 It said it gave me a pretty。

 I said it gave me a pretty good answer。 But the truth is， I have no idea。

 I'm not an expert on this topic。 And as with anything that we get out of when the large language models。

 I would highly encourage you to verify the output。

 but I think this is interesting because at least at the very minimum。

 it help me learn about through this question what might influence the number of mosquitoes in my yard and give me things that I could go and follow up on and verify。

 see if they are correct at these facts hold water。😊，See if these questions really are useful。

 but they certainly look like valid and important questions。 What is the size of your front yard？

I'm not sure theres that that I even need to go research that。

 a larger yard is likely to have more mosquitoes。 What is the climate like in your yard。

 I know that that matters。 What time of year is it。

 I know that that also matters from personal experience。

 Are there any bodies of standing water sources in your front yard or nearby。

 I know that matters that sort of general knowledge in the southeastern United States。

 And are there any plants or vegetation in your front yard the mosquitoes are attracted to and actually happen to know that that is also an important factor。

 So it's actually given me a bunch of really good questions。

 It's given me some facts related to those questions。

 which I would have to go verify I don't know as much about。

 but it is a really helpful tool for automatically taking a question breaking it down。

 I can see sort of its reasoning about how it's going about and thinking about this。

 It improves my reasoning about thinking about how I might answer to this question。And in many cases。

 what we'll see is having the large language model break down the question will help it give a better answer to us so that we'll get something that's more accurate。


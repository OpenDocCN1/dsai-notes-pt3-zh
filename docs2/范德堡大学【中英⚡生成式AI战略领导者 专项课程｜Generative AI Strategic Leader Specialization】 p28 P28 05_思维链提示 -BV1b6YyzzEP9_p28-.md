# 范德堡大学【中英⚡生成式AI战略领导者 专项课程｜Generative AI Strategic Leader Specialization】 p28 P28 05_思维链提示 -BV1b6YyzzEP9_p28-

You may remember being told to show your work when you were a student。

 probably an elementary school or middle school， and you were working on a math exam。

 and you had to explain how you got there， or maybe if you've gone on and you've done other things where you had to prove that something was true that you had decided。

And so showing your work， explaining your reasoning is something that can be really important in a number of different domains。

 and it turns out that when it comes to writing prompts， this can be really， really important。

Getting an LLM or a large language model to explain its reasoning behind something actually can make the large language model perform better for us now this is a really interesting thing but if you think about it。

 it kind of makes sense right because we have a large language model that's trained on different patterns of text and it's learned to predict what comes next so if it can explain its reasoning correctly。

Um， then it's more likely that it's then going to produce the right answer because the right answer sort of intuitively should come after the correct reasoning。

Similarly， if you think about it， if it starts explaining the reasoning correctly。

 if it gets the first step right， it's probably going to get the second step right because it may have seen similar problems reasoned out Now this is an intuitive explanation。

 this may not be right， but I think intuitively you can kind of think about it is that if you break down the problem you're solving into multiple independent steps and you explain them and there's sort of a natural sequence and logic and flow to them。

 it's more likely that the final output which is the answer is going to be a natural extension of the correct reasoning and therefore correct。

 it's more likely to be correct if your goal is to accurately predict the next token Similarlyly if you have the problem and you get the first step right in the second step right。

 you're probably going to get the third and the fourth as a large language model because you've been trained on this stuff。

So there is a technique for this and it's called chain of thought prompting and I'm going to show you examples of this。

 but it's really helpful to remember when you're building prompts that requires some sophisticated sort of intelligence and reasoning capabilities now we don't always need this type of you breaking the process down step by step and explaining the process。

 but when we do and we need that more effective reasoning。

 it's really useful to understand how chain of thought prompting works。

So I'm going to start off with a positive example where we use it and we show what it does and how it works。

 So we have some examples here that we are going to give sorry I'm actually going start off with a negative example first I apologize that was a mistake so I'm going to start off an example that does not use chain of thought prompting and I'm also going to show an example where I'm going to make a mistake in how I phrase the prompt and how I structure the prompt and I'll come back to this mistake in a second。

But what I've got here is I have four different or three different questions that require some reasoning and in the first two I've given an example of what I want。

 I say I have four bike racers start a race and travel an average of 30 miles per hour。

 that each race for two hours is the total number of miles ridden by all riders greater than 200 and then I have an example and I say answer yes。

And then I say a question， I have a staging process for a bike race to line up racers。

 it takes 47 seconds to stage a group of eight riders and 67 seconds to get their group to the starting gate and ready to race I want a new group to start the race every 30 seconds do I need eight group staged at all times in order to have races continually starting every 30 seconds and the answer is no。

 this is the example I'm giving it。And we'll see the reasoning behind these in a minute。

 and then I say I'm in a spaceship without gravity， I have a cup with a needle in it。

 I moved my foot on the bed， knocking over the cup onto the floor。

 I lift a book up and put it on a desk， is there anything on the floor？Now。

This is the question I'm trying to get chatGPT to answer and so I've given it basically some examples of questions with answers of either yes or no。

 so I'm trying to elicit a yes or no answer from chatGPT。

 I'm using few shot examples to do that and I'm showing it questions I'm showing it answers。

And then I'm asking it for the answer about this question about a cup knocked on the floor now I have actually seen some variations of this and I apologize because I don't remember exactly where I saw this first example of reasoning with the cup and the needle inside of it knocked on the floor but I thought this was an interesting one because it works really well for showing the difference between chain of thought prompting and without so this is without chain of thought prompting。

So what does chat GPT say because we asked it is there anything on the floor so the question was I'm in a spaceship without gravity。

 I have a needle with a cup or I have a cup with a needle in it。

 I move my foot on the bed knocking over the cup onto the floor and then I have some irrelevant information and then I say is anything on the floor？

Now， without chain of thought prompting， it says yes。

 when the cup with the needle and it is knocked over onto the floor。

 both the cup and the needle will end up on the floor。In the absence of gravity。

 objects will not fall downward as they do on earth。

 but they will still move in response to forces applied to them。 In this case。

 the floor supplied by your foot， knocking over the cup will cause the cup and the needle to move and come to rest on the floor。

 Liing a book and putting on a desk does not affect the position of the cup so they will remain on the floor。

So it says， yes， there's going to be something on the floor， the cup and the needle。 Now。

 let's look at the same example。

![](img/edcbaa8c8c72c7e4274679e7d085eaad_1.png)

But with chain of thought prompting applied。So here we go with chain of thought prompted。

 so with this one。We've spelled out the reasoning behind each of the examples。

 so we go back to the bike Rar。And we say， will the total be greater than 200 and so we say reasoning？

Each rider will ride 30 miles per hour times two hours， equals 60 miles。 I have four riders。

Therefore， the total number of miles ridden by the riders is four times 60 miles equals 240 miles and then answer yes。

 this is chain of thought prompting， we're explaining the reasoning behind the examples to the large language model so in this case we're explaining we're sort of working out the math showing our notes of how we got to this answer。

And then we do the same thing for the next one， where we're staging a bike race and we want to figure out how many people have to be staged at a time in order to start a race every 30 seconds。

And we give the reasoning each group takes 47 seconds plus 67 seconds to be ready to race。

 so I will need to calculate how many races will need to be run before a group is ready to race a group will have 114 seconds over 30 seconds equals 3。

8 races run before it is ready to race I can't have a partial group， so I need to round up to four。

 I only need four group staged to be able to race every 30 seconds。

 so I do not need eight groups answer no。And so you see rather than just say here's the example。

 here's the answer， we say here's the answer， here's the reasoning， and then here's the answer。

 the correct answer。So then in this final example with the spaceship。

 again we're having the spaceship， there's no gravity。

 we have a cup with a needle in it knocked on the floor。

 and then in this example we tell it to provide its reasoning first and then its answer。

 so we're prompting it and giving it a format that makes it clear we want the reasoning first and then the answer。

And what's interesting is we see different reasoning than we saw before and we get a different answer。

 if you remember before we got the answer of yes， their cup and the needle will be on the floor。

 but if you look down here on this one at the bottom。

 we can see that it says answer no because theres no concept of on the floor in a zero gravity environment。

 So if we look at this one this one's actually giving us sort of a better reasoned answer in my opinion now there's probably different nuances and I'm not an expert on this。

 but I think if you don't have gravity， you're not necessarily going to have the cup and the needle resting on the floor just because they got knocked off and so the reasoning is better and this one it says。

In a spaceship without gravity， objects do not behave as they do on earth with gravity。

 when the cup in the needle is knocked over， the cup and needle will not fall to the floor as they would on earth。

 instead they will float in place or move in the direction of the force applied to limb。

And so therefore in the absence of gravity， there is no concept of object being on the floor as we stay on them on earth and so basically what it's saying is like well。

 you might move them or cause a force to be applied。

 buts not they're not going to just sit there on the floor because there's no gravity and so it comes up with the answer no so you see right here we're getting a completely different answer out of the large language model and the difference is is that one example we're giving it。

😊，The examples were' given it the reasoning behind the examples。

 and then we're asking it to provide the reasoning and then the answer。

 which is this case and where we're saying no， there's nothing on the floor。

 which is probably a better answer in this case。In the other example。

 all we're doing is saying here's the question， here's the answer， here's a question。

 here's the answer， and we're not giving it the reasoning。

 and then finally we're saying here's a question and it's going to try to produce the answer first which is what it does。

And so the difference is really only in what it does here it's answering first。

 but it's not explaining its reasoning first and its reasoning actually isn't quite as good and its answer isn't quite as good。

Now， you know， spaceship knocking a cup with a needle off on it， this might not apply to you。

 but it's an interesting example of where' more nuanced reasoning and if you have a case where you need to have it think through and I say think very liberally here。

 but if you need it to try to get better reasoning behind the answer or a better computation。

 whatever you want to describe it as。But intuitively。

 if we thought through the process of getting the answer and we have a good process of breaking down the problem and going step by step to a solution。

 we're likely to get a better answer out a better solution out。

And so that's what chain of thought prompting is doing is we're trying to elicit that break the problem down into the steps。

 think about you know step by step how you're going to solve it and the way that we get there。

 the way that we get to do that is when we give it few shot examples like we do up here。

 we explain the reasoning behind the answer and we explain the reasoning first。

 we say this is what I'm thinking and doing this is why I'm getting there。Similarly。

 we do it on this one too， we say here's my reasoning and we provide the reasoning before the answer and the goal is to get the large language model to do the same thing to follow our pattern of breaking down and explaining the reasoning。

Before giving the answer。Think through the problem to give the fundamental steps and then to produce the answer and we get better outputs in this case and in most cases it's been shown that you're going to get a better reasoning out of the large language model if you have it explain its chain of thought。

 what it's thinking through what it's trying to do in order to solve the problem then you'll get a better answer out。


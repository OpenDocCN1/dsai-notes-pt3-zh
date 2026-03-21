# 范德堡大学【中英⚡ChatGPT与Excel｜ChatGPT + Excel： AI-Enhanced Data Analysis & Insight】 p45 P45 02_动作少样本示例 -BV1PdVizZE1d_p45-

Large language models can actually do some planning， which is an interesting ability。

 so they can actually go through and take patterns with few shot examples and they can learn what the next action should be given a particular situation。

 but I'm giving you this example not because they're limited to coming up with planning and the sense of actions or doing sentiment analysis。

 but I want you to expand your sort of mind on what's possible with few shot prompting and see it as a technique that can be taken and adapted to all kinds of situations。

So we've seen how we can use few shot prompting。 We're doing sentiment analysis。

 Now we're going to do something very different with it。

 So we're going take a look at this example where we're describing different situations with driving a car。

 So in the first one we say situation I'm traveling 60 miles per hour。

 And I see the brake lights on the car in front of me。 Come on。 And the action is。

 we're going to break。😊，So again， we've got a first example in our few shot examples situation。

 I've just entered the highway from an on ramp and I'm traveling 30 miles per hour。Action accelerate。

 So we're teaching the large language model that it's going to be given a situation and it needs to decide what the car should do。

 Situ， a deer has darted out in front of my car while I'm traveling 15 milesph。

 and the road has a large shoulder。 Action。 B and swerve into the shoulder。Situation。

 I'm backing out of a parking spot and I see the reverse lights illuminate on the car behind me。

 and then we prompt it with action。 We leave off at the end of our prompt with something that indicates a large language model We want it to decide what the action is。

 And what do we see it do， it actually says stop and wait for the car to back out before proceeding。

 and it's making a sensible you know decision about what the action should be。

 Now I don't think we should go and build self-driving cars with few shot prompting。

 I don't think we're going get there with that。 but I do want to show you that we don't have to think just with a narrow rigid box of like you know classify something。

 We can actually kind of have complex tasks that we're having it perform Now sentiment analysis is a complex task。

 but this is also a very complex tasks that's sort of in a different vein。

 So I want us to think very creatively about how we can use few shot prompts。 Now again。😊，对。

One of the things that we're getting is we're getting some constraints on our output。

 it's learning what the output should look like。Now I'm going to then go and do something else interesting。

 I'm going to show you kind of an interesting capability of large language models and one of the things that can be done to use one large language model to teach another one。

 which is kind of an interesting capability。So I'm going to say please provide more examples and then I'm going to kind of prompt it with situation and it's going to start and it's going to start generating additional situations and action so it's learned from our pattern。

 the types of things that we're describing in the types of actions and now it's going to go and generate more examples so it says you're driving in heavy rain and notice that the road ahead is flooded so this is the continuation of our situation。

And then it says action slow down and cautiously drive through the flooded area watching out for other vehicles and avoidance sudden movements or changes in directions。

I would actually disagree with this， I'm not sure it makes that it's smart to drive through a flooded area that's probably questionable decision making。

 which again just reminds you that you need to own the output of the large language model and check it。

Situation， you are driving on a two lane road and a car is approaching you from the opposite direction with their high beams on action。

 dim your headlights to low beams to avoid blinding the oncoming driver but you notice the interesting thing about this is it's giving us some rich situations and possibly appropriate actions I'm not sure I agree with the flooded one but we're generating different examples of situations and what to do and they look very similar to what we produced before and one thing that's interesting is we can actually take examples like this。

And then curate them and have a human edit them and then provide them back to a large language model either later as additional examples for a few shot examples。

 and so once we've had a human look at them and curate them a little bit， maybe clean them up。

 maybe we don't want that one on flooding because we don't think that's a good idea so we actually say。

 well you shouldn't drive across flooding or we sort of spell at the rules。

 but you can imagine that the level of effort to create the initial examples。

Right here is much higher than the effort to go through and generate subsequent examples which we can then go in hand edit and curate so we can quickly build up these examples both in order to generate an output right now that we want。

 but also to generate examples that we can later give back to the same large language model or that we could go and give to another large language model to teach it。

 and in fact some people have actually gone and done this they've taken output from Chet GPT。

 for example， and they've taken it into another large language model like Facebook's Lama and used the output from chattGBT to improve the outputs of Lama。

 and so this is another interesting capability is that large language models through these few shot examples they can generate few shot examples for other models。

The other thing I just want to go back to is。This is a very different sort of task and style than we had before。

 we have a situation and then we have an action that's being predicted。

And so we can have all kinds of interesting things anywhere where we can have a pattern that we can describe a set of examples that show the input and what we want the outcome to be。

 and we can also show things that have intermediate steps， which we'll look at in another video。


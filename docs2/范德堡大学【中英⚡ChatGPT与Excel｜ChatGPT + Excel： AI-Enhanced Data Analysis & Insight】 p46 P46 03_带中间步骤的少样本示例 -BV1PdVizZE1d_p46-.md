# 范德堡大学【中英⚡ChatGPT与Excel｜ChatGPT + Excel： AI-Enhanced Data Analysis & Insight】 p46 P46 03_带中间步骤的少样本示例 -BV1PdVizZE1d_p46-

The examples that we give in few shot prompts don't have to just be an input and an output。

We can actually show intermediate steps to reach a particular goal Now one of the reasons why this is really interesting is that when we begin showing the intermediate steps。

 the large language model can learn how to apply a series of intermediate steps in order to reach the goal so we can start getting more interesting output。

 then just here's an input and here's the output or here's a situation and here's the action。

 we can start looking at if this situation occurs， what might be the next action and then the action after that and the action after that until we reach some state that is important to us like we are no longer at risk of running into the car in front of us。

And so if we tailor our examples correctly， we can actually have the large language model do sort of the intermediate breakdown of the problem into a series of steps where we can have it decide how it might go and tackle the problem。

 Now let's look at an example of this。 we're going to take our car example from before。

 and now we're going to enrich it a bit。 So we've now got actually two essentially situational examples。

 We start off with one， and it's the same one from before the situation is I'm traveling 60 miles per hour。

 and I see the brake lights on the car in front of me come on。 and then we say think。😊。

I need to slow the car down before I hit the car in front of me。Action， press foot on break。

Think the car isn't going to stop in time action， check if the shoulder is wide enough to swerve into。

Think the shoulders wide enough。 Action swerve into the shoulders。

 So now we've built a more complex scenario that includes the original situation。

 But then we have sort of updated steps of what's happening and what the thought process is and what we need to do next based on that thought process。

 So in this case， we're traveling down the road。 Suddenly。

 the brake lights on the car in front of us come on the。

We think that we're going to hit the car so we hit the brakes。

 We think that we're not going to stop in time。 So we look over。

 We see that this shoulder is big enough。 so we decide to swerve into the shoulder。

 And so we're now basically having a more complex situation that also has multiple steps involved Similarlyly。

 we've taken one of our other ones that we had before I've just entered the highway from an on rampamp and I'm traveling at 30 miles per hour。

 think I need to speed up to the speed limit so that I don't get hit from behind action。

 press foot on accelerator。 think I've reached the speed limit action let up on the accelerator。

 So we're basically going through we're breaking down the problem or situation into multiple steps and what's happening。

 Now we provide a situation again the parking lot situation。

 I'm backing out of a parking spot and I see the reverse lights illuminate on the car behind me。

 action。😊，And so now we're prompting。For what we would like the large language model decide and now we see instead of just a quick。

 it's done， you know look， stop， wait for the car behind me instead it says action immediately stop backing up so we see immediately stop backing up and then it thinks I need to check my surroundings to make sure it's safe to continue backing up。

And then action， check mirrors and surroundings for any obstacles or pedestrians。

 so it's thinking about what does it need to do next， it needs it's thinking oh。

 I need to look around and make sure it's okay so it looks in the the mirror and it looks in the side mirror。

 the rear view mirror， the side mirror and then it thinks okay it's safe to continue backing up and so action continue backing up slowly and carefully while keeping an eye on surroundings So now we've got more sort of finegrained detail in what we're actually going to do in the particular situation。

😊，Now there's all kinds of interesting things where we can imagine doing this。

 we can think about customer service， the customers reporting a particular problem and we've recorded what customer service agents did to help the customer solve that problem and so we could imagine that through few shot examples the model could learn to help a customer diagnose a problem and if it had seen enough different examples。

 enough different paths， it could go through and figure out what to do。😊。

We can also like last time we can generate more examples so we can say generate another example and it says generate situation。

 I'm driving on a narrow winding road with several blind curves。

 think I need to slow down and be cautious to avoid any potential collisions and it goes through a series of actions until it saysre normal speed。

And then we could say think。I am running out of gas。

And it says think I need to find a gas station before I run out of gas action。

 check the GPS or map for a nearby gas stations， think the nearest gas station is too far away。

 action， reduce speed to conserve fuel and try to make it to the next gas station or rest area but you can see how we're getting a script it's sort of like a problem solving script now。

Let's think about this if we're the customer service。

 We might want to go and generate a sequence of actions。

 and then we could input what the next responses that we get from the customer。

 So and let's look at where we end off on this example Action。

 pullll over to the side of the road and turn on hazard lights to signal other drivers。

 Call for roadside assistance or walk to the nearest gas station as possible。Think。

Roadside assistance。Is unavailable。And the nearest gas station is too far away to walk to。

 so let's see what it decides to do。Think I need to conserve my phone battery and find a way to get to a gas station as soon as possible。

 Action。 Check if there are any houses or businesses nearby where I can ask for help or use a phone。

 Think there is a house in the distance。 And so you can see how it's building up the script of what to do。

 It's doing problem solving。 It's creating interesting situations。

 We can also prompt it to keep going， We can keep having to go further based on inputs。

 like what would happen in this situation。 How would you go about dealing with it。

 We also see that the input is fairly constrained in what it's giving us。

 It's still following our pattern。😊，Now， this is a key thing to go back and think about is the intuition behind this。

This works partly because this tool knows how to predict what's next， given a pattern。

 it's learning from language， given this pattern， this is what I do next。 you can also imagine。

That it's seen in its training data， lots of scripts， things that looked like， okay。

 here's what is going on。 You can almost think of like a movie script。 so and so said this。

 so and so said this in response。 you know， and then you might see a description of what was happening。

 Well， they get into the car， you know exit scene， something like that。 But you know。

 we're using patterns。 we're using structures that are likely to have been things that it was trained on and seen。

 So it's learned how to from these examples go in extrapolate what should happen next。

 the patterns and its ability to learn and into it。

 what needs to come next in the pattern is based on that it's seen these types of things。 Now。

 if we went and we picked some type of pattern or structure that is very different from what it's seen。

 it may be able to do it may not be。 So one thing to think about is when we're structuring things。

 try to pick simple patterns in terms of how we structure the text。😊。

They're going to be something that it's likely seen， you know。

 something similar to in the training data。 So this idea of a prefix within some situation you know an action。

 you know think about trying to pick a format like that that looks like something at' seen。

 notice another thing we're keeping each example， although it's wrapping around here。

 these things are actually each one line。 So it gets much harder to follow the pattern。

 if we say like action colon， and then we have a whole bunch of stuff on multiple lines。

 it comes harder to see the pattern because not every line starts with one of these prefixes。

 So you have to think through the structuring and the formatting of these things。

 but in the base of it all， we're trying to give it some pattern that it can quickly and easily pick up on in order to understand how to solve the problem we can provide the intermediate steps like we're seeing here。

 but we don't necessarily have to give it the logic for how to。😊，Decide the next step。 In fact。

 if we think about this。When we say roadside assistance is unavailable and the nearest gas station is too far way to walk to。

 if I had to describe the rules of how to do that and this whole situation that we're going through。

 if I had to really write a prompt that all the different rules in this situation do this in this situation do that。

 you can imagine it would take up a lot of space and it might be really hard to do probably is going to have limited flexibility。

 so one of the powerful things about these fu shot examples is we can you tap into the large language models reasoning or whatever we want to call it it's computational abilities to go and figure out what's next and come up with the next item in the pattern。


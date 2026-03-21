# 范德堡大学【中英⚡生成式AI战略领导者 专项课程｜Generative AI Strategic Leader Specialization】 p24 P24 01_少样本示例 -BV1b6YyzzEP9_p24-

A really interesting thing that we can do in a prompt is we can actually teach the large language model to follow a pattern using something called few shot examples or a few shot prompting。

 So the idea behind this is we're going to give the large language model examples of input that we would give it and then the output that we would expect And so you can imagine a human will go through and go through a couple of examples。

 so they'll give it some input， they'll show it what the correct output should look like。

 they'll then give it another input， give it the correct output and the idea behind this is is that we're developing a pattern that the large language model can then learn to follow So actually within our prompt we're teaching the large language model a new trick。

😊，Were basically showing it what we want it to do and how we want it to format the output within a series of examples。

 So rather than describing the process we want it to follow。

 we're giving it an examples of what we want it to do and then hoping that it will continue the pattern that we provide。

 So let's take a look at this。 So if you'll see right here。

 we've got a simple example of few shot prompting。So the idea behind this as we start off with input and you'll notice that this is a common thing that you will see in few shot prompting is that you'll see a prefix applied to the lines now you can have all kinds of prefixes and your prompts and your patterns don't have to just be input and an output it could be a couple of different steps and we'll look at that in a minute。

But as we see here， we have an input which is the movie was a bit long and what we're going to do is we're going to do what's called sentiment analysis。

 This just basically is try to analyze some comment about a thing and try to figure out what the user sentiment was about it。

 like were they positive about it， that they think it was a good thing or were they negative about it。

 Do they think it was a bad thing or were they neutral and we're just going to do a really simple example with sentiment analysis where we're going to take some fake reviews of different things and then we're going to decide if they were positive。

 negative or neutral。😊，So what we're doing rather than saying go and analyze these user comments and tell me if they are positive。

 neutral or negative， instead what we're going to do is give a series of examples so we give the first example which was the movie a was good。

 but a bit long and we say the sentiment was neutral， so it has some pluses and minuses， it was good。

 but it was too long。Then we have an example where we say input， I didn't really like this book。

 it lacked important details and didn't end up making sense。

 and then we say the sentiment was negative。And then we have another input where we say。

 I love this book that was really helpful in learning how to improve my gut health and the sentiment is positive。

And then what we do is we're going to give it the thing that we actually want to perform the task on that we're going to hopefully get it to follow the pattern on and we'll say input。

 I wasn't sure what to think of this new restaurant。

 the service was slow but the dishes were pretty good。

 and then we cue it in to follow the pattern by saying sentiment colon basically。

Tell us what you think about this thing。 Now， my prefixes are a little bit leading。

 They are giving you information about what to do， but it could also learn from these patterns。

 if we just saids input and output。 it can also do that。

 And I'm giving you a little bit of richer information。

Now my goal then is to get the large language model to go and analyze the input I give it and decide what should be attached to sentiment and it picks up on our pattern and it says neutral so it sees that in this review you know it says service was slow but dishes were pretty good and so it's seen that sort of positive and negative and it's following my pattern that I gave it I didn't tell it this is what neutral meant but in the examples that I had before a kind of a balance of positive and negative ended up being neutral。

Now a couple things to note， one， we didn't tell it what to do。Two。

 we didn't tell it exactly what the output should look like。

 and what we see is that it's constrained itself。To the output and then basically the labels that we gave it earlier。

 we had negative， positive and neutral and it's automatically constrained itself and provided an output based on that now it won't always constrain itself。

 but this is a nice thing as in many cases this can help us get a more you constrained or bounded output out of it。

Now if we went and we gave it a new one， we could say input。I really hated this coffee。

It was roasted too much and tasted。Burned now， notice I'm not going to give it the prefix for sentiment。

 So let's see what happens when I do that。And then you notice it provides the prefix and the output that I expected。

 Now， the really important thing to think about with this is if you go back to when we talked about large language models and what they're doing。

 they learn to predict next word。 They're learning patterns。 and so。

When it sees input in a statement。It's predicting that the next word should be sentiment。

 because that's what it saw in the examples that we provided before when we ended with sentiment。

 then what it did is it knew that it needed to pick up right after sentiment。

 So if we go back to this and we edit it and we just add a line here and we say sentiment。

Then it should pick up the pattern right after sentiment and so this is kind of helpful to know about when you're thinking about few shot examples now this is a simple example of following a pattern。

 but you can see how this is a powerful way of teaching。

 particularly if you have data that describes the task that you want to do。

 but and then when I say describes it shows the input and it shows the output and it doesn't necessarily describe how the task was performed。

 but we can see what's being done and that type of thing can be a good fit for a few shot prompt。


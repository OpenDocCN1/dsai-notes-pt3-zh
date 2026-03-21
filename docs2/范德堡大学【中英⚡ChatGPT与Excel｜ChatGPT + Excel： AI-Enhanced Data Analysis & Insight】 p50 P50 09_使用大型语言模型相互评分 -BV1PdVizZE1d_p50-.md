# 范德堡大学【中英⚡ChatGPT与Excel｜ChatGPT + Excel： AI-Enhanced Data Analysis & Insight】 p50 P50 09_使用大型语言模型相互评分 -BV1PdVizZE1d_p50-

We're going to be faced with the problem with prompts of the large language models themselves are going to be moving very rapidly。

 They're going to be continuously evolving。 And we've already seen that。 We've seen Chat GT and G 4。

 we've seen Lama and alpaca。 we've seen vuna and lots of different ones are continually coming out。

 And one of the things we want to know is when we develop our catalog of prompts。😊，Our patterns。

 we put lots of work in developing prompts that work well for us。

 how do we evaluate them and make sure that they're maintained over time。

 because if we change our large language model， does that mean that all of our prompts are going to break or if we change the data that we're working on slightly does that have ramifications for us so we need better ways of helping to evaluate the output now one way of course that we're going to do this is we're going to have humans look at the output in many cases but we'd like to do things that could probably help scale better。

Be able to actually go and do sort of large scale automated analysis in some way So how do we go about doing this Well one of the really interesting things with large language models is we can actually use them to evaluate themselves This can be one of the inputs that we use to help determine how good our prompts are and how maintainable they over time is we can use a large language model to grade either itself or the outputs of another large language model so we've seen the examples of this where we have they've actually taken large language models and they've had one large language model teach another large language model essentially。

😊，But we can do something similar in that we can take outputs from a large language model and actually feed them back into the model itself to grade them。

 or we can actually go and take another large language model that we're working with and have its outputs graded by。

 for example， a better large language model maybe with more parameters that can has more powerful。

 So let's look at an example of this and how we might build a prompt to do it。😊，So in this example。

 I'm going to teach the large language model in this case。

 ChatGBT how to grade the output of a prompt。 I'm not actually going to show it the prompt in my example。

 I'm just going to teach at the gradient process so that it can help automate it for me and so I'm going to use some few shot examples So as input here at the top I'm saying here's my input and it' it's a bit of text about Vanderbilt University from Wikipedia。

😊，It identifies that Vanderbilt University was founded in 1873 and I explained here's what the output was。

 the output was the following is a list of events and dates and the output Vanderbilt founded 1873 and then the explanation is that the output has unwanted text at the start and should only include the names and dates and so it I gave it a grade of5 out of 10 so this is the output that was produced and then I'm providing a human explanation of what is wrong with the output of why it's not getting a perfect score。

And then I'm grading it and giving it a five out of 10。

So I'm going through and I'm doing a couple of these by hand to show it what I want。

 and then I'm giving it another example with that exact same piece of text I'm saying the output was just 1873 and the point of this is that if you can probably sense it by now is I want a prompt that's going to extract events and the dates that the events took place and that's it I want an event name separated by a comma and then the date of that event I don't want any other text I don't want explanation。

 I just want names of events and dates and I'm showing how ChaGBT can grade the output to see if it's matching that format I'm not even showing it what the prompt is I'm not showing it what the task is I'm giving it examples to help learn。

And then I say explanation。The output is missing important information about the event that happened on that given date。

 and I give it a grade of three out of 10。And then I have one more with the input。

 which is that same paragraph about Vanderbilt。 I show Vanderbilt University comma 1873。

 which is the ideal output for my fictitious task。 And I explained that the output exactly。

 And then I actually cut it off if there's a typo here。

 It's really supposed to be met expectations or something like that。

 And then I give it a grade of 10 out of 10。 What's interesting is this doesn't even matter that I made a mistake here in my explanation。

😊，Because it still works。 And so then I give it a completely different input。

 I say here's a different input。 Again， it's about Vanderbilt and。

The history of the English program at Vanderbilt in Creative Writ， and so I give it as input。

 another piece of text on that， I say the output was， and I give it what the output was。

 the fugitives in South Agrarians first half of 20th century and then Vanderbilt is a founding member of the Southeastern Conference。

 1966 and。That's essentially a prompt。For chat GT to then go and grade that output。

 And so it then provides an explanation of the output。

 It actually mention something that I didn't grade in there， but it's interesting。

 and it says there's inconsistent capitalization。And then it gives it a grade of 9 out of 10。

 So as a human labeler and a human performing this task。

 I actually ended up with a 9 out of 10 because I it wasn't consistent in capitalization。

 but you can see it did a good job。 It took the sort of substance of what I wanted and it performed the grading task that I had given it。

 and so we can actually use large language models to evaluate the output of prompts。 Now。

 there's a number of ways you could potentially use this。

 One is if you have some system that's going to。😊，Go and make decisions or generate information with a large language model like chat GT or some other model that you're running。

 you might want to have the model check itself or another model， check itself。

 or you might want to do this multiple times where you take the output that you're getting and you give it a grading criteria similar to what I've done here and you've developed a prompt with grading to criteria you might have multiple prompts with the grading criteria and you all have them score the output。

 And then if the score is below some threshold， well maybe you want to have a human look at that output or maybe you just want to retry it and see if you can get something better to be produced and so。

😊，This gives you an extra sort of tool of how do we go and evaluate what's coming out。

 make sure it looks good and still have sort of the power and sophistication of these models and this is one way to do it Now there's lots of ways that you could phrase the prompt。

You might want to go and look at the alternative approaches pattern to develop some different ways。

 this is one example using few shot examples and I could have gone back and say， you know。

 we could have said act and use the persona pattern， act as a prompt critic， perform and her。

Give the output。That I provide you a grade in terms of how well it matches the expectations of the。

Prompt designer。 I am going to give you examples of grading prompts。

 And so we could have gone and done something like that。 I did a relatively simple prompt。

But we could do a much a more sophisticated prompt using some other patterns， again。

 it's going to generate an explanation， and then at the end of it it should generate a grade force as well。

And so it'll then go through and give us an8 out of 10。 So you notice we got8 out of 10 one time。

 we changed the prompt slightly。 we got9 out of 10。 Either way。

 it looks like that's a pretty good output based on our grading criteria and what we want。

 And so we can use this sort of tool in our toolbox when we need to evaluate a prompt in the output of a prompt。

 We don't have to always fall back to having humans look at it。

 One thing we can do is we can fall back to having the large language model itself evaluate the output。

😊，And then we can build different types of automation around that or we can use that as a trigger to escalate to a human now of course if we have a lot of really good examples of grading that helps us a lot。

 but we don't have to have a ton if you see in my example I had just three examples of grading the output and it did a good job of figuring out what I wanted。


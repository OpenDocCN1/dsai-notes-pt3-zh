# 范德堡大学【中英⚡ChatGPT与Excel｜ChatGPT + Excel： AI-Enhanced Data Analysis & Insight】 p56 P56 01_请求输入模式 -BV1PdVizZE1d_p56-

When we're working with large language models， often we're going to describe in our prompt a set of rules that we want the large language model to follow。

 rules that are going to affect its output and essentially program the large language model。

And one of the things that we're going to want to do so we're going to want to say here are the rules now apply them to an input that I'm going to provide later。

And so one of the challenges is how do we get the large language model not to immediately respond to all of our rules if we have a flipped interaction。

 for example， sometimes when we flip the interaction and we say ask us questions。

 it'll generate 10 or 20 questions all at once， and so what we want to a way to do is basically a simple way that we can get the large language model to listen to what we're saying。

 acknowledge it and then wait for input from us。Now we can do this。

With the ask for input pattern so the idea behind this is we want to get the large language model to listen to the rules and then ask us for the input to apply the rules to so when were talking about asking questions in a flipped interaction we might want to describe the rules for asking the question and then we just wanted to ask one question so we just want to get one question out if we're describing rules for alternative approaches we might want to say here are the rules you're always going to create alternative approaches to whatever ask you to do。

But just ask me now for the first task to create alternative approaches for。

 we don't want it to go and have a big response to it。

And what we see is that that's not always the case。 so let's take a look at this example。

 Now in a prior video， I introduced the alternative approaches pattern and when you saw me use this pattern。

 it worked really effectively。Because I was actually combining it with the ask for input pattern。

 so I'm going to show you what it looks like when I don't combine it with the ask for input pattern。

 so I went and I said whenever I ask you to write a prompt for me to accomplish a task。

List what the task is， list the alternative approaches for creating the task and then write a prompt for yourself for each approach。

 so I'm asking chattGBT， give me a bunch of alternatives for prompting you chatGBT to solve the task。

This is going back to the earlier idea where I showed how we could actually use ChatGPT to generate prompts for itself to help us with prompt engineering。

And what I do is I use this， but I'm taking away something important that I'm going to show you in a minute and what it does is chatGPT responds。

 it says certainly， but then it dream up a task， it says here are three alternatives for completing the task。

 organizing a cluttered desk， I'm not interested in the task organizing a clutter desk。

 it just respond into my initial prompt to which was create alternative approaches for a task。

 it dreamed up a task and then dreamed up its own approaches for that task。Now。

I'm not interested in this， so now I've got my conversation and it's got all this extra stuff in it that I don't care about。

 I had to wait for it to generate it and you know if I was trying to create some interactive experience that had some consistency。

 this would not be helpful so。What I can do is I can apply the ask for input pattern。

 and then the idea behind this is we just do one simple thing。And that is at the end of the prompt。

We tell the large language model to ask for the next input so in this case we say ask me for the first task So the very last thing we do we describe all the rules or whatever it is that we want in our prompt and then the last thing we do as we said now ask me for the first task。

 ask me for the first idea， ask me for the first thing you want me to generate a story about whatever it is。

 but it's a way that we can sort of cut off the large language model and tell it don't go generate a bunch of stuff。

 you know I'm glad that you can do that， but what I want you to do is I want you to stop right here and ask me what I want to do。

So it's a way of forcing the large language model。To basically turn the control back over to the user and let them decide what to do next now like all prompt patterns。

 when we're dealing with a larger language model， it is somewhat stochastic or random it means it's not always going to do exactly the same thing every time and it may not work 100% of the time but this works very。

 very reliably to just say ask me for the first input or whatever it is at the end of the prompt。

Because it clues the large language model in that it needs to stop。

 and if we look at the comparison of the output。It's actually much more focused。

 so we see in this case it says certainly let's begin what is the first task you would like me to create alternative approaches and prompts for rather than this much longer thing that it generated before。

That was not really helpful to what we were doing， so it kind of cuts it off。

 notice it's the same input， but it's sort of cut it off， it's told it。

 look you need a stop right here and you need to wait for my input。


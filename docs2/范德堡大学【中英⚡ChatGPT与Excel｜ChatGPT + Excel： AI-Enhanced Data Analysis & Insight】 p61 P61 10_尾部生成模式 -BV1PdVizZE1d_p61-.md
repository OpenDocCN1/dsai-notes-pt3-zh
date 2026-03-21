# 范德堡大学【中英⚡ChatGPT与Excel｜ChatGPT + Excel： AI-Enhanced Data Analysis & Insight】 p61 P61 10_尾部生成模式 -BV1PdVizZE1d_p61-

When we're having a long conversation with a large language model。

 sometimes we'll run into the challenge that the large language model will forget the rules of the game。

 it'll forget what we're trying to accomplish， what is the task that we're working on。

So one of the things we need is a way to remind the large language model。

 what are we doing and we like it to remind itself if possible。

 and so the way that we can do that is by using what we call the tail generation pattern and the idea behind this is that we're going to generate a tail and end to the output that the large language model produces that will help remind it what we're doing and so。

The tail is going to always be generated at the end of its output and the tail will remind the large language model what the rules of the game are and we're going to see this in the context of combining the tail pattern with the alternative approaches pattern and with the ask for input pattern。

 So we're going to put all these things together and we're going to see how this is a really useful thing。

 So generating a tail on our conversation use the tail generation pattern is really。

 really effective in maintaining our conversation longer and maintaining the rules and the knowledge of our rules longer。

😊，So I've actually used this several times and I haven't talked about it。

 but I'm going to show you what it does。So this is the prompt that I used in the alternative approaches pattern discussion。

 so I'm asking chattGBT to generate a set of prompts to solve a particular task。

 so I'm asking chattGBT to help us with prompt engineering。

 I'm going to give it a task and it's going to generate possible prompts that we could use to perform that task with chatGBT。

Now， if I do this over and over and I keep saying anytime ask you for a prompt。

 you should go back and generate multiple alternatives for it。

 the problem I'm going to run into is that eventually it's going to forget that it's supposed to generate a bunch of alternatives and then it's supposed to be generating prompts and so I need a way that keep reintroducing that rule into the conversation to keep it alive longer。

And so one way I can help do that is with the tail generation。

And so this is the tail that's being generated。 I have the prompt and I say when you are done。

 ask me for the next prompt to create alternatives for。 so I'm adding this on。

 I'm saying when you're done at the end of your output。

You're going to ask me for the next prompt to create alternatives for so notice what I'm doing I'm actually using the ask for input pattern I'm saying at the end of the input at the end of the output that you produce。

 you're going to ask me for the next input so you're going to ask me for the next task to accomplish。

And I'm telling it you're going to ask me for the next prompt to create alternatives for。

 so I'm also reintroducing the rules of the game， I'm describing what the purpose of the input is that I'm going to be giving it and what it's supposed to do with it and I'm making sure that this shows up at the end of my prompt or sorry at the end of the output that the largelinguals model is going to produce。

 so I've divine the rules and I'm said at the end of what you do you're going to reintroduce this rule by basically asking me for the next input to create alternative prompts for。

😊，So let's see what happens。So I add this tail on， and so I'm generating a tail I'm using the tail generation pattern。

And I say write a prompt for chatGT to automatically detect questions in a chain of emails and summarize everyone's opinions on the question as bullet points beneath each question。

 so I've given it the task， here's what I want you to write me some possible prompts for。

So I would give it。The the instruction， it's now going to write the prompts and it generates a bunch of prompts for me。

 right？So now I've got all these alternative props。

 and then the last thing it does is it generates the tail。Just like I said， so it says。

 please let me know if you have another task for when you would like me to write a prompt and create alternative approaches for。

 so right here it's created a tail on its output。 It's at the very end and it says。

 please let me know if you have another task for when you'd like me to write a prompt and create alternative approaches for you notice that it's sentenced that it's created。

😊，Ecompasses a lot of the rules， it encompasses enough of the information about what it's trying to accomplish that we don't have to worry as much that it's going to forget the rules。

And so then I go and I give it another task， I say write a prompt to evaluate different prompts for summarizing the questions and it goes through and it generates all the prompts which we saw before。

 and then at the end it generates the tale again， please let me know if you have another task for which you'd like me to write a prompt and create alternative approaches。

So we've got it to reintroduce the task again and so now if we went in and we put in a new prompt。

 it still will remember what the context is and if we went in and we had you know back and forth without this at some point it's going to forget the rules of the game and it's going to say。

 hey， know what am I supposed to do or it's going to forget to generate alternatives or it's going to do something else。

 but by continually reintroducing the rules of the game as this tail on the output， then。

Every time we go to send in a new input just recently we had the rules of the game that give it the context that it needs to accomplish the task So the tail generation approach is really。

 really useful when we're gonna have a longer conversation where we're gonna to try to program something。

 we're going give it a bunch of rules up front and then we're gonna to have a whole bunch of interactions and we don't want it to forget the rules or the context Now it doesn't have to be rules。

 it could be anything that we think that needs to be reintroduced over and over into the conversation and what we do is we just make sure that at the end of the output。

 we ask it to put in whatever that tail is， it could be asking for the next input。

 it could be asking for some other additional information， it could be reescribing the rules。

 it could be kind of whatever you want it to be but it's like a little nugg it a little tail that we're going attach to that output to remind the large language model here's what we've been taught。

alking about and give yourself a little hint about it at the very end before we go on to the next task。


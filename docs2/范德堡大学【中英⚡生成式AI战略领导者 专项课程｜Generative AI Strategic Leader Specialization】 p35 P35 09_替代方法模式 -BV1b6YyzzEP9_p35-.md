# 范德堡大学【中英⚡生成式AI战略领导者 专项课程｜Generative AI Strategic Leader Specialization】 p35 P35 09_替代方法模式 -BV1b6YyzzEP9_p35-

Brainstorming different approaches to solve a problem is a really interesting way of using a large language model and one of my favorite uses for it。

 so something I really like about large language models is that I can come up with a problem than I want to solve and I can rapidly come up with different ways of solving that problem and I can test them out and get feedback。

Now， one way to do that is using the alternative approaches pattern。

 So the idea behind this is we're going to have the large language model。

Within some particular scope， always suggest alternative approaches for solving a particular problem or performing a particular task that is we always wanted it to give us good ideas that now I say good ideas they may not be good。

 they may not even work but you know kind of like brainstorming in a group you may have a lot of different ideas。

 some of them may be great， some of them may be terrible。

 but just the fact that everybody's thinking through ideas。

 throwing them up on a whiteboard or writing them down or talking about them can help you do a better job of thinking through the problem and figuring out what is the right solution that makes sense So I'm going to show you how to use the alternative approaches pattern to essentially perform brainstorming with the help of a large language model Now one of the things to note is just like if you get a group of participants that have different backgrounds they may help you come up with ideas that you yourself would not have come up with。

Well a large language model was trained on a big corpus of material and it's probably seen lots of problems and seen discussions of different solutions to that problem or different alternative approaches for a particular problem so you can think about it it is in some ways learned information about how to solve problems in different ways and can help us get access to that knowledge now it may also have never seen the exact problem that we're asking it for。

 and it may be able to synthesize using what it's seen in the past interesting potential approaches。

 even it hasn't seen the exact problem that we're working with。

So let's start off with an example of this。We're going do the alternative approaches this pattern we're going to say from now on if there are alternative ways to accomplish the same thing。

 list the best alternative approaches， so this is a very generic wording for this it's probably better to structure it very you know precisely to the task that you're working on provide more rich sort of context but I'm going to show you that even within a fairly generic wording and we can get this pattern to work for us。

And then I'm going to say compare and contrast the alternatives and ask me which one I want to use so I'm adding a little bit to this pattern I'm saying give me the alternatives but also give me some information。

 compare and contrast the alternatives， so maybe that'll help me think through which one is going to better fit my particular situation I can see if what are the pros and cons of each approach and which one sort of is a better fit based on those pros and cons。

And so。I then ask it， if you think back to in some of the past videos we've looked at using gameplay to create prompts and test us on our ability to write prompts。

 and so one of the problems that chatt GPT generated for us is it asked us to write a prompt to distinguish leap years。

 basically we would give it dates and the prompts should be able to determine if it's a leap year or not。

And so I'm going to turn that into a task for chattGT。

 So I'm asking chatt GPT to write several prompts for itself to solve this task。

 So I'm having chatt GT write the prompts for me Now I could have introduced this earlier in the course and just any task that you have。

 you want to be better at prompt engineering， ask chatt GPT to do the prompt engineering for you。

 And that's basically what I'm doing here。 and sometimes this works。

 but I don't want you to think that this is the best approach that I should just always go to chat GPT and ask it how to do it。

 Now you should have a sense yourself， just like any problem you're bringing to a large language model。

 you have to own the content So you should have some expertise in this area to help you distinguish whatever the better approaches what things don't make sense what's unsafe or harmful in some way you need to own whatever content comes out。

 So that's part of the reason I didn't just start by saying prompt engineering go ask ask chat G。

for the prompt。We're not going to do that， but in this case we are， we're saying。

We want Cha GBT to write a prompt。To use few shot examples to determine if a date in the year month day format is a leap year and the output should either be year is a leap year or this is not a leap year。

And so chattGPT then says approach one direct question format in this approach we directly ask chatGT whether a given date is light leapier and then it shows us the few shot examples for doing this。

 so it's generating the prompt force that we could provide you know use essentially to go and check of something into a leap year。

Then the second approach it says conversational format。

 and then it uses a completely different sort of style。

 It's still roughly the same format of generating few shot examples to solve this problem Now notice I scoped it to few shot examples I could have left the scope more wide open and just say write a prompt to do this。

 but I thought it'd be fun to look at different you know can we write the few shot examples in different styles and will it make a difference and we could go and test this and see if it does。

😊，But we now see it generating again。It's solving the problem of showing few shot examples for leap years。

 And now it's。Actually， you know I noticed something interesting is showing us how to solve the problem。

 it didn't actually fully follow the format that I gave it because I said why why why is a leap year or this is not a leap year and it is putting the date at the year at the front so it's actually made a mistake and this is part of the reason why you should read your prompts that it generates so make sure they're doing exactly what you want。

 but I could go and tell it and fix it and refine it。

 but you notice now I've got two different approaches to few shot examples to solve this problem。

And then at the end I get a comparison， it says approach one is more formal and structured。

 making it easier to understand in parse， it may be suitable for applications where clear and concise answer is required and then it says approach to is more conversational and natural making it more engaging for users it may be suitable for applications where user interaction is important。

 which is kind of true if you were going to prompt the user and then have like here's what the user said here's what the assistant supposed to say。

 you this would probably make sense， if you were just reporting on a Q&A then maybe the other format makes sense so it's a reasonable discussion of the different alternative approach for solving this problem。

Now， let's look at another example。I thought， what is a task that can sometimes be burdensome and so I thought about email now I haven't actually done this and tried it out of my email。

 I still kind of keep my email personal if I can to my laptop。

 but I thought that this would be an enhancement in the future if I was running a large language model directly on my laptop。

 something like Lamar or a pocket Paca， maybe I could do this and I would be comfortable with it。

And so I say whenever I ask you to write a prompt for me to accomplish a task and I'm going to change the alternative approaches pattern slightly。

 I'm going to tweak it a little bit for this one， list what the task is。

 list alternatives for completing the task。And then write a prompt for yourself for each approach so STE basic format now I'm doing two things one is I'm having it list the task at the beginning so right here I'm saying list the task and then I'm saying list alternative approaches for completing the task so this is gonna be up front one it helps me know what its approaches are going to be before I even see them I can see a preview。

Two， this can actually be helpful for large language models if you haven't kind of summarized the task and summarized different approaches or reasoning。

 this has been shown to be helpful in many cases， so I'm actually asking it to do that at the beginning just to show you how you can tweak the pattern and get some possible improvements。

In this case， it does roughly the same thing that we saw before。And then I ask it。

 ask me what I want you to write a prompt for。The prompt I ask it is I say write a prompt for chatt GT to automatically detect questions in a chain of emails and summarize everyone's questions as bullet points beneath each question So the idea behind this is really this key part is at the end you can imagine getting behind on email and you want chat GPT or some other large language model that you trust looking at your email。

 that you put it in the whole email conversation chain assuming that you're following appropriate privacy and other rules around whatever content is discussed in that email chain。

 maybe you start with something like what movie or what restaurant people want to go out to eat when you have like a group discussion you get to these long group discussions and they've gone off the rails people have discussed other things thrown in jokes commented on other people's jokes and by the end of it you can't really decipher who wants to go to what restaurant and why because there's all this other random stuff thrown in so you might go and say。

Smorize the questions and people's opinions on it， and it'll give you maybe just a discussion about the restaurant and people's perspectives。

So you would dump this in and I say write me a prompt to do that and so it gives me three different approaches。

 one write a prompt that instructs chat GPT to first identify all questions in the email chain and then extract responses related to each question and finally summarize the opinions as bullet points。

Approach to， write a prompt that asks ChetGT to simulate a conversation where it plays the role of a summarizer and notice it's basically using the persona pattern here in its own prompt for itself。

Asking the user to provide the email chain and then generating the summary with bullet points and then finally it says write a prompt that presents the email chain as a case study that's an interesting approach I wouldn't have thought of that what's interesting is a case study it probably read lots of case studies so it's probably good at thinking about how do you think through a case study。

And ask chattGBT to provide a summary report that includes the questions and the corresponding opinions and bullet points。

 and then it gives me each of the different prompts so chattGBT。

 your task is to analyze the following chain of emails and identify any questions that were asked for each questions。

 please summarize the opinions expressed by the participants in the email chain as bullet points beneath the question so it's generated its own prompt for itself。

Prompt approach to chat GBT， let's simulate a conversation where you play the role of a summarizer and it goes on to discuss it and then it has a slightly different format down here for how it wants things presented。

And then finally prompt for approach3， chat GBT， consider the following chain of emails as a case study That's really interesting and a completely different approach that's that's when I just would not have thought of from the beginning Now maybe if I went to business school or something I would be more thinking of case studies and this is a natural approach but this is something new to me and so I can learn from how to write prompt and now I have three completely different approaches that I could go try out without having to think of of myself and I've also learned something maybe case studies and presenting you know different points of view on an idea as a case study is a good way to get output from chat GBT。

Now， what would I like to do next Well I'd like to take my alternatives and I would like to evaluate them some way and one way to evaluate output。

 particularly when it's just text and you want to figure out how good does it look does it seem to solve the problem is just use the large language model to evaluate its own output or to evaluate the output of another large language model Now usually you want to do this in a separate conversation right you don't necessarily want to tell the large language model you know now evaluate yourself。

 sometimes that leads to worst behavior where it just says， oh， I'm right know。

Sometimes what we want to do is take that into a separate conversation and evaluate it。

 and I'm basically asking it， how would you write prompts to take your own output and evaluate。

 how would you write prompt to evaluate the prompts。

And so I say write a prompt to evaluate several different prompts for summarizing the questions in an email conversation and the different stakeholders perspectives on the questions。

And so then it gives me three alternative approaches again， approach one。

 write a prompt that presents multiple prompts to chatGBT and ask it to evaluate each prompt's effectiveness and summarizing questions and stakeholders perspectives。

 approach to write a prompt that instructs chattGBT to simulate a conversation where it plays the role of an evaluator and the user provides different prompts for evaluation so again。

 using the persona pattern。And then write a prompt that asks Cha GT to provide feedback on each prompt and suggest improvements of any。

And so there's there's kind of a different take in each one。

 the last one is really about how do we improve each one。

 second one is using the persona pattern act as an evaluator and the first one is really to evaluate effectiveness so they're kind of different sort of takes on the same idea。

 but now I have three completely different ways that I could go and take my prompts that it generated itself and kind of look at you know and evaluate them using chatGBT itself。

😊。
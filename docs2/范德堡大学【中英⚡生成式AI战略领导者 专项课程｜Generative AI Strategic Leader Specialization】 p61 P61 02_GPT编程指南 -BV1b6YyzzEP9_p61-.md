# 范德堡大学【中英⚡生成式AI战略领导者 专项课程｜Generative AI Strategic Leader Specialization】 p61 P61 02_GPT编程指南 -BV1b6YyzzEP9_p61-

To really use generative AI effectively， we have to start thinking about programming it now if you're not a software engineer or a computer scientist。

 this may seem alien to you， but it's really quite simple and it's important for actually really getting the potential of generative AI and I want to show you what I mean by this so I want you to start thinking about programming generative AI to do something。

Now what does that mean Well let's take a look at a really simple example I've gone into ChaGBT and I've said I'm going to the grocery store。

 really simple statement， not a lot of context about what this means what it's supposed to do and how does it respond that's great。

 do you need to help with making a shopping list or perhaps some tips to what to buy。You see。

 I'm just giving it a simple statement now。What if when I want it to respond。

 I want it to respond in a happy excited over the top way rather than something sort of really flat what would I do well I could go into this conversation I could say redo your last response and make it really exciting。

But there's another way to get there and it's to start thinking about time telling it what to do in the future before you've given it the message that you want it to change its response。

 So this is is I could go now and I could say update your response。

 make your response really excited and over the top。Like that。And now it says， oh wow。

 that's absolutely fantastic heading to the grocery stores like embarking on a thrilling adventure。

 but the challenge with this is right， I had to go after the fact and tell it what I really want it I had to go and give it that additional context and let's say you were trying to build some type of custom GT for somebody else to use。

 you don't want them to have to know to go in after the message and say what you want。

You want to be able to tell them up front， go do whatever you want。

 and it will figure out the right way to respond so let's see how we can do that。

Rather than thinking about just saying here's the message。

 instead we can start giving it time and programming， we can say from now on。

 and this is really an important we're saying in the future， messages to come。

Respond every message with a super excited and happy tone be way over the top so what I'm doing is I'm not giving it a message for right now。

 I'm giving it a message about what to do in the future。And when you start thinking about that。

 describing what you want done in the future is programming。

 that is programming how it's going to respond in the future when you give it a message or maybe you're creating a custom GPT and somebody else gives it a message。

 but it's creating that context。So from now on， respond to every message with a super and excited happy tone。

 be way over the top， I'm going to the grocery store and now we get that excited message that we saw before。

 wow， that sounds like an epic journey。And so you see， we're programming it。To respond differently。

 Now， what are the types of things we might want to program in。

 We might want to program in tone like we have right here。

 How what does it sound like when it responds， Is it really formal。

 We could have gone in and we could say from now on， respond in an extremely formal way。

That's one thing we could have done we could have said be really over the top and excited。

 we could say be neutral and so we can adjust the tone that it uses to respond to the user What else can we do？

Well。I'm going to go in and I'm going to ask it， give me some unique ideas for how to use generative AI that combine all of my roles in what you know about me now he doesn't know anything about me。

Doesn't know who I am， doesn't know my name， doesn't know where I live。

 doesn't know what my job title is， and it gives me a bunch of sort of generic stuff。

 some of them actually I think randomly hit the nail in the head。

 personalized learning and development tools well that would be something that's interest to me。

Creative content generation， data driven wildness。Not so much of an interest to me。

 AI assisted project management， innovative problem solving sessions。

 enhanced environmental initiatives， interactive historical learning experiences。

 all of these are exciting things， but they're not really about me they're not personalized to me so what's something else we can do to program it well we can program it with background knowledge。

It could be knowledge about who I am and where I live， or it could be knowledge about my business。

 about my university， it could be knowledge about how I want things done in terms of like here's background knowledge on process that you should know and so I can do that I can give it background knowledge I can say from now on remember the following things and use them to help you respond my name is Jules White。

 I'm a professor in computer science at Vanderbilt University。

 I'm the senior advisor to the Chancellor in Genrative AI Enterprise and Education Solutions。

 I live in Nashville， Tennessee and I teach a large class on Promp engineering on Coursera。

So now I've given it background information about me。

 and now if I go and I say give me some unique ideas for how to use Gen AI that combine all the roles you know about me。

 now I get things that are based on where I live， national themed AI generated educational content。

 AI drivenn enterprise innovation workshops and you see it's pulling。Information it knows about me。

 I've given it background information so we can program tone。

 we can program it with background knowledge that it should base its answers on。

 not just the knowledge that it was trained on， but we can actually give it new knowledge that just baked in now people talk a lot about having to train a new model。

 but in reality most of the time you don't even need to train a new model， you just need to tell it。

 here's the information that you don't know today that you need to know in order to respond or solve the problems that I want you to solve。

What else can we do with programming them Well I've gone through and I've taken Vanderbilt's web page and I just copy and paste it I just highlighted everything on Vanderbilt's webp page here and I have dumped it into chatGBT so it's got tons and tons of unformatted information what does it do with this right Well what it does is it starts summarizing because that's a common use case that a lot of people use it for so it starts summarizing all of this stuff which is great if that's what I wanted。

 but I wanted something slightly different。I wanted to say from now on。

 turn everything I give you into CSV， this is a comma separated value or tabular data like you could import into a tool like Excel or numbers。

And so I want it to no matter what I dump into it， it gives me structured information out that's a very different way of behaving than chat GPT normally does I'm totally changing its standard behavior and reply to do something much more complex。

 which is turned into data I'm basically giving it instructions about what to do and how to respond by default。

It says， okay， I understand and now I go and I dump all that same Vanderbilt information from the web page into it and now you see what it's doing。

 it's turning it into data， so it's creating a version of chat GPT that's customized that knows no matter what I give you。

 turn it into structured data that I can do something with。

So you're beginning to see that we can program。The large language model to do unique and new things that we normally don't think it can do。

 we normally think oh， it doesn't know about me。 it doesn't know my background or it won't know the user's background that comes in and starts interacting with it because when we start think about customizing it for other people we want it to know who they are or if we start thinking about customizing it for other people and we're going to be representing our organization we may want to customize the tone that it takes and how it communicates with people if we're a law firm。

 we might want it to be very formal and very， very careful and what it says and if we're a really fun brand。

 we want want to be over the top and excited about what it's doing great job that you're going to the grocery store。

 but in order to do that， we have to customize that tone So programming it is all about telling it what's going to happen in the future we go from being able to just say I'm going to the grocery store and getting a flat response to this to going and saying from now on which are really。

powerful words， everything into the future go and do this differently and now we get the big over the top answers like we have here with emojis and wow。

 we can program what it knows about you or the user， the background information it has。

 we can program really complex things like that no matter what you give it， it turns it into data。

And suddenly we can build office applications， work applications， all kinds of complex things。

 these all come from the simple idea that we can program how it responds in the future in the conversation that's the key to really。

 really building exciting customized versions of large language models like ChatyBT。


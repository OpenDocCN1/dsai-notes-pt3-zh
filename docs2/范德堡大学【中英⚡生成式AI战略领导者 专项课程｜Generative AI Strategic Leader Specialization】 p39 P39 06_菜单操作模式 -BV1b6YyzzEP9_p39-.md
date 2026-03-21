# 范德堡大学【中英⚡生成式AI战略领导者 专项课程｜Generative AI Strategic Leader Specialization】 p39 P39 06_菜单操作模式 -BV1b6YyzzEP9_p39-

When we're working with computer software， one of the things that's really useful is that programs typically have some menu with a series of actions that we can apply。

 so if you've ever used word processing software， there'll be like a file menu that allows you to run an action to open a new file or save a file。

 you may have a menu that allows you to search and replace different pieces of text。

So this idea of having a menu and different actions that we can run is a really useful concept。

And sometimes when we're working with prompts and prompt engineering。

 and particularly when we have a long conversation。

 it can be helpful to sort of develop the equivalent within a prompt。

 basically define a set of essentially a set of actions that we can run and order to work in the conversation without having to repeat these long prompts。

Or we want to just sort of codify certain actions that are helpful to people and bake them into a prompt at the very beginning of the conversation So let me give you an example of this we're going to look at using the menu actions pattern。

 This is a pattern that allows us to get the same type of behavior but end prompts so we're going to develop a menu that is a series of actions that we can run and actions are basically you know essentially a prompt it's basically a set of instructions that we're going to give the large language model into order to do something at a particular point in the conversation。

So here is how this works。We describe what we're going to type in order to trigger the action。

 so I say whenever I type right。Bullet point paragraphs。

And let me talk about this in more detail in a minute。

 so don't worry if this seems just doesn't quite make sense yet so whenever I type this phrase right and then I have in less than greater than bullet point and then paragraphs。

 these are placeholder so basically I'm saying I'm going type in right and then a placeholder for a bullet point and then a placeholder for a number of paragraphs。

You will write content for the selected bullet point， bullet point。

 so basically what I'm saying is I'm going to give you a bullet point that you need to go and write the content for。

And then I'm going to tell you how many paragraphs of text to write。

And then you're going to go andrite the text， so basically I'm developing an action which is before all I could do is expand my outline。

 so when I talked about the outline expansion pattern I talked about being able to rapidly expand the outline and now what I'm going to say is at some point I'm going to be able to tell you。

 no go and turn that into text rather than just outline so I'm creating a new action。

I'm also going to go ahead and keep my original action。

 which is just expanding the outline So I say whenever I type and I have a placeholder for bullet point。

 you will expand that bullet point so what I'm saying is if I just type in like 3。5。

2 which is a bullet point like a number in my outline。

 it'll know that it means expand that in the outline if I instead say write which is kind of a keyword and then a bullet point and a number of paragraphs。

 it knows that that means it's supposed to write the text for it So I'm definingfining a menu。

 I now have two actions I can either expand my outline or I can write the text for part of my outline。

And so now I'm developing more sophisticated capabilities for my outline expander。

 I'm turned it into a real program now something that I can interact with。

So let me show you an example now here's my first action being run， I'm saying right 3。5。

32 Now what that means is right。The content for the bullet point that was labeled 3。5。3， so label 3。

5。3 you're going to write the text for it or for that part of the section in the outline and you're going to write two paragraphs。

And so what we see is it takes。The bullet point 3。5。3 from the outline。

 which was experimenting with tone and style variations。It then writes。

Two paragraphs of text for that bullet point， so I've created an action， I've defined it。

I've created a menu of actions and I've defined it。

In my in my prompt and now I can run that action and get get the text generated。

 And so then we see it prompts us again， what do we want to do next。

 So this is actually not part of the of the text it wrote so it did write two paragraphs then ask me what I want to do next。

 So then now I'm going to go back and I'm going to do exactly what I did before。

I'm going to say expand on 3。5。2。So this is what I did before and now it knows the difference and it knows that's a different action and so it goes and expands 3。

5。2 and puts the outline for it again。I then go down and I say okay， give me text for 3。5。

2 and notice something kind of interesting。 I'm actually making a typo here。

 but it's kind of being smart and inferring what I'm supposed to do and this is kind of an interesting thing is it's a very sort of it tries to help you out。

 tries to get things right and it knows based on the pattern that what I probably meant was right 3。

5。2 and I wrote text so it's kind of a smart act menu action system。😊。

And then it actually goes and it pulls in that bullet point 3。5。2。3， sorry I said that wrong， it's 3。

5。2。3， and then it writes one paragraph of text， and so I've created a basically a complex program where I can expand my outline if I want to or I can have it write the text for a part of the outline。

 but I don't have to repeat myself， I get to use this simple little format and I've explained what the format is and now I can rerun the actions whenever I want to。

So one way this is useful to me is like if you're doing the same task over and over with prompts。

 it can be helpful to use the menu actions pattern to basically define a set of actions and kind of like on a menu of a prompt that you use all the time and then whenever you want to iterate really quickly using that content and those set of actions。

 you can just introduce that menu actions prompt and then go and use those actions over and over on the output that you're getting in order to manipulate it or do something。

You've basically built yourself your own program within the conversation。At the same time。

 sometimes an organization may have。A number of people are doing the same job and they can share actions with each other to help automate different tasks and so this could be really useful to help people be more effective with their jobs and to share with each other useful prompts The other thing is is you don't have to worry so much about remembering exactly how you worded it right once you've written the action once and gotten it to work in the menu then you can reuse it over and over without worrying about you know not quite getting it right when you do it and then that leads into a final thing that's really useful about the menu actions pattern is that within an organization you can share a set of common menu actions that everybody should use and you can codify the best you know wording for those prompts。

😊，And for those actions and what they should do， maybe codify best practices into them and then share them across the organization。

 So it allows for knowledge， sharing and reuse of different prompts and then easy application of those prompts。

 You could also imagine baking these into a root prompt for something like a customer service portal where you want to give people certain actions they can run to look up information about their account。

 they could do it in natural language， but you could also describe here are some actions you could run and allow them to get better behavior out of it。

 So the menu actions。😊，The menu Aions pattern is a really powerful pattern that allows us to easily reuse other prompts and actions that we've used to share them with others and develop knowledge bases of them so that we can become more effective prompt engineers。


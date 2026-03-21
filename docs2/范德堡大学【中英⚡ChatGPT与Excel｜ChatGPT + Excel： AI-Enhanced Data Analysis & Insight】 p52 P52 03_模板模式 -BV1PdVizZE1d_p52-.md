# 范德堡大学【中英⚡ChatGPT与Excel｜ChatGPT + Excel： AI-Enhanced Data Analysis & Insight】 p52 P52 03_模板模式 -BV1PdVizZE1d_p52-

Getting a large language model's output in exactly the format that we want can be a challenge sometimes。

So the next pattern that I'm going to teach you about is going to help you get exactly the format you're looking for and tell chat GBT where you want the information that it's producing put into the format。

 So you're basically going to give it a template and then chat GPT is going to go and fill in your template just like you might do with an assistant where you'd say here's the template that I use for you know creating these form letters and here are my different placeholders within my template and then your assistant could go in and fill in that template。

😊，That's exactly what we can do with the template pattern。

 So the idea behind this pattern is we would like a specific template followed for our output。

 and we can describe that template to chat GBT and then have it produce all of its output using that template。

 Now we could do this with other approaches like few shot examples。

 But we're going to do this with the template pattern in this example。

So here's what the template pattern looks like， we say I'm going to give you a template for your output。

 we're queuing the large language model that there is a template that's going to be in play and it needs to follow it。

Capitalized words are my placeholders， so we're telling it when you look at the template。

 if something is capitalized， that's something that you're going to replace with the content that you're generating。

Fill in my placeholders with your output， so there's our cu to it to go and replace the placeholders and please preserve the overall formatting of my template。

 We don't want chattGT to just decide on this own what the format should be and ignore everything that we're giving it in terms of instructions。

And then I say my template is， and I've got this sort of funky little template down here and I'm going to talk through it。

So I have question with three asterisk in front of it and then three asterisk following it。

 Now what this is going to do actually is this is using some knowledge of how chat GT in the chat GT interface formats。

 the information that we see。 So those three asterisk are basically going to mean you're going to italicize in bold this is like a heading。

 so it's going to say question and it's going to be in italics and it's going to be in bold。

And then we want it to fill in a question， so question which is on all caps。

 and notice we're differentiating between things that are part of my template and things that are capitalized。

 which are things that are placeholders that it's going to fill in。And then we're saying answer。

 similarly， it's going to be an italics and bold。And if you want to figure out how this works。

 this is called markdown。 So we're basically chatGBT is rendering the output to you in markdown。

 So I'm just using this knowledge to help me out a little bit。

 and so I'm creating a template that includes markdown。

 and then we're using a placeholder for answers。 Now you can guess I'm going to have it generate questions and answers。

 This is what's going to come next。 But right now I'm just telling that what the template looks like。

 Here's what my template is going to be and I'm going to ask you to fill it in and then I tell it I will give you the data to format in the next prompt。

 create 20 questions using my template。And of course， it says it's happy to do that。

So then what I did is I paste it in from Wikipedia。An article on Pao Indians。

 my son was studying Pao Indians at school and so I thought it would be fun。

 can I generate some questions about Pao Indiands for him and I see if he can answer them or learn more and it might be interesting to talk about these questions and so I paste that in and then what we see is we get output that follows the template that we gave it。

So if you remember， the first thing was question and it was not in caps。

 so this was something we wanted it to preserve， and then we had question in all caps。

And Chat GT has generated a question about the Pao Indians who were the Pao Indians。 Now。

 interestingly， it has decided to put this in all caps too。

 which actually kind of works for the format， I didn't actually mean for it to put it in all caps。

 but it works。And then I had answer， which was not capitalized。

 and then I had answer with something to be filled in that was in all caps。

 and it fills in the answer。 so it's creating questions about Pao Indians， who were the Pao Indians。

And then it's filling in the answer to the question。

But the whole thing is structured using my template， and I told it generate 20 of these questions。

 and so it's basically repeated my template 20 different times， but filling in the content。 Now。

 notice these are like really powerful placeholders。The placeholder I gave it was question。

And so it has to understand what is the meaning of the word question it looks at and has to understand to some degree and people may argue it's not really understanding anything。

 it's doing something else。I'm going to talk about it in terms of understanding。

 because I think that's a natural way to talk about it。

 If we later discover it doesn't really understand。

 it doesn't matter that the template pattern is a great way of using this。

 and it's easier to talk about it in terms of understanding。

 So it's understanding the placeholder that it means question that your question that you generate should go here。

And then it's understanding answer， answer is where the answer to the question should go。

 and it knows from my prompt that it's supposed to generate 20 of these questions based on the content I'm giving you。

 so it's extracting 20 questions about the paleo Indiands。

And producing the question and the answer and formatting it according to my template。

 like we see here， and we get a bunch of questions that we could go and then have a discussion about。

So there's a first example of it。We can also go and take it and say take this。

 you know a little bit further So I took my colleague Doug Schmidt， and I imagined like。

 well what if I wanted to go meet Doug Schmidt for the first time and I wanted to try to know something about him and have something to talk about and make sure I was versed on his background so I could intelligently talk about what he was doing。

 what he was interested in his background。And so I just took his web page here。

 Now ChaGBT explains to me， hey， I may not have a version of this web page before 2021。

 It's kind of fascinating that it actually is able to take information from a web URL little trick it may not be up to date。

 Of course you should if you're gonna use this before meeting somebody own the information and make sure it's actually correct。

 but it could give you a starting point。 And so then it goes and generates 20 questions using the format that I gave it about my colleague Doug Schmidt。

😊，Now looking at the。Questions so far， they seem pretty good now if we wanted to do this in a more reliable way。

 we could have pasted in the actual questions or pasted in the actual information from his web page in order to get information about him and generate 20 questions。

Now， I'm going to show you another example because I talked a little bit about these placeholders that。

They're not just placeholders， like there's a real deep understanding of the meaning of the placeholders when you're using the template pattern。

 you don't just have to think of them as being really easy to match。

 they can also be kind of smarter placeholders， a placeholder that you might give to another human being if you wanted to explain to them how to use the template you're providing。

So let's look at this example。I'm giving it the same sort of preamble for the template pattern。

 I'm still using capitalized words， I'm still using markdown to try to get this formatted in a way that I want。

 this case it's going to create headings wherever I have these hashtags。

And so what I'm doing is I'm saying bio and name， so I'm going to paste in information about a history of Vanderbilt。

 and I would like to get basically a list of people from that history of Vanderbilt。

And I want the names of the people and then I want an executive summary for each person and a full description for each person。

Now I'm stating that my executive summary is a one sentence summary。

 so you notice my placeholder is more than just go and talk about this person。

 I'm actually putting constraints on what I want there。

 I want one sentence that summarizes you know this person's role as described in the information I just gave。

And then for full description， I say， I want a one paragraph。Summary。

 now you can imagine you could go and capitalize。A complex set of instructions。

 a one paragraph summary that only considers their you know history as part of Vanderbilt。

 you know before 1800。 Now I haven't actually tested that one out。

 but I suspect it would actually work。 but the key thing to note is I'm giving it more than just a simple you know match。

 I'm actually giving it a match summary， go and create a summary here。

 but I'm also putting constraints on what it should be。

 it has to be a one paragraph summary you know or a one sentence summary。

 And so this is like a power of the template pattern is that we can kind of have complex instructions in the placeholders that we're actually going and replacing。

😊，So now I'm going to take a look， I past quite a lot of information in。

 and this is what we get as a result。Is we get the headings as we had before with the name that all makes sense。

 But then if we look at the executive summary， it's exactly one sentence。 So it's not only。

Fillling in the template， but it's filling it in with the rules that we've described in the template。

 so now we've got a one sentence summary in the executive summary。And in the full description。

 we've got a one paragraph description。 And it goes through this for every single person that it extracts from the。

From the information that I give it， so the template pattern is a way to help you get the output that you want in the format you want。

And you can use the placeholders in really sophisticated ways。

 they can be something that can semantically extract information so I can dump a bunch of information in and say I want to know the people and it has to understand who are the people in this box you know this bucket of information that's just been dumped in。

 it has to be able to extract the people， and I can say I want a summary of each person。

 but it has to be one paragraph so you can have instructions and constraints on these placeholders。

You can also have sophisticated things。 We could have said， for example。

 what is the role of each of these people in the history of Vanderbilt。

 And it could describe their role。 So the placeholder。It can not only format the information。

 it can not only do sort of simple extracting and matching， but it can also do sophisticated things。

 it can follow rules or do things that would be really time consumings for a human like take an extract information that would require a human to read through and understand and then put it in。

 So we're saying create a one sentence summary of this person。 Well。

 if I was gonna to have an assistant do that they'd have to go read all the information and then make a list of all the people for each person they have to write first the one sentence summary to try to capture everything about that person and then they have to go write the one paragraph summary。

 So that's really fast really sophisticated intelligence that it's using in the key to getting the output that we want from it is using that template problem。

 We're saying this is the format that you're gonna to give it to me in。

 this is exactly where everything goes and here are these sort of really sophisticated rules in the placeholders to help you decide what goes in how it gets formatted。

 what to exclude。😊，It's a really， really powerful pattern for getting information in the format that you need and getting the right information put into that template。

😊。
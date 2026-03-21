# 范德堡大学【中英⚡ChatGPT与Excel｜ChatGPT + Excel： AI-Enhanced Data Analysis & Insight】 p51 P51 01_游戏玩法模式 -BV1PdVizZE1d_p51-

One thing that I find really helpful when I'm trying to learn a new topic or improve my skills in Sarah or just have fun is to play a game。

And when we can play games with new knowledge that we're trying to acquire。

 it's usually a fun way to to really become masters of that knowledge and test our ability to use it。

 particularly if the games are fun and sort of challenging。 and so。😊。

One of the patterns that we can use is called the gameplay pattern So the idea behind this pattern is we're going to ask chat GPT or another large language model to play a game with us and it's going to decide the rules it's going to be the game master in most cases Now we can give it a variety of different sort of scenarios that can govern what its role is in the game but we're going to look at gameplay where the large language model is serving this sort of the game master it's creating the rules and it's driving the game and so。

😊，We can then take a game and we can say， I'd like a game on this topic or that has these basic rules fill in the rest。

 one of the things that's really nice about this is that if we say create a game。

And we give it some basic structure around the game。

 it can tap into its training data in order to populate the game with content so if you think about games like you know getting the rules right obviously takes a lot of thought but then there's a whole other challenge for a lot of games of how do you create a lot of great content to go with that game and so this is a pattern where we can tap into the training data from the large language model in order to help it populate the content now it can also do a pretty good job of deciding the rules as well。

 but we're not gonna to necessarily look in these examples that complex rule generation。

But we are going to look at a really useful example of this and I'm going to show you how to create a game to improve your own prompt engineering skills。

So the basic pattern of this is to say we are going to play a game and we say involving or about or whatever。

 and we want to give it the topic， we really we start off this pattern by saying we are going to play a game and here's the topic。

And then we decide some more information about what are the rules of the game。

 So in this case we're going to have some simple rules You're going to give me a simple task that can be accomplished via prompting you So I'm telling it we're going to play a game。

 You pick task where I could theoretically prompt you in order to solve that task So you imagine what we're trying to do is have it play a game with us where it's going to give us a challenge of something we would try to write a prompt for and then we're going to write the prompt and see if we did a good job and then it's going say we're gonna to say your task should all have a reasoning or programming component to them although they shouldn't require source code Now the reason I do this in this game is you get more interesting questions in my experience。

 if you have some logical component to this。 remember we talked about prompts as a way of programming a large language model that everybody can be a programmer and that's what we're trying to get at。

 We don't just want to generate a bunch of poems about lonely trees。😊。

In the middle of a field you know we'd like to do more than that we'd like to have to solve problems that have some sort of logical or interesting component to them and that's what we're getting at here with this prompt so we're going to build a game it's going to challenge us to develop different prompts and then we're going to try to make these tasks that we're solving related to sort of programming or logical things。

Now next we go on and we give it some more rules， I will try to write a prompt to solve the task。

 you will give me the output of the prompt and tell me how well it solved the task。

 so it's going to give us the task。And you know we're also we're having it ask us questions so it's going to give us the task。

 the task is going to be something that can be solved with a prompt， we'll write the prompt。

 and then it will run the prompt in order to generate the output that that prompt would have output and then it's going to tell us how good our prompt was。

 so this is interesting we're actually having it play a game where it's pretending to be prompted and then telling us how good our prompts are。

Ask me questions until I tell you to stop。You will ask me a question， wait for my response。

 and then ask me another question after telling me how I did， ask me the first question。

And so it says，Great， let's get started with this first task。Given a list of numbers。

 determine whether the list contains any duplicate elements。 if it does return， yes。

 there are duplicates， if it does not no duplicates found。

 So now we've got a specific prompt engineering task。

 we're going to have to figure out how do we write a prompt where we give it a list of numbers and have it return one or the other of these things。

 And it's kind of interesting right， This is one of the challenges that we often face when we're dealing with a large language model is getting it to generate a precise output。

 And so it's given us something where。It has sort of a thought component to it of like how do we design and tell it about what it is we're trying to achieve。

 but also it's also got an output component and we're trying to match a specific output format。

And then it says， please write a prompt for me to solve this task。

So I'm going to solve this task using a few shot examples， so I give it a list of numbers。

 I show it some examples， I say basically in my prompt I say here's the numbers 1，2。

3 and then I have duplicates and I say no duplicates found， then I have numbers 2，2，2 duplicates。

 yes there are duplicates and so I'm following the output format it told us。

And then I'm going through and giving you a series a few shot examples to solve this。

And then I prompt it， my final end of my prompt is basically duplicates question mark on the list I just gave it。

 when is solving the problem that it's asking for or trying to we'll see what it says。

 but basically I'm asking it does this list have duplicates and we're hoping that what it says is no duplicates found and match this exact format that I provided before and it does。

 it says no duplicates found。Right here。And then what's nice is it does the other part of the game that we explained your prompt effectively comm the task and provided examples of different cast or of different cases。

 the task was to determine whether a list of numbers contains any duplicate elements and you provide it with examples based on your prompt that was able to correctly determine the list that's not contain any duplicate elements and then it goes on and it says let's move on to the next task so now it's playing the game so it's moved on to the next task。

Given a sentence， count the number of words in the sentence and return the results in the format。

 the sentence contains x words where x is the number of words。

 so it's giving us an output that I have to produce and notice it's giving an output now where I have to put the output in a different particular format。

So before we just had to go and say there's duplicates or no duplicates。

 but now we're having to do something a little more complicated。

 we're having to count words in the sentence and then make sure the count shows up in a particular place in the output so is exactly testing our knowledge of prompt engineering and some of the patterns and other techniques that we've seen in the past。

 please write a prompt for me to solve this task。I'm going to use a pattern called the templatelate pattern to do this。

So what we say is I'm going to give you a template for your output。

Number is my placeholder and all caps fill in my placeholder with your output。

Please preserve the overall formatting of my template， my template is。

 and then I have the sentence contains number words， so I'm going to solve this problem。

 here's my prompt to go and solve this problem and then I say how many words are in the following sentence the cat jumped on the mat。

And it says the sentence contains six words， which we see is exactly the format that it was looking for and then it tells us it grades us on our prompt。

 so what's really nice about this gameplay example is that from now on you can go and use it to test your ability to do prompt engineering and you don't have to think up what are prompt engineering tasks that I could try out you can just use this prompt to have it generate the content for you。

 it can think up the ideas of the problems for you to solve with prompt engineering and we can see in a simple example it's already gone and tested some different dimensions。

 a prompts for us and given us some opportunities to try out some different patterns。

It then goes on and it gives in another interesting one。Given a date in the format，YY why， MMMM， DDD。

 meaning year month of date determine whether the year is a leap year or if not。

 if it is a leap year the year is why why why is a leap year if it's not， and so how do I solve this。

 I'm going to go through and give it some few shot examples kind of similar to I did before。

 but it's testing my ability to figure out what do I do to solve this in this particular case。

And then it gives us the right output that 2023 is not a leap here Now what's really nice about this。

Is remember， it's supposed to be checking our prompts and testing our prompt engineering skills。

And I want to show you something that I didn't even notice until it told me and tested me。

So I said date 2009，724， so July 24th， 2009， and then I asked if and then in my example。

 I said leap year right here， and then I said the year 2004 is not a leap year， so my prompt example。

Actually had a mistake because I'm asking it if 2009， you July 24th， 2009 is a leap year。

And then in my example， I give it the wrong template， I say the year 2004 is not a leap year。

 it should have been the year 2009 is not a leap year。And then it actually notes that right here。

 it says there's a small typo in the third example。

 the year 2004 is not a leap year should be the year 2009 is not a leap year。

 but this did not affect my ability to understand and respond to the task。

 but it does give me feedback of my prompt engineering it also shows me I need to be careful about the examples I'm giving it if I make a mistake in my example in this case I got lucky and it didn't affect things。

 but it could on future ones。It then goes on， gives me a new one which I didn't actually go and solve。

 given a string of characters determine whether this string is a palindrome。

 the string is a palindrome， if the string is not a palindrome， return。

 this string is not a palindrome， replace string with the actual string。嗯。So。

It's getting a little repetitious in here， but we could go in and inject additional sort of ideas to help tailor the output even more。

 So you can imagine we might want to go in and。Target our prompt engineering a little more now。

We've been learning a lot of prompt patterns in this paper。

 so one way we can adapt this game is we can give it a more specific topic about the type of prompts we're trying to develop so in this example I'm going to take the description of the recipe prompt pattern and what's helpful is you can go to our prompt pattern paper and you can actually take a little section or explanation of those patterns along with the name and you can provide it into this game as context and it does a reasonable job if you provide enough information on the pattern and examples of asking you questions that would use that pattern to solve it。

So in this one I go in， I actually modify the game and I say all of your questions should revolve around the recipe prompt pattern。

 This pattern provides constraints to ultimately output a sequence of steps。

 given some partially provided ingredients that must be configured in a sequence of steps to achieve a stated goal。

 The pattern is not about cooking per se。 Now I added this in here because I knew I knew knew knew in my heart that it was going want to ask me cooking questions which that's fine。

 but I've done enough of those but creating a complete sequence of steps to achieve a goal。

 given an incomplete list of intermediate steps。 So I really want to use this。😊。

Cooking is obviously a natural way of talking about recipes。

 but I don't want it to clue in too much on that， I'd rather do some other interesting tasks。

And so then it says your goal is to create a prompt that instructs me to generate a sequence of steps for assembling a simple wooden bookshelf The bookshelf has four main components the top and bottom panels。

 the sides and the side panels and the shelves you have been provided with the following ingredients。

 attach the top panel to the side panels insert the shelves into the designated slots。

Using these intermediate stepsts create a prompt that will result in a complete sequence of steps for assembling the bookshelf。

 Remember， the prompt should be designed to fill in any missing steps and provide a clear order for completing the assembly。

 Now， what's interesting is。This is kind of an interesting prompt because it has to have an understanding of a bookshelf and its structure。

 and you would have to go and write a prompt that's going to elicit the right problem solving behavior on assembly of a bookshelf。

 so it's kind of a cool little problem。I then went and I took it and I said， all right。

 well let's use another one of the patterns from the paper and so I adapt and I say we're now going to change the topic of your questions。

 the topic is now the context manager pattern， and then I'm basically providing the intent and context from the paper and I'm saying this paper or this pattern enables you to specify a remove context for conversation。

And I'm not going to go into the details that did a pretty good job and asked me a question about the Eiffel Tower and its construction。

Then I went and I said change the topic again， I said we're going to change the topic of the question。

 the topic is now the template pattern。And I describe what the template pattern is。

And it actually does something that you follows what is exactly said in here which you might want to generate a URL。

 so we might get all URL， so we might want to like tweak this a little bit but it does a good job it then gives me a task your goal is to create a prompt that instructs me to generate a URL for a product page on an e-commerce website the URL should follow a specific template structure and it gives me the structure。

 product ID/lash name， the product ID and product name or placeholders that need to be replaced with the actual values。

So you can see how I've got this game， it can test me on prompt engineering。

 so I'm learning about prompt engineering， it can actually give me helpful feedback。

 it caught on a typo and my few shot examples。And then I can go and tweak it， I can say okay。

 now the topic is we're going to do a game based on this particular prompt pattern。

 now we're going to do one based on this pattern。And what you'll see is you'll get interesting content that will come out of it and challenges of things that you can try to prompt Now they may not all be good。

 they may not all be interesting， you may get in a rut where they're kind of like getting repetitive but that is on you then to think about what additional information do you go and inject into this game to make it fun again or to make it more variable I was pretty surprised at the quality of questions that I got and it brought in a lot of topics like assembling a bookshelf is not what I would have thought about that's certainly an interesting one or when it asked me about information related to the Eiffel tower and its construction all of these things kind of bring fun to the game or is it a leap year or not all of these things are kind of interesting ways and all I did is gave it kind the base rules and then the topic area and then it pulled in all this information to populate the game with things that kind of help keep me engaged new content。

Ideas to challenge me and make me have fun and in this case。

 writing out the rules is a lot easier than thinking up all the content for the game。

 which it does really effectively。
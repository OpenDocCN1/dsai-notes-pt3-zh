# 约翰霍普金斯大学《Excel商业分析｜Business Analytics with Excel： Elementary to Advanced》中英字幕 - P14：13_新员工分配.zh_en - GPT中英字幕课程资源 - BV1nFA7emEc6

All right hi everyone welcome back In this example we're gonna now do a special type of transportation problem so remember just where we are in sort of the grand scheme of things we have LP or linear programming problems we then did a special type of linear programming problems called transportation problem and now we're going to do a special type of transportation problem called an assignment problem an assignment problem is exactly what it sounds like we'd like to assign something to some other thing now in this example here on the screen we're going to assign workers to offices but you can also imagine assigning computers to jobs or people to task but for any sort of assignment it turns out you can use a transportation template to do that pause video for a second and read the little problem on the screen just to get a sense of where we're going and have a spreadsheet and work through this with me as we go along okay we're going to rebuild our transportation template instead of just kind of copying it for the old one again repetition sort of lease understanding it's better to build it a bunch of times so you can understand where all the pieces go。

Here's sort of the situation imagine you're in HR right now a company has three new hires。

 Jones Smith and Wilson and you can send them to any office in Omaha， Dallas。

 New York or Miami so you brought in three new recruits offices have a need。

 you can send them anywhere you could only do one candidate per office you can't send a candidate to two different offices and the costs for the relocation only way you get a new job they pay for you to move a little bit the relocation costs provided by the firm are here so Jones to Omaha for example would be $800。

And your job with the goal here is you want to minimize the cost you want to minimize the total cost so compare this if you have the last example open。

 you can compare it to what we did last time once we had our shipping cost table。

 we then created a wrapper row in a wrapper column with the supply and with the demand。

 pause the video for a second， think about what the supply would be and think about what the demand would be from our quote unquote factories or our stores。

 what would go in these wrapper columns。Ready well it turns out Jones can only supply one Jones so the supply here would actually just be one and that's true for Smith and that's true for Wilson and this is just one person not actually 1 so let me fix that it's just the number here so Jones can only send one Jones elsewhere you can't take Jones and split them and send them to different places same thing for the offices there's a restriction here only one candidate per office so the number of people that were sending to Omaha demand would be111 and one。

This is what makes an assignment problem different than a general transportation problem。

 This is always true。 This is the difference。 In an assignment problem。

 there are no wrapper columns on the cost table。 it's assumed to be one。

 And since they're always one we don't write them So we actually leave is completely blank we leave it off。

 we can turn off all the formatting as we go through。

 So you're never going to see a wrapper column in an assignment problem。 It's implied to be one。

 everything else is then the same。 So we take our cost table and we copy it and this will now become our assignment table used to be our shipping table。

 how many of we' going to do assignment table。 we have our offices at the top， we have our。

 I guess workers at the bottom and now we still do we clear out the middle and these become our decision variables who's going get sent where what could happen。

 You can imagine something like a couple ones could appear when we turn off the dollar formatting。

 and let's think about what this means if you have some row。

To ones it means you're sending Jones to both Omaha and to Dallas So one is gonna be like a yes like we send one Jones to Omaha one of the Dallas and zero or blank is like a no So this obviously is a problem I can't send Jones to Omaha in Dallas So how do I prevent this from happening Well。

 first off， just like before I need to keep track of the sum of the row and this is important now so my sign what does it need to be for this to actually work I can't have zero that would mean that Jones doesn't get assigned I cant have two It means Jones is getting assigned to two offices So what can I have to single apostrophe equal sign here to get the equal sign it has to get to one Where is that coming from each candidate gets assigned an office。

You can't just say welcomelcome to the firm Jones we don't have a home for you doesn't work that way so this is what you're after this is gonna be your constraint and notice how we're setting it up over here on the right that's fine Sor does not care where things go only you should care where matters so this is obviously no good so just to keep things sort of dummy numbers that make a little bit of sense we can put in some dummy numbers just to make sure the spreadsheetss working。

So this idea of adding up across and these are formulas inside of F11 F12 and F13 I want them all to equal and then exactly one you don't need to put equals one we could type this right into solver but in the interest of transparency we're going to write this out and then of course we're going keep track of our total across the bottom row now what is that going to keep track of while I add up everyone going Oha and this is the constraint now that only one candidate per office I really want this number it could be zero right I have three candidates and four offices。

That can happen。 Someone's not going to get a candidate。

 but I just want to make sure that this number is less than or equal to one should never have a column with multiple ones in it。

 What does that mean it means I send Jones to Omaha and I sent Wilson ma that's not allowed only one candidate per office So the sign is always going to be less than or equal and then I'm always always just going to type one So the only formulas in this table center it and make it pretty。

 The only formulas in this table are the usual formulas that we use for the transportation problem where I sum each column and then I sum each row inside last but not least add your objective here we want to minimize our relocation cost we will color code this cell gray and what's this going be How do I know how much going to cost Well think about it if I send Jones to Omaha it's going to cost me $800 So to keep track of that I would multiply $800 by wherever Jones。

sent if it get sent to Miami， let's say its a  zero under maha and a one then I would want to include the $1100 relocation cost so hopefully you see where this is going this is once again a big sum product of all the costs and the decision very the formula text so you can see the formula but it's once again a good old sum product This is a true cost in dollars so we can format it as such now the question is what's the best way to assign people to these offices minimizing the total relocation and the spreadsheet model is ready head over to data head over to solver we're going to set our objective cell which for me is in V19。

We're going minimize this one please don't maximize the relocation cost we're going to have a whole bunch of variable cells here now this is a four by three table and we're going to subject it to the usual constraints so let's batch upload these things I want the candidates to be assigned one office Now this is where really need the one here because I certainly come in here and just type one although you could also just link it either one works but I want the candidates equal 1 so F11 F13 and then I want to add another one。

Where I take how many candidates are being sent to each office。

 total rowno instead of the column and I say I want that to be less than or equal to and once again I could type one or in this case it to be different highlighted across and I hit okay。

 this should feel familiar this is all the same our setup up for the objective function。

 putting it in solver， check the box。This says the variables can mean on negative。

 select simplex LP and itself So found a solution Thank you， solver， you hit OK。

And now we have this solution and once again， the summary sentence is extremely important again。

 Excel， the computer will be very good at finding the answer that it will be very terrible at communicating or explaining the model back to your boss or to a client So our summary sentence here what does it mean remember zero means no and one means yes we would send Jones Smith to New York and Wilson tomaha for a total relocation of 2000 and 400 again just I love doing this because I see people still watch it they say oh there's no way that can be the best answer I say go find me a better one and they sit there and they play and they try to do it and of course they can't 2400 is the absolute minimum the best answer for this relocation All right nice little assignment problem again the only big difference what's missing here are the wrapper columns in the cost table and you have an assignment problem you don't need those you leave those blank really do miss them you can certainly put ones in there but it's best practice to leave it。

Great job on this example， I'll see you next time。
# 约翰霍普金斯大学《Excel商业分析｜Business Analytics with Excel： Elementary to Advanced》中英字幕 - P16：15_公主新娘.zh_en - GPT中英字幕课程资源 - BV1nFA7emEc6

Hi everyone， welcome back Today we're gonna learn about integer programming。

 This is another type of linear programming where now our decision variables all have to be integers as a friendly reminder。

 what is an integer integer like a whole number 1234 when not allowed to have 1。51。61。

7 so we only want whole number solutions inside of our linear programming problem It turns out that this restriction is not as easy as it might seem solver will take care of all the math on the back end。

 but one thing that you the human should not do is run solver without adjusting for it for integer programming and I'll show you how to do that and I'll show you sort of the common pitfalls that can happen but just remember as we talk about integer programming this is all fancy names。

For you know LP， which is linear programming and then we have our transportation and we have our assignments and now we're sort of working with integer programming。

 So all of this falls under the umbrella of linear programming Since it is a linear programming problem read the problem pause the video about Liz Bailey and the owner of Princess Pris and let's see we can go through and solve it and it's gonna feel very similar to something we've done prior。

 I just want to introduces new concept of integers as our decision variables So if you want pause the video and get this started as we go Okay Liz Bailey is the owner of Princess Pris。

 she uses radio to market and two types of ads are available those during prime time and those during other times So peak and off peak so let's create our little spreadsheet here we will give it a header and we're gonna introduce our variables so this should feel like our old template we have two types of ads to buy we have peak or prime time and we have off peak so let's label them accordingly and as always we will label our decision。

green and let's center to make things look pretty each primetime ad costs $390 So that's gonna be a cost to it。

 costs usually go under constraints。 so maybe we'll put our constraints with our budget and let's line these up remember you have to line these up with the corresponding column so each prime time or peak ad costs 390 well throw that in there and reaches 8200 people now we want to if you read the problem a little bit we want to maximize the number of people reached so that's gonna be part of our objective more people a better so we put 8200 usually we put our coefficients of the objective function here and sometimes we put dummy variables in the green cells I'm gonna go a little quickly through this one because we've done this one before off peak ads So this is our column C now they cost 240 so we'll put the cost under our budget they reach 5100 people5100 on average Now here's the budget。

So remember how this works on our constraint table we always go three past where the decision variables end。

 so I have two decision variables it ends in column C so I'm going to go1，2。

3 past maybe I have more constraints to come let's see so we add them on we put our LHS for lefthand side we put the sign and then we do right hand side as a reminder the sign and right hand side these are numbers these are not formulas budget you want to be less than or equal you want to be under budget you don't want to be over budget and our budget is 1800 you can format this to money if you want you can leave it as is since it is a budget it's implied that's all fine。

We'll send everything the left hand side is a formula this is going to be the sum product of the decision variables。

 how many of each a you buy。Coma and then the cost for them understand this formula if I buy one peak ad it's cost me $390 I multiply them together If I buy two off peak ads it's two times 240 I multiply them together my total cost then adds them up so beautiful some product to get me my87 so this is actually okay if I buy one and2 but now I need to keep track of how many people。

That I reach so let's put our objective what is the point what are we trying to do the number of people reached and our objective here is a max we will label the cell as people reached and then we will color code at gray and how many people do I reach if I have one peak ad that reaches 8200 people well once again I multiply it together and when I add up the number of people reached by the peak adss and then the number of people reached by the off。

So let me put some formula text in here see what's going on and remember the left-hand side formula text I can show that as well a nice use of the sum product formula Now we have some other constraints that we just need to manage that's fine she wants at least two primetime ads at least two primetime ads so the primetime ads has to be at least two we've seen this before remember what that means it's got to be greater than or equal to two we also want no more than six off peak ads so off peak ads have to be less than or equal to six we can do that that's fine。

So let's put that in， no more than six off peak， at least two peak。

How does it work remember in the constraint table you never put variables you never these are all numbers in here。

 but what numbers go inside of these tables， they are the coefficients when you write out the algebraic inequality they are the coefficients that occur on these variables so when there's nothing here remember it's like an invisible one so it's like one times the number of peak variables or one times the number of off peak variables so the coefficient always goes inside the box so no more than six that behave the number of off peak。

Should be less than or equal to six， that's fine and at least two peak。

 one peak should be greater than or equal to two and string table is going to look something like this。

I'm going to leave the other cells blank， remember blanks are treated as zero。

 and then I'm going to put dollar signs on。My left hand side formula。

 this lets me just drag it down so I don't have to keep typing it every single time right so then we check do we have all the constraints matched so let's go over to solver。

Let see what we find So data solver we set our objective。 That's the gray cell as always。

 we want to maximize the number of people reached and the variable cells are the green cells subject to the constraints。

 Here we go so let's add them in there I have left hand side I have two less than are equals together so I'll batch upload those less than or equal to and then I'll do the right hand side so I have the two budget and no more than six off peak as constraint and I have to add one more I want the lefthand side to be greater than or equal to the right hand side for the contraint that at least two peak ads are and I hit okay I select simplex LP for linear programming This is still all a linear programming problem and I hit solve solver found a solution all constraints and optimality conditions are satisfied Thank you so much solver we hit so let's start doing this here let's just write this down summary sentence say the following we're gonna recommend consultants here getting paid lots and lots of money for our work。

Peak ads。And 4。25 off peak。As and hopefully as you write this， something feels wrong。

 How do you buy 4。25 off peak ads。 I only want to say every fourth word that doesn't work。

 So this is the problem。 This is the problem right here。

 one of the constraints that's implied by the problem sometimes they're clear about it sometimes you have to sort of infer it is that you can only purchase a whole number radio ad you can't buy 0。

25 or radio a so this is the problem and what's interesting about this notice if you did this you're gonna reach the most people the reach here will be 3800075 people but here's the warning to you。

 This is what I see a lot of students do warning warning warning this should not be you a lot of students say well I'll just round it do not round your answer That is not how this works The math behind this is a little complicated little tricky again Excel takes care of it all for you but do not round your answer just to show you why not if you have two peak ads。

So you round it four off peak。What would the reach be， let's find out。

 so let's just round this to four for a minute。And that would reach 3680036800 people so that is sort of the wrong way to do it。

 that's a common mistake what you need to do is tell solver that these things can all leave you integers and that's the new skill for this Everything so far should feel very similar The only thing to do is add integer constraints to solver。

This is the correct way let's go back to solver for a minute if I hit add this is a constraint。

 the variables have to be a certain thing， this is a constraint， go back to your variables。

 your decision variables。And in the dropdown menu there's a you know the first three less than equal to equal greater than equal to the fourth one is integer IT this says I need these numbers to be integers When you select integer in the middle dropdown it automatically populates the right dropdown to integer so hit OK。

And you'll see that now appear in the constraint。One thing you should check is under this options bar。

There is a checkbox back here that says ignore integer constraints Sometimes this is checked if you're putting on the integer constraint and nothing's changing you might have this check by accident where you're just ignoring that the reason for that is the algorithm that solver runs is more complicated it takes more memory it takes more time if you don't have the problem set up just right everything we do in this class would be perfectly fine but if you just make up numbers and you put on integer constraints you can really bog down your computer and freeze it if you're not careful so this is sort of like a safety but for everything we do all the numbers are fine So go back to the problem hit okay make sure you have this new integer constraint on your variables and you hit solve solve or found a solution all constraints are satisfied so we hit okay。

Look at the answer that solver came back with solver came back with the correct answer， which is by。

Four peak adds， one off peak a to reach。A maximum。Of 37900 people。

 So you can imagine if your consultant firm ran solver and then recommended two peak ads for off peak ads。

 you would your solution reaches 36800 people the correct answer So do not round the key here is do not round The correct answer when you put in the integer constraint and solver is to buy four peak ads one off peak ads and you reach 37900 people almost1000 people more than the other rounded answer So this is a big warning watch out this will be of course in any quiz the wrong answer choice that'll be there tempting you to pick but add the integer constraint。

 do not round if you just run the regular LP problem All right so go over this example make sure you can add the integer constraints and now going forward look for integer constraints。

 do you need the variables to be integers That's a question you have to ask yourself as you go through and try these problems All right great job on this example we'll see you next time。


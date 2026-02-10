# 约翰霍普金斯大学《Excel商业分析｜Business Analytics with Excel： Elementary to Advanced》中英字幕 - P18：17_二元投资决策.zh_en - GPT中英字幕课程资源 - BV1nFA7emEc6

Al right， Hi everyone， welcome back。 We're gonna to do another specific type of LP problem today called a binary example。

 we're going to use it to make an investment decision。 This is mildly amazing。 I love this。

 because you can get decision making down to a mathematical formula。

 You can let solver make decisions for you。 I think most people know this。

 but just in case not binary variables means0 or one。

 A lot of people have heard this with binary numbers， but binary means0 or one for decision analysis。

 How we're going to use a spreadsheet to make decisions for us。

0 is going to correspond to a no A one is going to correspond to a yes， Now。

 there are lots of decisions that are binary， should I hire someone should I not。

 Should I approve this project， Should I not。 There are also lots of decisions that are not binary where the answer might be sometimes or maybe or a percentage So not every decision is going to be modeled by a binary decision variable。

 but sometimes you can here， read the problem if you haven't done so。 We're going to。😊。

we should invest by some all or none of these seven investment opportunities。 This is a yes。

 no decision。 Do I buy the block of shares for Texas Transoil this cost。 Yes or no。

 do I buy the block of shares for Vp at this cost Yes or no。

 We're not asking how much money I put it we're not asking what percentage of an investment do put towards it this is just yes or no and when you have a problem like this then you can model it and solve it optimizing on something using solver so you can get decisions equations right read the problem if you haven't done so already and let's think about how we're going model this example is going to be a yes no on finding the right investment to maximize the return Now so you know we're looking at here we have a bunch of constraints here by the client That's fine We have7 stocks that can be bought in block。

 Now watch the units here are in thousands So one。is 480000。 We'll leave the number small for Excel。

 But then when we write our summary sentence， we have to watch our units。

 The return here in thousands of dollars， the expected annual return is all positive we have up to 3 million for investing。

 So in a perfect world if I have the choice where I know everything is gonna have a positive return I picked the highest one here Houston drilling and I look at and say well this is gonna be the highest return。

 but I have these constraints that are just going prevent me from buying only one thing What are the decisions that I have to make I have to decide yes or no to the7 stocks。

 that is7 separate decisions。 So our variables here， which are binary now。

 and I'll just call them x1 x2 I don't have a good name for it。 It's like yes or no do I buy it。

 I don't want to list out all seven stocks。 So x1 x2 x3 x4 x5 x6 and x7 and I'll shrink the columns a little bit as well just so we have nicer formatting。

Maybe I'll move this over here。 And it's important to realize what this represents。

 This is the first time in any problem that we've done。

 We're not representing the variables with a dollar amount。

 We're not representing the variables with how many bags of coffee beans or something It's a yes or a no。

 It's almost like text。 We're going represent them， of course， with numbers，0 or1 because of course。

 Excel doesn't like text。 but we have seven variables。 we've seen problems with7 variables。

 the number7 shouldn't be too scary。 This isn't the thing that should concern us。

 It's the use of the variables。 The fact that it's going to be0 or1 to decide should I buy the stock or should I not。

 You can imagine just like last time when we had mixed integer problems So some variables were binary some were not。

 This is a particular type of integer， but instead of any integer， it's0 or one。

 It's a binary integer problem。 Now， think about what I want to do here。

 I want to optimize my return。 So my objective as a financial investment firm would be to maximize maximize what maximize the。

Turn on this。 So this would be my gray cell。 And this one here I might need to make a little bigger。

 instead of me expanding the column out。 what I'll do is I'll merge it。

 And let's think about each investment。 What does it return。

 So this is where again the units are in thousands。

 So maybe put my units here on the side just to remind myself that the units or thousands。

 And if I buy the first stock。 I expected return of course， is 5 the second stock。

 its return is 89121104 and 75 So here's how this is gonna work。

 I'm going to ask solve to find me the best results here。

 and solve is gonna come back with a bunch of zeros and a bunch of ones。

 So let's just pick ones across them。 it can't give me any other number。 So I'll do 1，1，1，1。

 maybe a01 means yes， purchase the block of shares for Texas oil1 in X2 means yes。

 purchase also the block of shares。 This is yes or no。

 It's either buy it or don't buy it not puts this much money towards it。 but yes or no。

 if a0 comes back。Then that answer is no。 Don't buy this one。 So buy it， don't buy it。 Yes or no。

 As a reminder， zero is no and one is yes。 Now， what is my expected return。

 How can I do a formulation on this， if I buy the block of shares if I buy the transt oil block for $480 Thatll be my cost that'll be a constraint that'll build into the $3 million for investing then my return is 50 So these are my in thousands of dollars remind myself those units over there my return for this block of shares is 50 my return for this block of shares is 80 What's nice about this is multiply this together you still get 50 if you multiply the one in the 80 you still get 80 when you multiply the0 in the 750 being no cancels the return。

 So if you do a sum product which is exactly what we're gonna do again is still an Lp program on the decision variables all seven of them their expected returns line up the two blocks of cells close the parentheses and hit enter I'll show that formula here So you have it you can see that the sum。

is doing exactly what you want When there's a one it adds the expected return。 And when there's 0。

 it adds 0 times 75， which is saying nothing。0 times 75 is 0。

 If I turn all of these off if the solver comes back I won't do this， of course。

 but'll say what if you turn all of them off， then the return is00 times 50 plus0 times 80 plus 0 times 90 is always gonna give you0 Play around with this And again。

 dummy numbers here are key。 if I did every other one you can check 50 plus 90 plus 110 plus 75 is exactly 325。

 this will be in dollars and this will be in thousands of dollars。 I to watch my my units here。

But it's doing exactly what you want。 It's adding up the ones that are turned on and it's turning off the ones that are turned off。

 This is the power of 0 and1 and how you can use this in decisions Now I have these 1，2，3。

4 constraints that are on here So let's start to build our constraint table and move the text over a little bit as always even though we have seven decision variables we're going to go1。

2，3 over so I need columns I j and K here and we're gonna put some constraints down。

 I have about four we'll build a nice table we're still going to use our lefthand side our sign and our righthand side Now let's think about what this means in terms of the constraints。

 The first one says at least two Texas oil firms must be in the portfolio。

 Someone loves Texas oil So Texas oil which ones are my Texas oil firms here you may not be as familiar with some of the cities in Texas but just in case you are not the Texas one here is well obviously the trans Texas oil is a Texas firm Houston is a big city in Texas So I'll copy that。

As well， just to remind you。 And then there's one other called Texas Peroleum。 these are all fake。

 of course， but Texas， nonetheless。 So the first one。

 the fourth one and the fifth one are all your firms from Texas。

 And the client has demanded that at least two of them must be in the portfolio。

 So let's label this constraint。 at least two Texas。

 which ones we say those were it was the first one， the fourth one and the fifth one。

 So I'm using a one here， again， one means turn it on Yes to purchasing that one。

 And now how do I build this in constraint。 If you want。

 is a good place to positive video and think about how you would do that What's the sign I need at least two at least two。

 this is the tricky one。 at least is the one that is greater than or equal to。

 It's a little bit counterintuitive So greater than equal to two and the left hand side is no change。

 It's still our good old sum product。What is it of the variable cells。

 comma and then these numbers here in the constraint table。

 So I'll stay on that so you can see the formula。 It is the same formula that we've always done。

 but realize what's going on here。 It counting how many of these firms there are this two is coming from11 times1 So x1 is on transtexas is on x4 is off So that's0 it's contributing0 to the sum and then one of these is on So I put a1 in here to almost count it。

 we've seen this before when you want to count what the variable is。 but then becomes becomes a1。

 And if I just happen to have some combination where let's say the t ones are off So x1 x4 and x5 or off。

 this will be one plus0 plus 0。 that's what's happening here when I'm adding up these numbers and I get that the lefthand side is a1 and this combination would not be in my feasible region。

 it would fail the constraint and this would never be returned as a solution by solver So that's the first one if you want pause the video and see if you can get 23 and 4 for your con as we go All right contraint number two。

No more than one investment can be made in foreign oil。 So no more than one foreign。

 So now we have to think of ourselves which ones are foreign oils。 There's two of them here。

 British petroleum and Dutch shells， these are your two foreign oils。

 So we'll keep track of if x2 and x3 variables are turned on and it says no more than one。

 So my lefthand side。 let's actually put the dollar signs in before I forget So put dollar sign B dollar sign 8 dollar sign H dollar sign 8 just drag this formula down。

 no more than that is less than or equal。 and it says one。

 So no more than good old great third constraint。 one of the two California stocks much be purchased。

 So you can have one but not both。 So California constraint here。 which ones are my California again。

 if you know some cities in California great if you don't I'll tell you here the California would be San Diego It's a wonderful city in California。

 California Petro， obviously that's California as well。

So I have x6 or x7 that I really have to worry about。 So let's think about this for a second。

 How can I say one of the two stocks must be purchased。

 So I definitely need to keep track of x6 and x7。 my lefthand side formula is not gonna change that just gets down my right hand side says one of two stocks must be purchased。

 So I need to make sure So what's happening right now some product I get0 times1 which is0 So this is like counting how many are turned on What is the thing that goes in sign here。

 if I do less than or equal， then having no California stocks would be okay if I do greater than or equal then having two would be okay and that's a problem as well。

 I'm only allowed one So what's my sign here if remember in the dropdown this for solver equals is a choice Here's one where we equals I just want this equal1 thatll be okay notice if I turn both on then the sum turns into a two and that's not allowed。

 So this wont pass if I turn both off if I turn both off then I get a zero back and that's no good。

Because I need one of the two。 So really what I'm allowed for is just one of these two So equal be my sign here。

 that's a good one。 that's a new one。 And then last but not least of course。

 this is my budget and it says up to 3 million for investing to purchase a single block per the table So if I buy the first one。

 what's the cost And now here's where I use these numbers in the table Here's where I use these numbers in the table if I buy x1 what's my budget budget is good old fashioned less than or equal and I got to be careful here It's 33 million but all my numbers are in thousands。

 so you have to be very careful here。 I want to put 300。

0 I don't want the extra three because that's included in the units all over the place。

 so I really I want 3000 here So watch out for that that's a little tricky could could have everything perfect I mess that up with the budget anyway so if I buy the first one。

 what's it gonna cost me that's gonna cost me 480 if I buy the second one。

 what's that gonna cost me 540 and you can work your way across the table So 680 just copy it correctly。

170510 and 900。 And when now when I do some product for all the ones that are turned on， it will add。

 it will sum their cost to my total， and this cost should be under 3000 or 3 million。Allright。

 I think everything is good to go。 Let's go ahead， give it one quick check。 make sure you agree。

 data solver the box pass up。 Let's set our objective。 That is the gray cell for me。

 it's in sort of the merge B12。 I hope it works for the merge。

 we'll find out I want to maximize this cell。 This is my return My variable cells are the seven variable cells for me in row 8。

 subject to the following constraint。 I want to add a couple constraints here。

 Now nothing is batchable。 I can't do it。 So I just have to be careful here。

 let's do the first one that for the Texas constraint So the first one is greater than or equal to2。

 let's add another one。 This is my no more than one foreign。

 My left hand side is less than or equal to1 let's add another one。

 My California constraint is equal to one use of equal there。

 and then last but not least is my budget So I want this number to be less than or equal to this number Left hand side less than or equal to the right hand side。

 and now here's the。New one。 Now I was gonna hit solver and solve it。 but let's just go right to it。

 Let's do one more and add。 just like before when I had to tell solver that the variables had to be integers。

 remember binary is a specific type of integer problem。

 I still have to tell solver that all seven decision variables。 at least all7 in this case。

 you can imagine cases where some of them are binary。 Some are not have to be binary。

 and that's right here it's the dropdown after integer is the next one in the list。

 it is a binary decision variable。 As usual it populates the binary constraint。

 you hit okay and it gives you the box back。 Just make sure you agree。

 objective max variable cells theres the binary constraint。

 select the box to make unconstrained variables non negative select simplex LP and then you can hit solve solver found an integer solution。

 say thank you solver and come back and hit and here it is。

 So solver is coming back and say I want you to purchase x3， which is your Dutch shell。

 X4 Houston drilling x5 and x6 and my return here。Is $360000，$360000。

 So convince yourself that this purchase of x 3 through x6 of the third through 6 option actually meets all of them。

 Do I have at least two Texas oil firms。 Sure do。 I have Houston drilling and Texas Peroleum。

 Do I have no more than one investment in foreign oil。 That's right， I just have Dutch。

 I don't have British， Do I have one of the two California's purchase， Yes， I do。 I have X 6。

 which is San Diego， but not X 7。And lastly， did I stay under budget。

 turns out my budget here is 2890， which is under my restriction of 3000。

 So that would be my summary sentence。 So the only thing that I just would caution about in the summary sentence。

 There's no you kind have this here So you purchase you can list these out。

 I'll just say x3 through x7 in the interest of time4 a return now just be careful here is 360。

 it's not dollars，$360。 It's000 just watch the units and that is the maximum return。 again。

 play around with this if you want turn these zeros and ones and flip around。

 if you can beat solver you won't be able to $360 is the absolute max where all the constraints are satisfied。

 You might be able to find better answers， but you're gonna break some of these constraints。

 which means you lost a $3llion client。 that's never a good thing。

 This binary analysis it takes making decisions down to a spreadsheet which is extremely extremely powerful。

 So go over this one， make sure you understand it great job on this one。 We'll see you next time。


# 约翰霍普金斯大学《Excel商业分析｜Business Analytics with Excel： Elementary to Advanced》中英字幕 - P19：18_投资组合方差.zh_en - GPT中英字幕课程资源 - BV1nFA7emEc6

All right， hi everyone， and welcome back。 One of the things that people do and sort of ask me after studying linear programming or energy programming。

 binary programming， assignment， transportation is they sort of make the realization。

 well not everything is a linear problem like not everything is a line。

 So this is all great in theory。 but what happens in the real world when you have lots of curves and the beautiful thing about this and you can apply this to nonlinear formulas。

 It's amazing。 So if you master linear programming。

 then you can actually get good at all sorts of linear examples where things get a little harder。

 of course is if you have more variables， you might need more powerful software to solve them the algorithms in the back get a little harder。

 but for small examples， you can see how this works。

 And then if you ever need you can go learn more advanced programming or use more advanced software。

 So let's do this one pause video read the example if you haven't done so already and then think about perhaps how you'd set this up。

 This is a brand new template for us So if you want to give it a try if not we're through it with me。

 Here we go。 So let's call this example or nonlinear template。😊。

One of the firstline formulas you see， especially in statistics is the formula for variant So here we're just gonna have two variables X and Y。

 we're gonna to keep things very simple just to develop a template and then we'll see another example next time but we have our two variables X and will be the things we want So we color code those green and X will be the proportion of money to invest in a stock and Y is the proportion of money to be another one So here's the backstory if you haven't read it already Ryan。

 a financial investor for Pb and is evaluating two stocks in a particular industry wants to minimize the variance So there's your objective right there and notice your variance formula again if youve seen this formula before you know has x squared that's a nonlinear term something needs to be done about that you want to minimize the variance of portfolio consisting of the two stocks but you still want to have an expected return of 9% and after obtaining historical data on past variances and returns he develops the followingline program and key here beingline So X is a percentage or proportion of money to invest in stock1 and y is the proportion of money to invest in stock All funds must be invested。

be constraint that says that whatever your percentages for x and Y are， they have to add to 00。

 So all funds must be invested。 So x plus y has to be 100 So we're still gonna have our objective。

 This looks the same。 and we're still gonna have our constraint table That's all historical returns on stock1 is 1% historical returns on stock 2 is 8% So we're going use that to get our return on to get an expected return or average return of 9 So how do I do this I definitely want to minimize my variance in finance for those who don't know variance is like risk want want to minimize to minimize my variance and the formula is 016 xd012 xy and009 Where's the x squared。

 Where's the X Y where's the And this is the beautiful thing about the linear programming。

 we our decision our objective and thing we're gonna add now to our let slide all this for a is our linear variables our nonlinear variables。

 So nonlinear。Do we need Well， I need x squared。 I need x Y。 and I need y squaredlinear。

 by the way here。 there's lots of ways to create nonlinear variables。

 linearar just means the variable by itself。 If you put them together in any way even xd or x Y or y squared。

 That is a non nonlinear variable。 You can certainly do s of x E to the x logs all your crazy formulas that you math。

 in here X has all built in of course and what you're going do here remember x and y are the things we're trying to find but we need xd x and we're do is calculate these are going be our formulas。

 says take x and squared。 so x squared great I need x Y I need x times Y use the asterisk for times and then y squared equals Yd and I'll show the formula So you build them out whatever you need you go and get them whatever you need go and get them the variables that still after x and Y those are still up above these are your now decision linear objective。

Is then our variance。 What I'll do now to set up the formulas。

 The coefficients on these variables can go below。 This is sort of the similar template that we have before。

 We'd like to see these things in cells。 I don't want to bur them inside a formula。

 you can certainly go into variance and just type out the formula。

 but then you'd lose the numbers on screen It'd be hard to check if you had to typo something like that。

 So I do want to see these numbers out front。 again。

 the point16 corresponding to the coefficient on x squared on x Y and on y square。

 who had other nonlinear， you would just go off and keep expanding this table to the right。

 But now we have sort of this new this is the new thing for this example。 nonline variable table。

 The variance formula is then the sum product of the variables， the calculated variables。

 The numbers comm the coefficients and I'll show that formula as well。

 Not if I put in some dummy numbers。 If we just plug in some dummy numbers。

 let's say 2 and 3 convince yourself this is working。 What is two squared What is。

36 what is y squared9s not as obvious to say what is4 times。16 and 6 times。2 and9 times。

9 and add them up。 but you can check that。 it does actually equal 9。9。

 So these are our dumy numbers I'd love to know what the right answer is to minimize variance。

 but don't forget I do have some constraints here All funds invested What does that mean as a constraint let me expand the column all funds invested means percentage this should be percentages。

 this is gonna be something like let me just make this percentages So 20 and maybe like 80% or something of that whatever the combination is I don't want to come back and say 20 and 20 I need all funds to be invested。

 So I'm still gonna have three past my variabless build out a constraint table three columns passed put on some borders will do our lefthand side will do our sign and we' do our right hand and all funds invested means that the amount invested the proportion of percent vest an x plus the proportion invested in y。

Well， this has to equal and we'll do single aporophe equals just to show the equal sign。

 And this has to equal here，100%。 And we'll do our some product formula on the variables and the coefficient。

 So this is all the same from before。 So I'm going a little quickly。 Hopefully you're okay。

 but I'll show the formula over here for the left hand side。So everything is the same。

 just add up the two percentages and because it says all funds must be invested。

 I really want 100% invested。 I don't want 20% and to be consistent。 you see here I have 0。4。

 So let's just make this a percentage and we'll keep everything the same so all funds should be invested great and then I want this other expected return of 9% so expected return of 9%。

The historical return on fund1 is 11%。 We'll put that in there and historical return on stock 2 is 8% so we'll take our lefthand side。

 I'll put in my dollar signs here I'll drag this down and I'd love to have more The 9% so we'll do greater than equal to 9% so we're working in percentages here and that is totally fine percentages are just numbers there are no other constraints here again。

 a simple example really to emphasize the new nonlinear aspect of this program。

 so we have a nonlinear variables here and notice we use them where do they could use not the constraints although you can imagine there could be examples where we need somehow a nonlinear constraint and you would just refer back to this table but really in the variance where they're coming from is being used in the calculation of All right so we're good so let's go to data let's go to solver and there's one small change here as well set your objective This is your gray cell for me it's be 11 I do want to minimize variance again variance is your risk by changing the variable cells the two variable cells are。

Not the nonlinear ones。 remember these are just calculated。

 What you're actually changing is coming from B2 and c2 the green variable cells subject to the following constraints。

 Okay， let's see here I have that all funds must be invested。

 so my left hand side has to equal my right hand side，100%。Let's add another one。

 I want my expected return to be greater than or equal to 9%。

 That is okay These variables here are not integers， percentages are not integers。

 they're not binary。 I do want like a number not a yes or no question but again you think about it and then you're okay I do want these things to be non negative it would be weird to come back and say invest negative 20% and here's the only thing that's new before I kept choosing simpleimpx Lp for linear programming This is very specifically non nonlinear these variables in here the calculations in here are nonlinear solver has a built in nonlinear solver Grg nonlinear so let's select that and hit solver found a solution all constraints and optimality conditions are satisfiedll keep solver solution and I have 93% to invest in X they don't tell me the number or the budget but just 93 of my budget in x and 7% and y and my variance and this usually is reported as a decimal although you could。

To do it as a percentage。 give back a reasonable number。

 dressing crazy when students give me back 9 decimals or something like that pick a reasonable number。

2，3 or4 as fun as your variance。 And then you'd write all this up in your summary。

 So just don't forget to include your summary sentence。

 Here there's no tricks about units or anything else。

 Just a new template that we're gonna build off of So wrap up the content of this course。

 So hopefully you see how this can expand。 go over this one。 make sure you understand it。

 Great job on this example。 I'll see。😊。
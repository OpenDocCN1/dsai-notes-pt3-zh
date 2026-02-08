# 约翰霍普金斯大学《Excel商业分析｜Business Analytics with Excel： Elementary to Advanced》中英字幕 - P6：5_第19洞.zh_en - GPT中英字幕课程资源 - BV1nFA7emEc6

All right Har。 welcome back。 We're going do an example that highlights some more skills in Excel and shows us how to do a little bit more modeling and some complex situations。

 So here's the question on the screen。 Please pause a video and read it if you have not done so already。

 this is a golfing example by design。 I would call it the 19th hole。

 the 19th hole sells golf club through its golf source throughout the US and demand varies with price See pretty normally sell for a higher price。

 people by less of it standard rules of economic in the last year。

 the demand that each price level was recorded below。 So below here is the table on the left。

 which I have copied into Excel， please make this table， if you haven't done so already。 Now。

 the company wants to estimate the relationship between demand and price。

 and then use the estimated relationship to answer the following questions And you can see where the first one's going。

 we're going assume cost of producing a set of clubs is 250。 assuming the price is a multiple of 10。

 what price should the company charge to maximize profit。 So once again。

 this is gonna to be a profit model where we look at the revenue and the cost。

 So the first thing I want to do。Data to get a better handle of it is I'd like to graph the data so let's highlight all the data head over to the insert tab and we can look at some of the recommended chart pick if favorite one。

 I think for this one a scatterpl is perfectly fine just to get a handle of what the shape of our data is Yes that's the thing what the shape of our data is and here we have as Excel tends to do a title that doesn't make much sense we might want to look at improving the titles update to price a demand and one other thing you might want to always consider is adding the chart element of both the X and the y axis this will help remind you what you're actually looking at the x axis here is your price this will be in dollars and the y axis let's update the title to be the demand Let's be mindful of the demands is in hundreds to get the actual demand we'd have to multiply all these numbers by10 but to keep things sort of close together so we could view them on a chart so we have this nice sloping curve we have this scatterpl and we'd like some sort of function we'd like some prediction。

To help us get what the demand will be at different prices this way， when I vary the price。

 remember as a manager， you control the price， not the demand， I can fill in sort of the gaps。

 So a lot of people look at a scatter plot and they know how to do one thing and one thing only let's see if this is you If I have a scatter plot I head over to add chart element I go to trend line and I hit linear and I add a linear trend line This is sometimes called the line of best fit。

 This is called the line of the least squares line or linear regression and people are very happy with their linear regression。

 It's a nice thing to do。 don't get me wrong。 the line itself is more cosmetic。

 the thing we're actually going to use here is the equation to add the equation go back to where you added the trend line go to more trend line options and then you have to scroll down to the very bottom on the right and you have to check the box that says display the equation on the chart。

 and when you do that it puts a little box with the equation sort of an awkward unreadable spot。

 but if you move it。To somewhere more readable you can see the numbers in there Now unfortunately。

 while this is great， there's a lot of math that went in to get this number it happens at the click of a button。

 you can't reference these numbers inside the text box there are other ways to get these numbers but for the sake of our model let's look at our linear model here I'm going just write the numbers over this is the slope of a line from the reminder that's Mx plus B are intercept which is our B is the number that's added here and then the slope which is our M know y M is used for slope it's a mystery for the ages that's something I let's move this over I'm just going copy them down so I have211。

31 and then negative003546 these numbers actually go on these are rounded numbers if you want to show more decimals or less you can format the way that numbers look I'm just going grab the numbers that are here just realize these are rounded and we're not working with the exact numbers and that's okay。

😊，All right， great。 So I have this linear model。 But one thing you might notice from the data is that the data starts to curve。

 It does seem to sort of bend around as the price increases。

 If you remember as easy it is to add a linear model。

 you might want to consider another type of model。 Like maybe linear isn't the absolute best one。

 And I've seen people model things on linear regressions because that's all they know how to do。

 and that's what they argue for。 So one thing I want you to consider is is linear the best model。

 I know it's an easy model and one you might be more familiar with， but is it linear data。

 Line modeling is usually when data has consistent slope。

 So it was a rate of change when it changes consistently。

 It seems to me that this price first demand is not having a constant rate of change。

 So let's look at another way to add another model here。

 Excel gives you lots of options for fitting a curve to a scatterpl。 we can pick some fancier ones。

 I want to show you that even on the main menu， there are some that are not shown you have these other ones your。

thmaker or polynomial。 you can look at the graph Also it helps you with the picture as to which one you're going for。

 I want to go with power。 Now this picture shows an increasing power function。

 Rs would sort of be decreasing， but it works exactly the same。

 I also have to once I select power once again click the box that says display the equation on the chart I close it and there it is it puts the equation a little bit in awkward spot。

 We're starting to overlap the trend lines or all the same color。

 it's a little difficult to see to be honest。 So I might want to consider if I was actually trying to show these graphs and again all I needs a numbers but I'm just trying to show you I might want to do three separate scatter plots if I really care to show the difference what I'm after here though of course。

 is the number on my power model So a power function Now for those who forgot what are the power function look like this is form a number in front a coefficient so y equals a and then the variables in the base raised to a power is like y equals x squared x squared is a type of power function。

 You could have two x squared。 So a would be2。B would also be2 or two x cubed。

 But the key point here is that the variable is in the base。

 and Excel will give you the numbers for both a and B。

 So we have a constant a and then we have our exponent， which would be R。

 over the columns to make this a little more readable and I want to grab these from here。

 the exponent B I know it's small but hopefully you can see it are you doing on yours。

 you get negative 1。908， that's fine。 Again， that's a rounded number that number probably goes on for more and more decimals。

 the problem is though if I look at my constant a， I have 6 E plus06 friendly reminder what that is E like handheld calculators。

 is scientific notation shorthand。 So this is like 6 times 10 to the6 So about 6 million or so。

 but let's remember I said you can format these to do whatever you want。 if you right click on this。

 you can format the text。 So I want to right click I have an option for format trend line label and it gives me this sidebar and it says okay this。

Label， what is it。 It's it picks a general。 Let's change it to a number and then you can already see it starting to change over here。

 You can pick how many decimals you want。 You can do this for any trend line for anything you want。

 we'll use since this is a very large number near 6 million。

 I don't need the decimals zero just to change it。 And then when you're done there's no like save button kind of happens automatically hit the x to close it out。

 And now you can see that it's updated both my numbers。

 and I probably didn't want both numbers to go to 0。 but I already grab the B。

 So we're okay notice it rounded it to minus2 but the key thing I want here is not 6 times 10 to the6。

 I want to get out of scientific not。 I just want this coefficient a of 58710。

6 again I have to write these numbers and store them somewhere else on my spreadsheet so that I can reference them later。

 you can't reference these numbers inside of these little boxes that are there。

 All right one more example just to make sure you get the hang of this and show you how many options you have obviously there's a lot more in Excel than what we're gonna do。

 But let's look at an exponential function。Maybe this is an exponential growth。 Once again。

 if you forgot what an exponential function looks like， it is similar to a power function。

 but the biggest difference here is that I have a number in front， as I did before。

 these are functions of the form Y equals。 instead of the base being X。

 My base is actually the number E E， the number is 2。718 and change。 So it's E raised。

 and then it's to the B X。 the B now is a coefficient on x。 So x， the variable moves back upstairs。

 This is different than a power function where it was the base。

 it is now the exponential E again is a number 2。78。

 So it looks like there's three letters in this formula， but E is actually a constant。

 So I need to know my constant which is going to be my a。

 and then my exponent B my B let's actually add that curve to the chart same as we did before。

 go to chart design， go to add chart element， go to trend line。

 Here we can click the exponential function。 Remember this just gives the picture。

 starting to get a little overlapping in my diagram。 The picture。

doesn't really help me that much though for what I'm after。

 I certainly need to do more trendline options。 click exponential and then display the equation on the chart it will give me the numbers that I need。

 and then I can sort of decide if I'm happy with the number of decimals that are showing or not I think for our purposes here it is perfectly fine。

 We're talking about remember at the end of the day here golf clubs so I think rounding to a golf club to2 decimals is perfectly fine。

 So let's see our constant in front is 466 do51 and then our coefficient B is negative005 I know it's small but hopefully you can see that once you have these numbers。

 again this all comes from the chart。 this is just storage。

 these are not calculated by equations on the spreadsheet they're just copied over once you have these things you don't really need the scatterpl anymore I'm going to leave it there but we' really not going to use this the point of this though a lot of people pick linear and they don't know why they have nothing really good to say this is what I've always done。

 So what I'd like to give you now is a tool。Where you can defend your model。

 you can say which one is best。 There are a couple ways to do this。

 but let's look at one called the mean absolute percent error。 and I'll write this all down。

 So first let's make a new table and we're going to do some prediction based on the different models and what I want to do is I want to copy my data。

 I want to copy the price data so I have it want to copy it down。

 I're going to make a new table about this big。 And what I want to do is look at the predictions based on different models。

 and we're going to do all three。 we can certainly do more we could do less but let's do the three here that we have linear power and exponential。

 and here's what I want to do。 this is like the x value。

 the price in our formula becomes the x value is the input。

 So when the price is $450 what does the linear model predict as the demand。

 does the power model predict as the demand。 What does the exponential function predict as the demand that means that I'm plugging them into the equation。

 I didn't write the linear one down， but I'm might as well hopefully you know this though。

PlusI'm going to plug in all my numbers so watch this linear is M the slope times the price is yourX plus the b plus the intercept。

So I'm plugging in the price。 Now， remember I know the actual number from the table。

 but I'm seeing what does my model predict。 I'm looking for like what are the values of the curve versus what are the actual dots on the scatterpl and you hit enter and you get some number。

 So once more here's the formula good old Mx plus B。

 And once you have that drag it down or double click it gives an error。

 So do as I say not as I do what did I forget to do here I need to do absolute referencing on the B16 so we could do a little function F4 that puts dollar signs on that says when I drag you don't and then the slope B17 should also get locked in place So really a21 is the only thing dragging if you saw that before I did job Now let's do it again that looks much better。

 so remember these are demands， these are actually golf club sold the decimals don't make a lot of sense。

 but just to sort of avoid rounding I'll make one decimal to remind you that these should actually be decimals we'll deal with them later。

 but one decimals fine I use the little rounding here。

 please don't truncate and causes some rounding errors which we don't really want。

The one more time delinear model Power model， I want the exact same thing。

 What does the power model predict。 So I'm gonna to take my power model。 Here's the formula。

 A x raised to the B。 So my a from the graph is this a large number near 6 million times X times my input。

 which is price raise it to the exponent。 That is B again。

 I need to lock in my values I'm not going make the same mistake twice。

 So let's lock in D16 and D17 putting the dollar signs in front。 hit enter when you're ready。

 I get some number。 It more decimals than we'll ever need。

 So let's shrink the decimals now before I drag it down。 and the power model gives me its prediction。

 these will be off from the actual data values And in a second we're gonna measure how far off。

 we actually are。 So there's my power Last function that we picked exponential function for no good reason。

 we want a then times E raised to the B。 So here's our constant a。

 let's lock it in now with our dollar signs and then time。Now be careful。 E is a built-in constant。

 If you want this constant Excel。 it's Exp。 This is the builtin E2。

78 oiler number if you want to use E。 So and then we put in we want B times8 So B is this value Use your dollar signs to lock it down for dragging and then times X which is our price This is the form of an exponential model。

 notice they're all kind of close or kind of close。

 so the question is which one is actually the best a model。

 I don't care how good your spreadsheet looks or how much it actually works It's only is good as sort of the assumptions behind it。

 So a lot of people just pick linear， but there are many other options out there。

 how do you know which one is best So these are our predictions based on the model So maybe we'll merge this show you we have these numbers And now the question we'reafter is so what What do I do with this Well let's compare this to the actual demand The actual demand So let's paste our demand values right。

So there we go。 Now these are actual numbers And what I'd like to do is have some way to sort of capture how close the prediction was to the actual model and we're gonna to do this。

 there's a few ways to do this， but here's just one of them。

 we're going to use absolute percent error so what is absolute percent errors a formula for this where the absolute part says we're gonna to use the absolute value and then we're going to take the difference between what was actually predicted versus what was actually obtained what the actual demand is so we're gonna take the absolute value let's start writing this out here。

 So absolute value。 by the way， absolute value in Excel is AB。

 some people make a mistake and they do like this vertical bar that's not true。

 It's a B is the formula。 So it's the absolute value of the linear prediction minus the actual demand So this will be the absolute percent error for the linear model take the difference take the absolute value notice that prevents you from getting a negative number in case the prediction is smaller than the actual demand So。

keeps everything positive。 We don't want any like accidental cancellations and then coming up with the lower error And then because it's a percentage。

 you want to then divide this by the actual demand feels like a percent error if you ever don one of those calculations。

 The absolute value is the only thing in there B sure you don't get negative numbers when you do that and you hit enter you get back a big decimal but we're usually after it as a percentage so let's format this to a percent And what this is saying is the absolute percent error of the linear model I should copy these models over the linear model to the demand is about 15% This predictions about 15% off from the actual value。

 once you have this， these are all draggable numbers there's no dollar signs needed I can just drag this down and it computes a percent error for each value it's kind of trying to measure how far off is a percent error the curve is or here the line is from the scatter plot and what you do with all these numbers is remember each point contribute some error some values are closer than other one So linear predicted 51 points。

And the actual value is 52 so this is a small contribution and an error。

 some are much further off like 34 versus 45 so you have all these numbers， what do we do。

 we take the average value of all these numbers and I get an average value and average error of 9。

7% so the average absolute percent error for the linear model is 9。

7% and what we're going to do here is we're going to do the same exact thing for all the models。

And this is why this is a golf example。 What's better。 a large error or a small error。

 We want a small error。 So we want to see what happens。 All right。

 so let's do the exact same thing for the power function。 Let's practice our formula again。

 so we have abs absolute value of the predicted minus the actual up the front seas divided by the actual again。

 we get a weird sort of decimal here。 We don't want that we can format that to a percentage。

 We can show one decimal to be fancy We can drag it down and then we can take an average is dragging the formula over So right away。

 you can see the power model is actually a little better。

 then the linear model has a smaller percentage error。

 so the power function models this be and we kind of saw that there was a curve built into the scatterpl。

 So perhaps that's not surprising as it may seem exponential one more。

 let's see the exponential beats the power again like golf low score is the winner。

 We do abs the absolute value of the exponential minus the demand divided by the demand close it up。

 convert it to。Percentage， show one decimal and drag it down。

 and then we'll copy over the formula for the average。 So we have two models here。

 notice linear is actually the worst of all the models and the one that has the smallest。

 the one that we're after here is going be our power model。

 So this is sort of in defense of the model we pick here。 Again。

 smallest value wins like offs that we're going to use the model with the smallest error。

 The power model does the best job of predicting the demand based on these prices。

 F that's keep moving along。 So now we have in defense of the power model。

 we're going to use the power model going forward。 This is the thing we're actually going to use。

 and we're going to remember we're still after this whole question has's been a while。

 but remind yourself the question。 Maxim the profit。 What price you're the manager。

 What price do we get to pick to maximize the profit as a manager。 You pick the price。

 You unfortunately don't pick the demand。 but you feel like you have a pretty good model and so let's actually model the business Allright。

So let's write down some of the information from before as a reminder what we have。

 we have a unit cost of $250。 This is per set of clubs format at this to be money。

 get rid of the penny Now we have our sale price。 This is like what are we going to sell it for This is the play variable。

 this is the variable in play what are we going to actually pick the only rule per the question was that this had to be a multiple of 10 For no good reason。

 must's pick a dummy number here。 I don't like to leave these saless blank because I want to make sure my spreadsheet is working if I'm selling it for $250 lets if I'm buying it for 250 let's sell it for $400 Why not And then once we have our sale here comes the calculations Let's compute the demand。

 demand now is coming from power model demand is coming from the power model This is extremely important。

 This is why we went through the trouble to figure out which model to use。

What are we going do here we're gonna go back and remind ourselves the formula for the power function a times x raised to the B。

 So here's a I'm not gonna drag anything so I don't need dollar signs on it times my x which is my input so the sale price and then raised to the B is this negative 1。

908 and I hit enter and so I'm predicting a demand this is actually not dollars。

 this is numbers here I'm predicting a demand of let's say 63 now be very careful here as a reminder this demand this is why it's all over the place here is in hundreds I might as well say what the actual demand is so I don't have to worry about the units and take this number that I found and multiply it by100 so let's start list out the formulas here that I'm using so one I play with the sale price that price based on my model lets me determine the demand let me fill in the gaps for the missing values then I compute my。

Actual demand， these are sets of clubs。 So let's kill the decimals and we'll multiply this by 100 mindful of our units。

 Let's go through and find our cost。 In this example， let's actually order what's demanded。

 So imagine the order comes in and then we play the order with the manufacturer。

 So we're only going get we're only going to buy what we have demand for。

 So the cost is going be the 6000 number here and then it's going to cost me 250 per set of clubs。

 And so as a business owner is going to cost me $1。5 million based on this demand。

 Let's multiply the two numbers together the actual versus what's there So we're gonna to fill every order as they come in and that's the only cost based on this model。

 the actual business cost of this is simple to show that this is really the defending the model is really the key to this problem How does this company spend money。

 I have to order the clubs that I sell。 how do I make money Well， I sell them for a higher price。

 very simple business model。I am going to sell the ones that have been ordered at their price。

 and this is the green cell， which we're currently have at $400。

 So I'm making more than I am spending。 and now I have my profit。

 Of course it is just my revenue minus the cost。 So I have all these values。

 Let's fill in the formula so you can see it and hopefully this makes sense and we can play around with it。

 So here's where sort of the rookie comes in versus the experienced person。 If you say wait a minute。

 I'm just buying these things at 250。 That's fixed why don I just sell these things for1000。

 Let's raise the price like crazy will make more money So watch it right now， I have 400。

 and I'm making 955。s a little under a million let's go nuts。

 sell for 1000 somehow by raising the price by increasing the distance between my cost and sale price。

 I've actually lowered my profit。 What tends to happen in these kind of models is that the profit。

 the thing we're trying to maximize tends to form a parabola downward。Facing parala。

 so we could sit here and try to understand the model a little bit like what happens if I sell at 800。

 What happens if I sell it 700。 Hopefully by now you're seeing where this is going。

 This has all the makings of a data table。 So let's come over here on the side and let's do a price as my input and then my profit as the number that I'd like the data table defined as a reminder you need a ghost sell that we're not going to use。

 but the table needs it and you're saying where is the profit in your model。

 So we're going to link back to B 43 as our profit。 And then this is just me。

 I like to gray out to sort of remind myself that this number is not really for me the prices have to be a multiple of 10 I know that I'm buying it at 250 so I'm probably not going sell it for anything less than 250 So let's start at like 260 and 270 and sort of work our way as far as we want we know that10 is too high but a heck。

 let's go pretty large maybe we'll go to like 900 or so。I don't know，800 let's go all the way to 600。

 Why not There's no right or wrong way to do this in the beginning And once we kind of have a feel of what prices maximize the profit。

 then we can narrow and change our values here but right now I have a table in multiples of 10 from 260 to 600 fantastic I don't want to have to fill in every single value the profit that is what a one-way table is for so we highlight the table by the way notice I don't highlight the text of my header but I do include this sort of ghost cell I head over to data I go to what if analysis I go to data table and I remember this is the thing that the recording doesn't capture so let me grab a screenshot of this box just to remind you this is saying for oneway table here notice our inputs our column we have a column of inputs so it's asking you where in your model is your column input it doesn't know that this is your price so replace this with whatever header your column is this is asking where in the model is your our sale price。

We are going click the green cell in this second entry box。 the row input。 we're gonna leave blank。

 We only fill that in when we have a header across the top。 we have a twoway table。

 something that we want to do。 So we'll do that in a second。

 but here's the image we're going do unfortunately I don't know why the screen that I'm using recorder doesn't capture the box but once you do that again I'm gonna to put right inside of cell input I'm going click the green cell for me it's B 37 and then I'm going hit okay and when I do that watch what happens。

 the table gets filled in quite nicely。 I have to format it and let it know that I want it to be some numbers。

 let's get rid of the decimals。 and I have the different profits at all these different prices and if you scan the table you can start to see it goes up and then you can start to see it actually goes down to make this even more visible to make this even more clear let's just show you that the numbers go up and they go down I'll highlight my table and I will insert a scatter plot to show you the numbers go up and then they kind of start to decrease。

 It's not as obvious that they do。 we kept going on the table this would be。More exaggerated。

 show you， let's see if I can do this here if I put in 800。Add these values in the chart。

 I'm just gonna add a couple more values to show you what I'm after。

 So when I do add a few more values here at the high end， I'm just doing this to show you the point。

 It does go up and then it clearly goes down a little bit。

 So I added these numbers just show you there's some sweet spot somewhere around。

 It know 50050550 where revenue is， in fact， maximize in this course。

 I'll show you how to find this number exactly right now。

 we're just kind estimating it to get a pretty close based on these1 and two way tables。

 The last thing I'm gonna do here is sort of actually answer the question remind yourself the question。

 assuming the unit cost of producing a set of clubs is 250 and the price must be a multiple of 10。

 What price should the company charge to maximize There it is to maximize its profit。

 So here we can scan the list and see which value is the largest one more sort of put the bow on top here。

 Let's highlight all the values。 Let's go to the home。T， let's add conditional formatting。

 highlight cell rules and lets do let's have it equal to the maximum value of my entire table。

 red is usually negative， so I'll change it to green and I'll hit okay so you can do conditional formatting with cell values。

 And this would be my maximum。 It's automatically highlighting for me the largest value。

 It's just there to call it out。 So the answer to part a we would sell。

 This is again the manager's choice here。 we would sell at a price of $530 for a profit of $1。042213。

 Now this is all specific。😊，And again， you can imagine some rounding errors here。

 but about a million dollars。 This would maximize our profit。 Again。

 this answer is only as good as the model behind it。

 And we did a little bit of analysis in the beginning to really say why this is the right model to use All right。

 let's look at the second question。 The second question says。

 how does the optimal price depend on the unit cost of producing a set of clubs。

 So remember all of this is based on our unit cost of 250。

 So let's say get an email or a letter from the manufacturing and saying that they' are increasing their cost as a manager you want to be prepared for this。

 So now of a sudden this number in play as well。 And so as the cost changes what is the best price that we should sell the clubs for when two numbers are in play。

 You don't going to do a one- way table anymore。 let's do we're gonna fit this down at the bottom here。

 let's do a twoway table and we're going to play around with both the price values， multiples of 10。

 Why't I grab this large table again let's grab all these values， which。

Maybe I'll just fit it right below it I'll grab all the values here Now remember how twoway table works。

 Let's do price on the left and then we can do our unit cost on the right Our current cost is at $250 Again no I don't know what the increments are going be wasn't given so let's just guessimate and we'll say we'll go up by 50 so 200 50300 and then we'll go up to like 550 again you can expand or change these numbers as you want and any one way or two way table you pick the header values so here's the unit cost so the first prior one was only for $250 in that sort of blank cell right above and to the left of your headers this is your go cell this is what we want to fill in so here we're gonna to fill in the profit this is a number that excel in these but we don't so I like to gray it out we can then merge to make this a little more readable of our headers so we'll merge the unit cost across the top and we will merge down on the left our price。

I then highlight all the numbers do not include the text headers and then I go to data and then what if analysis and data table the same box as before pops up。

 I know it's not showing on the screen you have your row inputs So this is like row across the top where where's this row of inputs going。

 this is your cost So in that cell is asking where in your model is your unit cost So for me it's B36 and then the column input cell。

 this is your price and that for me would be B37。 So you hit both of those you hit enter and all the numbers get filled in automatically this is very nice。

 Now let's format this to be actual dollar signs if you get those hashtags。

 it just means the columns too small， just widen the column and what I'd like to do is sort of do this conditional formatting one at a time notice so maybe leave all these numbers here。

 It's a big table but what I do here if I highlight the entire first。

I can put on conditional formatting and use my highlighting cell rules and make it equal to the max and I'll highlight the exact same row again。

 red is usually bad green is good so I'll change the color to green and just to show you that it's working as well for the twoway table when the cost is 250 my profit is maximized at $530 but now you have even more information if the unit price goes up to $300 let's add conditional formatting to the second column then this would be let's do equals max and let's highlight the rows one more time clothes app parentheses and then we'll fill it with green tech and as a manager now we're done Now unfortunately you can't drag the conditional formatting over so if you wanted to do this conditional formatting you have to do it for each one it's a little annoying if someone knows a shortcut。

 please let me know but this says the price now to be maximize our profit will be less that makes sense because our unit cost is going up。

We would maximize that， but our price that we'd want to sell at is now not $530， but $600。

 And this table you can go through and read it off for different values and you can play with different scenarios as you go through So excellent use here of a one way table and a two- way table Last but not least the question then sort of takes a step back and says is the model an accurate accurate representation of reality again a little bit openend question but'd like to are these numbers reasonable to get would you know different demand at different prices。

 Probably yes， if you had large stores across and you were changing prices up in some more expensive cities you can charge more for things So that data is probably reasonable and then going through this we did linear power and exponential I there a better model that's out there do you know of a better way to do this Could you get a more accurate description a accurate representation of this relationship between price and demand something to think about could you make this better I like what we have so far I think it looks nice。

I think it's working， we could defend this our choices along the way and we certainly have price points for different values of unit costs。

 so a very functional model， if there's anything now I might just clean this up。

 use multiple tabs and make this a little more readable it's getting a little long and sort of unwieldy but other than purely cosmetic and readability it is working nicely and we have solved the problem of the 19th hole All right great job on this example we'll see you next time。


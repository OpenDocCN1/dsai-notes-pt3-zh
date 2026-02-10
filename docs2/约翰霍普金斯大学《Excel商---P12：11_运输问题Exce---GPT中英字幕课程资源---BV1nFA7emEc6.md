# 约翰霍普金斯大学《Excel商业分析｜Business Analytics with Excel： Elementary to Advanced》中英字幕 - P12：11_运输问题Excel模板.zh_en - GPT中英字幕课程资源 - BV1nFA7emEc6

Al right， everyone， welcomee back。 Unlike other examples where I usually have a problem pasted here。

 I walk you through an example of a transportation problem。 Now。

 remember what we're doing here in this course。 So we're doing linear programming or LP problems。

 So LP for short。 And then what we're gonna look at now is a subset or a special type of LP problems called transportation problem。

 Everything is going look and feel the same。 We still have a single objective。

 we have constraints We have multiple decision variables to figure out。

 So it's all going to be part of the LP template， but these are very specific examples that have a very sort of specific and slightly different template that we're going use。

 And once you recognize that you have a transportation problem。

 you can use this template fill in the information。

 And then we're going to use solver to find the best or optimal solution。

 This transportation problem， which is a special type of linear programming problem。

 it tries to find the best which could be money time or distance way to distribute goods from sources。

Factories to multiple destinations， these could be retail centers or even customers。

 You can imagine big companies like Amazon or U or Fedex people that have multiple things that are going to and from。

 they have to transport lots of goods they are very good at these type of problems to minimize their cost to minimize time to become the best and leading experts in the business。

 let's just do a small example to get started and follow along with Excel。 let's get started。

 So we have three factories tos Moines， Evanston and Fort Lauderdale。

 these are all cities in the US Store are in Albany。

 Boston and Cleveland purposely picking these so we have ABC and D and you are in charge of shipping。

 have items in your factories and they have to go to the stores there's a lot of information here。

 So the one thing you're gonna notice about these transportation problems is that they're a lot longer to read there's a lot more given So you really have to organize this well so a couple things we have shipping costs。

 So this can be presented as a chart as a table but if you're shipping things from Des Moines you can ship things to three different places。

 we can go to。Albany to Boston or to Cleveland， and the cost will be $5$4，$3 for each item。

 If you're shipping from your factory in Evanston， my old hometown。

 then you're gonna ship it again to possibly A B or C， Albany， Boston or Cleveland。

 This would be $8$4 and 3。 You can imagine I'm picking nice numbers here just so it all works out。

 But these costs are known beforehand。 And if you are shipping from your last and final factory in Fort Lauderdale to either A B or C。

 well then those costs are $9$7 and $5。 So for now， just watch and pay attention。

 you can imagine in some word problem to follow this will all be given。

 So notice we have 3 sources and we have 3 destinations right now they match。

 they do not have to match in general。 you can have a mismatch between your sources and your factories。

 Now， our goal here are objective。If wasn't clear by now， I want to minimize the cost。

 I want to ship what I need to these places。 I haven't given you the demands yet。

 but I want to minimize my cost。 do that。 I need to tell you what is demanded。 Well， each store。

 each factory， So let's put D E and F here。 These would be what your outputs are。

 Each store can produce， let's say100 items from Des Moines。

300 items from Evansville and 300 from Fort Lauderdale。 Now that's what can be produced。

 What are your demands。 What are the requirements from the managers of these individual stores in Albany Boston and Cleveland and ABC。

 Boston needs 300 items in Cleveland needs 200 items。

 So your job is to find the best way to ship to ship these items from their sources from the factories to the stores。

 But here's all the given information， You can imagine this could be a very lengthy word problem。

 This is all given。 and what do you as the manager。

 what do you as the person in charge you need to figure out how do we minimize。

The total cost and of course here the constraints would be I can't ship more than what is outputted in my factories。

 I also don't want to not meet the demand。 I have to meet the demand of my stores so here's how we build this template out when we have this type of transportation problem again this is just our basic template we will expand on this in future examples but for now if you want to save this is our transportation example So first thing we do is we create what's called a data table this is where we take all the given information no matter which way it comes in and we put it nicely into a table so what you do is which sources on the left as many as you need Des Moines we put Evanston we put Fort Lauderdale and we always list our sources on the left expand the column as needed so that it is readable as always and then we list our stores or our destinations on the top so we have three destinations here if we had more of we just add them accordingly。

And we create a nice little table with all of our costs。Right now。

 these costs are actual dollar costs。 you can imagine this could be miles for distance or even time between the cities as well。

 so we put all the numbers in and we center the numbers to make it nice and now we still have other givens that we have to put in。

 for example， I need to know what is outputted by each factory what source and I also need to know what is the demand So to clarify that since it's not obvious in our table which is what let's merge and center these three cells and we'll remind ourselves that these are our sources so I'll center this if you want to get even fancy we could change the orientation。

 there's our sources and then in the columns that are above merge and center and remind ourselves that these are our destination these are our stores。

Let's find a nice way to put our output and demand numbers on this table。

 We call these a wrapper column。 So right here we're going to put our supply or our output。

 and I want to know how much can Des Moines with an S on it there it is how much can Des Moines produce。

 What is the maximum production So I have 100 for Des Moines300 for Evanston and 300 for Fort Lauderdale that is our output notice these numbers even though they go down the column they correspond to the source going across then I put my demand Now my demand is going be a column。

 but just like their output， they correspond to the destination's demand So how much does Albany demand Well Albany demand again。

 this is given 300 units and Boston demands 300 units leaveland demands 200 units So I create these wrapping columns and rows。

 notice I have taken all the information that's written on the page and put it in a nice little table fantastic Once you have that。

Take the whole thing once it's all beautiful and formatted and copy it right below。

 clear out the numbers in the middle。 and clear out the output numbers。 clear out all the givens。

 We're just really copying the formatting of the table。

 And the inside of the table becomes our decision variables。

 This is going to be the right amount of things to send。 Now， it's no longer a data table。

 it is now going to be our shipment table。 This is going to be the actual answer of what I want。 So。

 for example， in the first cell here， I want to know how many from Des Moines do I ship to Albany。

 How many do I ship。 This is what solver will find us。The output numbers。

 So let's put in some dummy numbers right now。 So again， I don't know what the numbers is。

 I know that Des Moines， I'm just going make a numbers here。 How about 20。

 I'm gonna put 20 across the board 20 and 30 for all of them in Evanston again these are all dummy numbers These are all fake。

 This is clearly not the right answer。 Nothing matches。

 but I'm just putting in dummy number Now I need to keep track of how many are getting sent out from Des Moines read this table make sure you can read this table。

 for example， this says that Des Moines going send 20 units to Albany 20 units to Boston 20 to Cleveland。

 So I have to keep track of how many Des Moines to sending out to do that I'm going to sum the entire row across20 plus 20 plus 20 does give me 60 room over here and I will show the formula here So I am summing I am summing C12 to e12 how much is Des Moines putting out So this is a calculated number and I drag this down Evanston with these dummy numbers is putting in 303030 So 90 totals being shipped。

From Eison and Fort Lauderdale， of course， as well，404040。 Now， the demand。

 how many has Albany received， how many units has Boston received to do this。

 I will sum down the column。 This is also just a formula。 and I sum the entire column。

 If I had more destinations and more sources， this table would just grow accordingly。

 But for now it's the nice3 by three table。 and I sum across。

 So each one of these is formula on my wrapping column。 The green cells， again。

 these are dummy variables， just is just to put in they are just put in to make sure that the spreadsheet is working。

 The one thing I am still missing is my objective as a reminder， we want to minimize the total cost。

 Now， let's think about this for a second。 This is my objective。 So I'm going to color code at gray。

 If I send 20 units from Des Moines to Albany。 How much does it cost me。

 while the cost up here is 5 per unit。 So the total cost of shipping 20 items from Des Moines Albany would be 20 times 5。

 I multiply that as I go。Boston is $4 a unit。 I'm shipping 20。

 so the total there would be 20 times 4。 and then I would add it together with the total cost。

 Each one of these two blocks。 these two tables are multiplied together。

 So we want to do sum product one more time。 So this feels familiar。

 And I highlight the entire table。 Some product does not care is not a single row it can take any shape or size as long as it matches so we'll do the three by three table and then the three by three table again。

 The order on which you input these does not matter either for some product。

 can mix it up close the parentheses and hit enter and I'll show the formula text for this。

 and you can check if you multiply these numbers together。

 if you want put some zeros around us to make the math a little easier。

 but if you multiply these together， you do in fact get the sum product of all these numbers。

 you can see as you change the dummy cells that the spreadsheet is working。

 all the numbers are changing。 and this works out quite nicely。 So this is the model。 This is it。

 We're ready to use solver。 let me just pause for a second and make sure everyone's caught up。

 But in all the given information。😊，And again， this in comeat you in a table。

 this comeat you in a chart， this comeat you with arrows， word problem doesn't matter。

 I create my shipment table， the wrapping cells are now formulas。

 This one output measures across demand measures down， just add those up。

 and then I do a some product formula one more time for my objective。

So let me clear out my decision variables。 I'm also gonna make one change。

 I'm looking at my notes here， and I realize I copied a number wrong。

 Please make this change in your notes are on your spreadsheet。

 instead of 300 as the demand for Boston， please set this to be 200。 Sorry about that。

 Please change it to be 2 now let's get over to solver and actually solve this problem。

 So I go to data。 I go to solver。 I set my objective cell。 This is the gray cell that I color。

 This is the total cost。 I set it to be a minimum。 and I want to change the variable cells。

 which will be all my green ones。 It's okay that they are not in a single row。

 You can highlight whatever you want as long as they are connected here I have an ice3 by three table。

 highlight the entire thing。 Now， subject to what constraints。

 Let's have some constraints4 I had an entire constraint table。 I don't have that anymore。

 but the constraints are there。 They're just in different places。 So what do I want to do。

 I have really two constraints。 I can't send more。 Then the factory can produce。

 I have to be careful my output。 remember each factory has a limit in terms of what it can output。

 So the limit that's calculated are these。Sells in the shipment table。

 Remember those are all added up。 And I want to make sure that that's less than or equal to the givens。

 Hopefully that makes sense。 I can't send any more that is produced。

 and I'm gonna batch upload these by highlighting all three calculated numbers go first。

 less than equal to the givens。 the upper limit。 Let's add another one。

 I also have to make sure that demand is met。 So what is being shipped to Albany。

 Boston and Cleveland， the calculated numbers in my shipment table has to equal。 let's equal demand。

 It could also be greater than or equal。 I guess if you want to send more rather send more less。

 but the key is you can't be under。 if Albany demands 300 than you have to send 300。

 So we'll just use equality to get it。 So let's say equals。 and then we put in the givens。

 So we highlight the threes 300200 again make sure your says 200。 and then hit And that's it。

 This is the very first example。 So just has these two constraints。

 You can imagine this gets a little more complicated as things go on。 But for now。

 don't send any more than the factories can produce。 and make sure that the stores receive what。

Select the box to say make unconstrained variables not negative and select simplex LP for these transportation problems。

 Remember， LP stands for linear programming。We hit solve。 Salr found a solution。 wonderful。

 So we hit okay。 So thank you， Salr。 And we have these numbers here。

 And now just make sure you understand how this works。

 This is saying the best possible way to do this。 again。

 you could try by hand to see if you can break it。 But I promise you you will not be able to。

 The best possible solution is to send 100 units from Des Moines Albany。

 right now that' maximizes Des Moines output。 Evanston can send 300 units。

 so we're going to split that by 200 to Boston 100 to Cleveland。

 And then Fort Lauderdale with its 300 capacity get split between 200 to Albany and 100 to Cleveland。

 this is our answer。 and you would put all this， of course， in a summary sentence。

 So we would ship 100 units from Des Moines to Albany200 units from Evanston to Boston。

100 from Evanston to Cleveland， etc ce。 And you'd write this out。 But that's it again。

 try to see if you can beat it。 The key here is that the minimum total cost Your objective is 300。😊。

$900You have found the best possible way using this model and using solver to get the goods where they need to go without more than each factory can produce。

 again， appreciate the power of this。 And hopefully this for a minute and just realize this is an LP。

 We have a single objective。 We have decision variables。

 How many from each source am I sending to each destination。 And I have my constraints。

 So a slightly different flavor。 And we're going add on this again。

 these are called transportation problems。 And they are a subset of LP problems。 All right。

 great job on this example。 I'll see you next time。😊。


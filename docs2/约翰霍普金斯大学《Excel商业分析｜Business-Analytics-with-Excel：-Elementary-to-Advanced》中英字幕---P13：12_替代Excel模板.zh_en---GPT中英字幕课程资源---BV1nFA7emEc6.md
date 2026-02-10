# 约翰霍普金斯大学《Excel商业分析｜Business Analytics with Excel： Elementary to Advanced》中英字幕 - P13：12_替代Excel模板.zh_en - GPT中英字幕课程资源 - BV1nFA7emEc6

H right， welcome back In the last video。 we did our first example of a transportation problem using the so-called table approach what I'd like to do now is show you a different layout than the one that we have And this layout is a little bit nicer。

 a little more transparent I think for smaller examples it doesn't work as well for large but again for small examples I think this is great and just gives you another way to sort of attack a problem if you get one of these transportation problems to model it inside of Excel。

 So let's just remind ourselves of the data， the inputs from the last question。

 we have three factories that are supplying products。 Des Moines。

 Evanston and Fort Lauderdale we have stores in Albany。

 Boston and Cleveland we're going tobbreviate this is ABC and D as a friendly reminder all the shipping costs are provided So they're here in the image that I screenshot from the last video we have D to AB andC 54 and3 Evanston to AB andC it's 84 and3 and then from Fort Lauderdale to AB and C 97 and5 great those were all given those will always be given our outputs。

Of our factories to produce served items is always limited right you can produce an infinite amount of items so we have 100。

 300 and300 and then our demands what's being demanded by our stores the call says please ship me this stuff immediately A B and C is 300200 and 200 in the prior video I start off with 300 but hopefully you fix that as we went along and so our goal here is to minimize the total cost。

That's our objective。 And of course， our constraints are you can't ship more than what the factories can produce and you can't send less than what's demanded。

 You want to meet demand So let's create an alternative transportation problem this one's just a bit more nicer I think to lay out So we have our origins or factories whatever you want to call them just where things are coming from And here you know you'd listed out。

 And so since。Like in the past， in the last one we had Des Moines and we listed it once and it was nice。

 it gave us a small spreadsheet， but really Des Moines can ship to three places。

 what you do now is you list three times。And then you have Evanston and last time you listed it once。

 but now since you can ship to three places， we listed three times if it could ship to four。

 you listed four if you could ship to5，5 and so on。

 and then of course you have Fort Lauderdale we struggle to say thatre Fort Lauderdale and again since it can ship to three places you listed out so you just give a big list and again this is why this doesn't scale necessarily although Excel has lots and lots of row that you can fill in so you can certainly use this for many many problems then you say okay so I have all these origins and where can they get shipped to we put our destinations our stores wherever they're going customers and you list out each single one so we have Albany we have Boston we have Cleveland That's a longer spreadsheet it's not as concise it's not as pretty but you list out and now you have every possible combination that you have you have three choices for the first three choices for the second multipied together and you get's fantastic what else you want to keep track of again。

The data what's given we have our unit costs so we take our unit cost and these are all given and you type them in so 54。

3843975 and the last thing we want to know call our shipments these will be our variables our decision variables what do we want to send from each origin to each factory and we will color code these green and we' make this a nice pretty table okay everything here is the givenbbs so the next thing we need to do is put in our supply constraints this would be our factories what are we able to supply we have Des Moines we have Evanston and we have fort Lauderdale and you want to think about what they you know able to produce what is being we call this our outflow what is actually produced now this we have to keep track of let's put in some dummy numbers here just because let let's do22233344 these are the wrong answers these are just dummy numbers but let's。

Count how much is actually going out and remember we have our sign and then we have our capacity and you have to stay under what actually is going out has to be less than or equal to the capacity of the plant。

 so I have 100。300 and 300 again so I need to count。

 I need to find a way to keep track of what's being sent out okay we can do that this is a new formula fors if I ask you to take this table and sort of count there's two ways you can do it the long way to do it the not so pretty way is to say well let's add up Des Moines go to Cleveland add up Des Moines going to Boston you can do it this way like sort of select each one or maybe you can get clever and do a sum they happen to be an order but I'd just like to show you another way to do it you can always use this is probably the more I guess advanced way to do it you can use what's called the sum if formula and this says tell me what I'm summing what's my range what is my criterion and then well what should I sum So the range here since we're looking for Des Moines is say go look for the table for Des Moines what is my criteria Well I'd like it to match so search this entire column find Des Moines and then let's range。

 what should I add up add these here then knows to match the road。

when you do that close the parentheses it enter it correctly gives six I notice if I update something say here to three it counts it correctly and this is great I want to drag this formula down this would scale up with my model nice little hack here so let's put dollar signs on it a4 on both a4 and a12 to D4D12 hit enter and we'll drag this down so that's a nice little formula I'll put the formula text on that you can see it it's the easiest way to do it that we just kill a mosquito with a cannon probably but it's a nice way to scale up add now our demand constraints so we're going to make sure and solver that our outflow stays under our capacity and then for our demand constraints。

Let's look at our factories one more time， I guess this will be our stores this time。

 we have our stores。 We have our inflow and here we really want to be equals or even greater than equals let's do greater than or equal and this is given You can always send more I guess but it's gonna be not very cost efficientffic to keeps any more the demand here is 300 again 200 and 200 and our stores will list them off as Albany。

 Boston and Cleveland will copy and paste that from above and now we have our tables let's do the same inflow formula let's use the sum if formula so it says range where am I looking so let's look under our stores what's the criteria what am I checking for let's go actually get the store name and then what am I adding up we'll add up what's being shipped in so now I can actually track of what's going to Albany again I could have clicked the Albany Albany and Albany and you can see4 and3 and2 does add up correctly but I want something I can scale up。

Drag down There's no reason why these have to be sorted the way they are so this is just a more advanced。

 put dollar signs on everything so we can drag it down and enter when you're ready and drag to put some borders on the tables just to make them a little more readable we like pretty spreadsheets we'll center everything for readability and there we have it So this captures all the same information as the other spreadsheet it's just a different way to see it And again because this is a relatively small example we are able to do this template the one thing and the last thing we need is our objective function and running a little bit out of room so let me zoom to make things smaller I'll put it right here at the bottom our objective function as a reminder we are trying to minimize the cost Now this is a little easier to do we color code this gray what you want pause the video here and see if you can come up with a formula that would find the total cost based on this spreadsheet what do you want to do I'm going ship this many things my variables at these costs。

Two things from Des Moines Albany would cost $5 each two things from Des Moines to Boston $4 each well that is just multiplying and summing as we go so of course we're going to use our sum product formula with all the unit costs and then all the corresponding shipments the order on what you highlight doesn't matter and enter when you're ready and you get。

At least with these Wy numbers 156 we're going to get hopefully the same exact answer as we had last time。

 but of course we need solver to find that for us so once your spreadsheet model is correct and you understand it again don't just copy me as I go through it make sure you understand it let's head over to data to solver。

And let's go ahead and fill in all the information let's set our objective function again if it's color coded correctly it's the gray cell helps us find it quickly。

 we want to make sure we're selecting min and we want to change our green variable cells so1。

23 make sure those are all set let's add some constraints here and now you can also see the benefit of this template it matches what we're used to with our constraint table so I have my outflows let's do batch upload here all of my outflows need to be less than or equal to all my constraints and then we'll add another one and then all of my inflows need to be greater than or equal to my demand to put equals here as well you get the same answer and you hit okay。

So we have our two demands， our capacity demand。From supply and then from the stores what they are select the box or make sure selected to make unconstrained variables that negative and select simplex LP。

 solve and found a solution all constraints and optimality conditions are satisfied it okay and we're good and if you remember the 3900 was exactly the same number that we got last time so nothing's changed nothing's changed at all just the layout just the organization of the spreadsheet and from here of course we'd write a summary sentence maybe put some units put some dollar signs on these things and then present it off to the next person on the team All right so just another way to do it pick the one that you like the best pick the one that you understand try both them beginning until you find one that you really like as you work through the other problems in this All right great job on this example I'll see you next time。


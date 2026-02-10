# 约翰霍普金斯大学《Excel商业分析｜Business Analytics with Excel： Elementary to Advanced》中英字幕 - P15：14_MLB裁判分配.zh_en - GPT中英字幕课程资源 - BV1nFA7emEc6

。Allright， everyone， welcome back here I have an assignment problem for you with a little bit of a twist。

 Id really like you to pause the video after we go over what the problem actually is and try this one on your own you'll see like anything even though we create an initial templates there's always something later that needs to be adjusted that needs to be taken care of all right so here we go In this example our job is to assign one umpire crew to each city we have crews that are currently in Seattle Arlington。

 Oakland and Baltimore and they need to go to the next game at Kansas City， Chicago。

 Detroit or Toronto now you can only take one crew and assign them to one city so you should not send two crews to the same city so one Crer city you also want to minimize the total distance travel so you want to do this in the most efficient way possible。

Now baseball is a lot of unions and there's a reunion aquarium in here that you are not allowed to send any crew from Oakland to Toronto that is too far to fly just not allowed is' one of these constraints that you just have to follow so if you want pause the video now and try to find the optimal solution look up your old templates pretend's a little quiz pause a video and do it and see if you match me at the end of the video if you can do this there is a little catch in here I have the distances and miles between these city that is always given and of course the Xmars a spot here between Oakland Toronto that is saying that you cannot fly someone from Oakland to Toronto All right pause a video if you haven't done so and try to work this out。

Ready。What do we do So once we have our cost table now here notice costs and distance and miles we copy the table the whole thing piece it again and we clear out the costs and we turn the cells green these are gonna be the answers this is gonna be our decision variables we're going want all these numbers to be zeros and ones we can put some dummy numbers in here just to see what happens one of course means yes send the Seattle crew to Kansas City and then blanks or zeros mean no we must keep track of how many cities these crews were getting sent to so let's create a total column and sum up the row and we'll drive that formula down suming the row one more time I'll click it for you so you can see what's going on and I want this remember what is bad here I don't want to be zero I would say that the Seattle crew doesn't get assigned anywhere and I certainly don't want something like this to happen where I have a one in two different spots that says send the Seattle crew to both Kansas City and to Toronto that can't happen So whatever this total is the right answer。

The correct answer， then this number would actually be equal we get the equal sign just to show to remind you we're going to use a single apostrophe and then type equal that excel's way of saying this is not a formula you truly do want text and this number one is just number one it is also not a formula the formula that comes in or it column F I will drag down the dollar signs and the ones across the board now I want to do the same thing for my totals for my columns of this table I will sum down the column from B13 to B16 this will keep track how many crews are being sent to Kansas City I'm trying to avoid here is a one and then another one in the column again what do these numbers mean it says sendend the Seattle crew to Kansas City and send the Baltimore crew to Kansas City and now you have two umppir and crews that are showed up at the same stadium and of course that's just gonna mess things up so we don't want so we have our sum across the board and I drag this across I drag this across to keep track of all the sums so there's lots of badness going on。

Here obviously this is just a dummy answers to make sure the spreadsheet's working。

 but it certainly seems like it is and once again I really want this to be I could have it equal to one or I could even do less than or equal to one had a lot of work out just fine which when you want less than or equal or equal to one but this is how we're going to tell solver to meet our construct hopefully you got pretty close to this while you were working this out the last thing to include is your objective。

our objective going to be we want to minimize the total distance again I like to write up in my objective label what I'm actually doing。

 do I want to minimize or maximize and what am I actually minimizing it's not a cost here。

 it's actually a distance in miles of course。And we will color code this cell。 All right。

 how do we do this， This is the same as before， So we'll do equals some product。

 We highlight all of our costs and we highlight all of our variable cells close the parentheses and hit enterll show this formula off on the side using the formula text function and by distance in miles is 7750 based on these dummy numbers So if you play around the dummy numbers hopefully this should update and it does this is where you can try by hand to guess or user your intuition and what the right answer should be As I check things over I realize I copied1。

2，34 let's fix that they should all equal one and column them H。

Once we're happy with our spreadsheet， we head over to solver As usual we set our objective to the gray cell for meson B22。

 we want to minimize the distance traveled in miles and we set our variable cells these are always the green ones so we highlight the entire box of green cells we have a couple constraints here the first one being that only one crew can be sent to one city so we'll batch upload these this is me selecting all of F and that should equal one you can highlight the ones or you can just type it that's okay let's add another constraint I want to make sure that each city only receives one crew highlight all the cities and I can select equal and then once again or I can even do less than equal doesn't matter but you can select the one or type it it's all going to work and hit okay so once again you have your sort of supply and the man make sure the box check to make unconstrained variables on negative select simplex LP solver found a solution Thank you solver we hit okay and now let's take a look at our solution。

It was able to do this for 2590 so this is it this is fantastic right Seattle goes to Chicago。

 Arlington to Kansas City， Oakland would go to Toronto wait a minute as a reminder Oakland's not allowed to go to Toronto so if you found this answer you kind of fell for a little bit of a trap here what's happening in this one yes this is the optimal solution。

 problem is this X in the given Excel is not treating that as a number treating a zero so the cost to send the crew from Oakland to Toronto is zero that's amazing there's no cost to do that So of course it's going to be selected when you trying to minimize the distance so what you have to do here there's a couple ways to do it probably easiest way to do it is treated as a constraint I can't send Oakland to Toronto so why don't we add one more constraint and say hey look this cell right here for me E15 the cell that assigns Oakland to Toronto well this has to equal zero there's no way that cell is allowed to be one I don't care what else you do but that cell must be zero that's one way to do it。

Now when I run Salr I have a new solution Seattle is being sent to Detroit， Arlington to Chicago。

 Oakland to Kansas City that's perfectly fine， not Toronto and then Baltimore gets sent to Toronto so each row has a one in it each column has only one one in it so this is the final assignment and I would write that up for my send sentence The total distance the minimal total distance the best solution meeting this requirement that Oakland cannot go to Toronto is 4580 miles so watch out for the little X there that's the sort of trap if you didn't fall for give yourself a little pat in the shoulder nice job here the final answer for us is 4580 so feel free to go back into solver and make any adjustments is needed you can put as many constraints in here as it will allow Always make sure you meet all constraints All right great job on this example I will see you next time。


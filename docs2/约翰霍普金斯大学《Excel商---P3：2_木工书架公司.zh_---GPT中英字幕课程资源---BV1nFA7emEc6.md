# 约翰霍普金斯大学《Excel商业分析｜Business Analytics with Excel： Elementary to Advanced》中英字幕 - P3：2_木工书架公司.zh_en - GPT中英字幕课程资源 - BV1nFA7emEc6

Hi everyone， welcome back In this video， we're going to model a new company called the Woodworks bookshelf company。

 and we're going to look at some new skills in Excel and we're going to increase sort of the difficulty every problem that we do。

 So before we begin， please pause the video， read the question。

 Under where this company spends money， understand how this company makes money。 but take a second。

 read the problem and imagine how you try to model this in Excel before we actually walk through it together。

 ready let's begin first let's add a header to our spreadsheets。

 So here's the woodworks bookshelf Company。 we like pretty spreadsheets。

 so let's call that one heading one， you can certainly call it whatever you'd like。

 And here we have a company that produces two types of custom design furniture。

 Either from cherrry or from Oak and here we're trying to model possibly different projections or different increases in cost for each one。

 one thing you may not be familiar with here sort of the board feet。

 think of this as how many boards or how many feet of wooden boards that you need how many pieces that you need to construct each bookshelf。

So let's first think about how this company sort of spends money and where the sources of revenue go。

 So let's look at our costs。 again， we have two items here。

 we're going to be looking at our cherry wooden bookshelf and of course our oak wooden bookshelf so we have to separate the cost accordingly you can see from the table that sometimes they are different and we have our unit cost here we have 550 cherrry and we have 430 for oak format these as dollars as accounting we'll leave the pennies on so that we show everything we'll center some stuff in the columns to make it look pretty perhaps we can also merge and center a little later when we know what our spreadsheet looks like're always going for readability so that when we pass this off to either a colleague or the client or to our boss that they can read it they can understand where the formulas come from where the numbers come from we're going take this table and probably put it nicely in perhaps a different format as well So we have our unit cost for cherry and O and then of course we need the required board feed So maybe we put that in here board feed Now here we're building the same。

I bookshelf， it's exactly the same。 so perhaps we can list twice。

 you might get away with listening at once， but each bookshelf。

 whether it's cherry or oak requires 30 board feet。

 and I'm inheriting some of the formatting from before so we'll override that and just list it as 30 and there's our cost total so we have our labor cost that go together we have our materials cost that we can put these two together So let's compute these two So again if I need 30 boards for 30 feet of boards 550 how am I going to do that I'm going to multiply the two together。

 cherrry's going to cost $165 and if I do the same for oakll do 30 times 430 I get 129 perhaps I'll leave this without the pennies just for now although you can certainly show it if you want I tend to turn it off turn away there's our materials cost but of course I can have all these materials in the warehouse but then I need to pay someone to of course come put it together and this is where our labor costs are going to come in we currently have our labor's cost here。

labor required let's put these numbers in so each one requires 16 again it's the same bookshelf just different wood so requires 16 hours and then the cost per labor and the rate of labor is 1850 an hour and that is both for cherry and for oak so we'll keep listing things twice put those two together maybe we'll split this up here a little bit again you got to be careful here I need someone for 16 hours at 1850 an hour my total labor cost two sources of cost here I multiply to 16 times 18。

5 and it's exactly the same so we'll drag over the formula and get these two numbers right so we put these things together and we'll get our total cost as you can imagine here is going to be what plus our labor not surprising the cherry which has a higher unit cost is actually a little bit more for the company in terms of total cost than the oak bookshelf now here's where the modeling comes in。

We have anticipated annual cost increase so what would be our increase now we have 2。

4% expected increase for our cherry this is the materials cost Now we want to start to build the models we could see both numerically and graphically how the cost of bookshelves vary in the next few years with things that I want to put down here are the anticipated annual cost of increase so cost increases you got to be careful here I have for cherry my materials this is going be 2。

4%2。4% increase I have 1。7% for my oak and then don't forget we also have a labor floating around somewhere else where can we put this there's not really good spot forward I'll just throw at the end here 1。

5 as well this will be my labor increase Now whenever we want to build a projection we'd like to make a table from the table we will then make a graph all good graphs come from tables so let's build a table with our current costs and then we'll project forward based。

These cost increases。 When we do this， let's label a table call it year and then we'll have our cherry our oak This is gonna be our materials cost and then our labor and we're gonna to start with a current costs in year 0 so that's gonna be0 and then we'll go 12。

3，4，5 You can imagine we might go more or less it doesn't matter as long as you get the table down then we're good。

 you can expand this as we go。 let's put on some borders to make the table more readable let's hold the top label again。

 don't forget to start a year 0。 These are your current costs so we have our materials cost。

 we have our labor and then maybe we could even look at our total。

 we'll add these all up at the end and get our total costs。

 All right so let's grab the numbers that we already have from year0。

 our costs to build a cherry bookshelf is 165 notice I'm referencing the cells I am not retyping the numbers cost to build an oak bookshelf is our 129 our total current cost for labor is 29。

Doesn't matter where you grab it from。 Perhaps we even merge and center the cells later to clean things up。

 I have to be careful here when I want the total。 remember a bookshelf is either gonna be cherry or oak so I really want to split this up in what is my total cherry cost and then what is my total oak cost So let's have two column going and if I bill the cherry I need to add the materials plus the labor adding up the materials plus the labor and then for the oak as well I'm going do oak materials plus labor and I get 425 let's not show the pennies let's keep things is need as we can let's add more borders center all our numbers and let's see what happensright so just be mindful of these formulas。

 So one more what am I doing here the cherry number is the total materials that I calculated as of today the oak numbers same thing how the un cost times the board feet labor is being calculated from either column grab whatever you want is the total number of hours times the rate and then our cherry would be the labor。

pl materials and Oak does exactly the same Now I'd like to go ahead and use the cost increases from above and let's sort of do one of these together and let's see what you know for Excel here So I want to take the number of materials the cost for materials of cherry 165 and then I want to increase it by 2。

4 this is my expected cost and I want to do this plus see if you can find the formula that will actually do this ready how do we do be careful the mistake is just to multiply by it。

 but you can only tell it's going be wrong if you multiply your cost is going go from $165 to $3。

96 that's clearly wrong when you want to increase something you do1 plus the rate of increase1 plus the rate so we would do one plus 2。

40% you do that again I'm expecting something a little bit more than 165 and in fact I get it at 16896 we can show the pennies we can this kind of passes the sniffNF test that makes a little sense。

as well， let's do the same thing。 I take the number for oak and I'm expecting a 1。7% increase。

 So again， multiply by parentheses1 plus and then 1。7 don't type the 1。

7 of course click it reference it hit enter and you can see it also goes up by a little bit I don't know I guess I'll show the pennies here why not and labor costs I'm expecting them to go up it's given this number is given by 1。

5% so I click my labor times parentheses1 plus 1。5% telling because I didn't put the close parentheses on but it'll do it for me perfect。

 Now I want to add these up and again these formulas are fine I'm adding materials plus labor there's no problem there I'm adding oak plus labor So what I'll do is I'll highlight both of them and I'll drag the formula down and now we have a very nice total So our total columns are forming One of the nice things about Excels once you have formulas going that reference everything you can just drag these down but there's a problem So watch me。

Don't copy this first just watch If I highlight everything。 I say great， I have all my formulas。

 they're increasing。 everything's great。 and I drag it down for five years or beyond something weird happens。

 I'm getting these value errors。 and I'm also'm not even working for year 2。

 It looks like the numbers are exactly the same。 So whenever this happens， don't panic。

 double click on one of them and see what's going wrong。

 Let's go back to cherry for a second and let's look at year 2's value and see what happened。

 And it looks like when I dragged it down， it took B18 it took last year's number， which is good。

 and remember my goal was to grow that by 2。4%。😊，But when I dragged it down。

 it also moved the cell from B14 to B15。 And that's bad。 So I want the B18 to drag with me。

But I don't want cell B14 to drag。 That should stay the same。 Now。

 there's a way to do this inside Excel。 So first off， if you get this error， just undo it。

 remember you can't really break Excel and just undo whatever you need to do。

 So I'll hit the control Z or command Z to undo。 you could also use the arrows up here and sort of undo the mistake。

 So the way in Excel to tell to tell a cell sort of not drag with you is called absolute referencing and you go into the formula and you put a dollar sign and it goes before the row and before the column When you do that you lock the row in place and you lock the column in place。

 you can also turn on and off just the row where the column for this example。

 I'm going to be super conservative and just put dollar signs on everything And what this will do these dollar signs in the formula it doesn't change the value。

 formulaula is still working as the formula should but I lock in the cell that I want so I can drag watch this when I drag it down now。

 I'll just do one to show you again， this looks right， It feels right。

 It's a little more than last year。And when I click it the blue cell moved down。

 but the red cell B14 stayed the same。 That's what those dollar signs do。

 And this is kind of the reason why we don't like to put dollar signs as we type inside the formula bar these dollar signs mean different things This is called absolute referencing this means hold the cell in place I will drag but you will stay and it's a wonderful tool that lets you drag and create tables very quickly so what I'll do is I'll go ahead and put dollar signs on all my formulas here So I'll go back and put a dollar sign before the C and before the 14 I'll do it before the D and before the 14 I'm not going put a dollar sign inside my total because these cells when I add up the cherry and labor for each year I want these to drag I don't want any particular year to hold with me I do want these to drag so now that I have the dollar signs in let's try to drag one more time down to row5 and this looks right each number is increasing each year you can randomly click on one just to check that it's working does some nice color coding for you。

You can see that it's grabbing last year's number dragging down as you wanted to and then grabbing the number from row 14 to increase by that percentage。

 So this table is wonderful。 This is really the skill for this video to learn how to use absolute referencing to learn when to put the dollar signs in now we built a spreadsheet model that enables the company to experiment with the growth rate beautiful thing about this is if I want to change this 2。

5 plug in and of course all the numbers update so you can do whatever you want to play around these and I'll show you in another video how to do perhaps a better job of letting the customer see more values right now though I like to color code whenever we have some cells that I want to play with that are there sort of to be changed I'll color code I'm green if I have formulas that I don't want anyone to touch because I've had to figure out the formula and took me a while to get it I will leave those sort of not color coded and you can also color code the given。

 sometimes people color code the givens as well but remember for me green means go let。

with these numbers and see how the outcome is so a company now can look at their five yearear projection and they can look at their total cost and they can have a sense of how their total costs are going rise for both the cherry or the oak。

 and then usually from here where this would go next is you will come up with the pricing scheme accordingly so the company makes money。

 So we've done the first part we've built a Frenchy model to experiment with growth rates in wooden labor costs so that a manager can see both numerically and graphically。

 we haven't done the graph upa that's coming next how the cost of the bookshes vary in the next few years。

 everything here works great， just make sure that you're at this point。

 last but not least is to create a beautiful graph and we can do that a couple different ways we can highlight the entire chart head over to the insert tab and then you can pick whatever chart you want。

 I like to look at the recommended chart。 sometimes Excel has a better idea than I do and sometimes it doesn't。

 There's nothing wrong with really any of these to kind of show where we're after for no good reason。

 let's pick the first one。And let's start to remind ourselves how to work with Excel graphs usually these graphs get sent to the client instead of the table or perhaps you're sending both so often we want the graphs to have some sort of best practices of what things we want right now there's a lot going on but the first thing hopefully you realize is that the chart says chart title please please please don't be that person who sends over the chart with the chart title not updated so update this to whatever we want let's call it woodworks bookhe company and we can look at cost projections give it a name if we have the actual years we could plug in the years so this is pretty good there's a lot going on here you can see we're starting in 10' going up to 600 you can see the cherry in the oak lines or all different colors if you don't want to show all these lines like you just want to show perhaps the totals let's just show the totals you can click on any particular line and just make it go away just hit delete so maybe I'll get rid of these and just show the totals if I wanted to show just labor costs or just materials cost we can make it。

Totally separate graph and have two graphs but it just looks a little busy for my preference again this gets into a little bit of sort of personal preference Excel lets you change everything you want if you want to change the colors of the line you certainly can this is looking pretty good the only thing that I would add here as sort of as best practices is the axes titles again where's that this under chart design and by the way to keep things clean this is a very common question I get for my students when I click off the chart notice the chart design tab has gone away whenever you want to manipulate something make sure you have the item selected some new tabs may appear usually for design elements add chart element。

 add an access title let's add a horizontal one or the X axis and then let's add a vertical one for the y axis it defaults to access title which is probably the worst title you can think of and then just update accordingly if we had units you'd update this and then here I guess we'll have dollars really this is total cost and it's clear that it's in dollars but just because add it in now I have a title。

I have my axes they're labeled and now I can show the client the sort of projections and again this is just the first step after this comes pricing and then we look at profit and put it all together。

 but this is just a good start and a good practice spreadsheet for you to work on referencing or those dollar signs inside the formula that tell the cells to lock in place as you drag the ability to make a good graph comes from a good table and a good table comes from having these dollar signs or referencing absolute references inside All right so great job on this example I'll see you next time。

😊。
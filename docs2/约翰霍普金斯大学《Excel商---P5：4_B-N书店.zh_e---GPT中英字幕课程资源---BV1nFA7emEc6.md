# 约翰霍普金斯大学《Excel商业分析｜Business Analytics with Excel： Elementary to Advanced》中英字幕 - P5：4_B N书店.zh_en - GPT中英字幕课程资源 - BV1nFA7emEc6

Alright， Hi everyone welcome back。 Today， we're gonna look at another example for the BN bookstore。

 So please give the question to read positive video。

 read the question if you haven't done so already。 And when you're ready， let's begin。 All as always。

 let's create a header file across the top you can apply some cell style formatting to it。

 once we have our header cell made。 We're gonna read the question take off the given information and put it into our Excel spreadsheet or Excel spreadsheet model here we go。

 Bnn bookstore with many locations across the US places orders for all the latest books and then distributes them to its individual bookstores Bn needs a model to help it order the appropriate number of any title。

 So right away， we're looking for the number of books to order。 For example。

 BnN plans to order a popular new hardback model， which it will sell for $30 can purchase any number of this book from the publisher but due to quantity discounts the cost for all books to order depends on numbers orderediv it's less than100 the cost of 24 So these couple sentences here is telling you buy in bulk you get a discount。

 maybe you've seen this before。 So let's take the $30。

And this is going to be a regular price of the book。 and this is our $30。 So we'll put that on model。

 and then we have this order。 we need to know how many to order some way somehow we have an order play around this number this number is a little bit of the unknown color that green then we have this table for cost for ordering put that over here on the right if the number order is less than100。

 the unit cost is24 keep track of how many are ordered and then the cost the unit cost pay attention here this is important even though it says less than10。

 the cost is 24 if I buy 100， the cost is not $24 I have to buy less than1000 So what you do is you start the table off at zero that's gonna be your $24 when you get to 100 got to read this very careful after each10 the unit cost drops23 for at least100 copies you order 1001 copies is $23 and if you order $2000 copies the cost drops again to 2225 and if you order 300 is 275 and last but not least the lowest。

unit costs $21。30。 at least $4000。 this is important。

 I'm going to put it up here just to clarify this。 It's at least this many ordered。

 notice the table has to start at zero to get the unit cost of 24。

 a mistake people we hear is that they start the table at 1000。

 but remember you can order less than 1000 and that cost would be $24。 this table here。

 the reason why this question is a little bit wordier。

 The other ones is because we have this table would be nice if they hand us a table like this。

 but of course they don't。 Our job to create the table form at the table。 So everything looks nice。

 keep it off here on the side。 and we're ready to move on。

 B ann is very uncertain about the demand for this book。

 and it estimates that the demand can be anywhere from $500$450。 So I need a sell here for demand。

 and this is also sort of an unknown variable but they give us a range。

 So they're saying $500 to $4500。When we have these numbers， we could throw in some dummy numbers。

 I'd like to put in numbers just to make sure the spreadsheet is working as I build off of this number。

 So I'll make up a number here。 I'll put in 3000 for the order， say I order more。

 let's say 3500 and this just helps me put numbers in。

 I call these dummy numbers just to make sure the spreadsheet is still working also as with most hardback novels this one will eventually come out as a paperback and therefore if it has any hardbacks left from the paperback comes out。

 it will put it on sale for $10。 I have my regular price and I have my sale price， which is $10。

 Now I think I've gone through。 and used all the givens at which price all the leftovers will be sold So anything leftover will be sold。

 So now I need to know how many are coming in as leftovers what is my surplus。

 Now this should feel familiar where we had a difference between order and demand。

 So in this particular case， just think about this for one second， I order $3500 My demand is 3000。

 So how many do I have leftover。 say well the answer is gonna be to subtract。

 And let's watch why this。Could work or it's gonna to cause some problems。 This is fine。

 It's perfectly fine。 you're right。 If you order 3500 and the demand is 3000。

 There are 500 What if I ordered 3000， but my demand was 35，0，0。 Now。

 I should have no surplus left over， but this formula just having the difference here is telling me that I have negative 500 left over for the surplus。

 that's a problem。 You don't want a negative number left over for your surplus。 Yes。

 we're short 500 books。 So that doesn't mean I have negative 500 books in the warehouse。

 somehow some way I need to not have a negative。 Now there's a couple ways to do this。

 we saw this before that one way to do this was to use the max statement。

 and we can use the max of the two numbers of the difference or 0。 this is being a little clever。

 This as if the number is negative， take replace it with 0。 And when you do that。

 you can see it works Now， if I order 3000 and I have a demand for 3500。 Yes。

500 clients are not getting their books， but I have no surplus left over。

 and this is working on the other side if I switch the numbers back。

So I have I order more than demand。 Now there is 500。

 So this is we saw this before with Max and another example。 Let me show you another way to do this。

 So like way number two with surplus and we'll just pick one of them to move forward。

 but let's pick let's use a new function。 this could be a new function for you if you haven't seen this before if function nice function that will test for something to see if it's happening and then you tell it what to do but true or you tell it what to do if it's false。

 So for here I want to test is my demand bigger then my order。 And if that's true。

 I'm going to put0 and if it's not true， then I can take the difference。Expand out the columns。

 we can actually see the formulas。 So this should be working for both of them。

 So read this one more time。 think about what this is doing。

 It's checking first if the answer is gonna be negative。 This says if B9 is greater than B10。

 So if the demand is bigger than the order then put 0 put0 So let's see that in action。

 So let's say order is 3500 but my demand is 4000 checking is this bigger I my bigger If so the news the surplus to be0。

 So this is the if statement does the exact same thing as the max statement Pick the one that you are most comfortable with however you do it though we need to keep track of the surplus because that's I'm going multiply by。

 that's what I'm going to sell for the assumptions in the story here I sell all those at the sale price。

 So now the question is how many copies of this hard back novel should be in an order from the publisher we're trying to maximize profit here。

 So let's go through and look at our costs， we are going look at our revenue。

 then of course we're gonna look at our profit。 I almost work backwards here if I do this。

 my profit is always my revenue minus。My cost will play around with these two things。

 but really let's think about how does this business spend money So the only way this business spends money is I have to order the books。

 I have to order the books。 I be careful。 there's two numbers here demand and order the number that costs me money is the order So whatever I order that's what it costs Now here I have 33500 that means that I've ordered at least 3000 so that should cost me 2175 you have to be careful like I have to use the table somehow you really want to automate this。

 you don't want to have to put the number in by hand but understand that I would like Excel to come back with 2175 This is another powerful tool in Excel is a very strong formula This is a fantastic formula to add your catalog if you don't have it already it's called vlookup Vlookup or vertical lookup looks up values in a table for you so we can pass this 3500 to the table and it will return the unit cost so it tells you what it looking for and in the order that it's looking for so here's how it works It says tell me what I'm looking up。

Where am I looking it up， What column of the table should I return。

 You want the first column or second column here， We want the cost， I want the second column。

 And then it's gonna to say true or false。 do you want to be an exact match。

 Like am I looking for exactly 3500 or false do I want just the range。

 So let's try this one more time ready， So look a value。 What am I looking up。

 We're looking up the order Where am I looking it up in my little table over here with a cost and price What column am I returning。

 you want the numbers from the first column or the second column。

 I want the second column And then true or false， do I want an approximate match or an exact match here because 3500 is not on the table I want an approximate match。

 So I want true， you could type true or just click the button Close appheses going hit enter and look at that。

 pull back for us as expected 2175 This function is amazing， And if you have tables。

 it does a really nice job of looking of values on tables。 And it works， if you change this number。

 let's say I did3000。I'll say it to 4500， you can tell it's working because it's pulling up 2130 now。

 let's format this a little better。And so we have our Vlookup function This is only cost associated to us。

 I just have to order these books and multiply this by the number of books ordered。

 be careful this is just the price。 I have to take this number and multiply it by the number of books that are ordered there's my total cost built into this is a nice Vlookup function So watch out for that piece at the end here is the price times the number of books ordered Great now how do I make money be careful here I have to be careful I have to sell what I have so I don't want to just take the order。

 I can't say well it's the order time the regular price or something like that because here I've ordered 4500 books but I've only sold the demand is only 4000 on the other side if I were to switch these numbers and play around with this and we saw this in another video but you think about this for a little bit if I order 3500 and the demand is 4000 I'm only going be able to sell what I have in stock I can't sell these missing 500 books I have no surplus here So the revenue is gonna come from remember this the min of the demand。

And the order that's going to be what I am able to sell the smaller of the two。

 And then what am I selling those two for。That's the regular price。 This is my fix。

 And they may want to play around with this before you do anything else。

 and just make sure it's working in all scenarios here。 If my demand is bigger。

 I have no surplus being able to sell 3500。 that's going to be at a price of 2175 and the revenue here is going to be the minimum of these two。

 which is working the order times the regular price。 Now if in the case the numbers are swapped。

 and let's say I ordered more and what's actually demanded。 So let's put 3000 and 4000 in。

 I have 1000 leftover。 I'm using the smaller number。

 And then we said we're going add on to the surplus。

You're gonna to be able to sell these at the sale price。 So there's two pieces in here。 And again。

 maybe I want to break this off。 and the form is getting a little complicated。

 but there's two pieces here。 I have my revenue from my regular sales and then revenue from the reduced the sale price we hit enter you get both profit of course。

 is your revenue minus your cost format that also And in this way we're making a profit of $14800。

 at this point， I think my spreadsheet looks great。

 it' working And now just being a little bit cosmetic and cleaning it up。

 maybe we'll merge and center the header sell show all the formulas and we' bold the profit So stare at this I think this is done。

 make sure it's working and run through some different scenarios Now let's actually go back and answer the question How many copies of the hardback novel should be in an order from the publisher So the question is what is the right order amount that maximizes the profit to do that we don't there' two variables in play。

 The demand and the order。 I'd like to do now is make a table to show all possible。

And we know that it's the demand is from 500 to 4500。

 so let's put some of these numbers down5001000 and then we'll highlight the two and drag it down a 4500 and because I know what the demand is gonna be this is probably what I'm gonna order as well so we can paste this number transposed and if you saw how I did that we can highlight come over here right click or do special transpose this will take a row to a column and a column to a row so just a little bit of a shortcut to make a table I'll put some borders on this table and I will give these tables a header so you know what I'm working with。

 let's merge and center this I can have my demand again I'm told this between 500 and 4500 and then on the side merge this as well this would be my order order amount。

And we can play around with the spacing here and we can turn the text vertically。

 you can have some fun typing sideways。 ideally， I'd want to fill in the entire table。

 Now one way to do it， of course， is to do it by hand and you can say。

 okay if the demand is 500 and the order is 500 then my profit is 3000 and I would put 3000 right there you imagine though to fill in this entire table is going to be pretty rough。

 I don't want to do it by hand， there is a nice way to let Excel do it first let's format the table So when we do it looks all pretty and to do this this is called the two way table we've already seen a one- way table where I fill in a column and now let's see a two- way table while I fill the entire table like the one- way table I need to tell Excel what to fill in the middle of my table and so this is gonna be what I call the ghost cell and this is gonna be the profit I want this cell to populate the entire table and this cell is not really for us It's4 Excel。

 Excel needs it to work and so I often gray it out。To recognize that I don't need this。

 but it's part of the requirement to use the two way table。 Alright。

 so this is going to tell Excel where in our model the cells are going to come from。 Alright。

 so let's do a two way table。 highlightlight the entire table。

Head over to the data tab and then what if analysis and then data table Now。

 I realized that the data table of the little dialog box didn't show in the last recording。

 So I'm just gonna to paste a little image of it over here on the side。

 this is what you should be looking at asking you for two things。

 It's asking for your row input cell Now this is an image。

 This isn't actually the box So does bear with me here， It's asking you for the row input cell。

 What this means is of your table of the header that's a row。 So rows going across。

 which is really for us that a man。 Now obviously it doesn't notice that a man。

 but of the table of the top of your table。 where is that cell。

 Where am I plugging in the 500 Where am I plugging in the 1000。

 where am I plugging the 1500 And on your box here， what you want to click is at least for me B9。

 Now again， this is an image because I know iss not showing when I record for some reason。

 but you want to click B 9 into here， and then the column input cell is okay Now your table has a column with inputs。

 Where is that in your spreadsheet model。Martic Excel can't read。

 it can't find can't match these things。 So it's asking you of your columns。 which Ru is the order。

 Where is that in your spreadsheet model。 If you color code the numbers that you're playing with。

 then it's easy to find these things。 So it's the green one So in this particular box in a column input cell you're gonna type B10 or click B10 So one more time on your data table put in here B9 probably with the dollar signs and B10 again click these do not type it don't draw like I do I'm just trying to show you for the box So I'll do it now you won't be able to see this unfortunately because the little dialog box doesn't show data。

 what if analysis data table row input is my demand， So I'll click that again。

 you can't see this column input is the order I hit okay and it fills up the entire table notice the value that I was expecting at 3000 is right there。

 if you get these little hashtags of course it just means the column is too small so just expand the column so you can see the numbers don't panic there。

 you have all the answers you want so you can control as。

Manar of the situation you can control what you order so if you think the demand is 2000 then you can find the profit that maximizes and here for us if we think the demand is 2000 then clearly the best is 2000 and we can find all these pieces Sometimes if you want a color code just to make things pretty this is again just cosmetic we can do some conditional formatting we can throw some color scales on here and you can see where the most money is to be had of course as demand goes up then my profit will go up as well and you can see at each individual column what the demand would be now we can control unfortunately not the demand of the clients only the order。

 so really as a manager we'd be looking across saying okay if I order 2500 books know what demand of my shooting for here I would like to try to sell all my books and have the demand equal to my order but if it doesn't I can at least budget accordingly and see where I lose money where I make money where I break even in this particular example I'm not going to answer where a fixed number so I'm gonna to hand back a table and say。

What you know budget wise are we comfortable with ordering and I think this tables good enough for our purposes to answer this question to have an Excel model to work with two way tables to use our if functions to use Vlookup those are the three new things in this example do you understand how they work if Vlookup and then two way data table and then conditional formatting for aesthetic so that it looks beautiful all right great job on this example we'll see you next time。


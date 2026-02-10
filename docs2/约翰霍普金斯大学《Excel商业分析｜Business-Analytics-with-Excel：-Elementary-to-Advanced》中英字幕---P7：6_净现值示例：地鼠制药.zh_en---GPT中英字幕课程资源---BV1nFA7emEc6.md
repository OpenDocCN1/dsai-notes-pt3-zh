# 约翰霍普金斯大学《Excel商业分析｜Business Analytics with Excel： Elementary to Advanced》中英字幕 - P7：6_净现值示例：地鼠制药.zh_en - GPT中英字幕课程资源 - BV1nFA7emEc6

Hi， everyone to welcome back In this example， we're going to learn how to use Excel's NPV net present value function。

 and we're going to decide if a product is worth pursuing based on an NPV calculation。

 Please read the problem if you have not done so already pauseuse the video So if we can set up the initial given values and then let's start to model the problem ready Let's begin a large drug company go for drugs is deciding on whether one of its new drugs。

 E S is worth pursuing Es it was in the final stages of development and will be ready to enter the market one year from now。

 The final cost of development to be incurred at the beginning of year1 is 9。3 million。

 This sounds like an important given piece of information。

 So let's put that down somewhere let's start to write down the givens。

 let's call this development cost should also probably give our spreadsheet to header。

 we can title and make all pretty in a little bit。 So let's move things down and spread out some columns And what I'll do here is I'll just put down 9。

3 but I'll remind myself that my units are in millions so I do not have。

r down all the zeros and we'll see if we can work with this going forward。

 All right let's keep reading the givens here。 The company estimates that the demand for equals will gradually grow and then decline over its useful lifetime of 20 years。

 so that sounds like another piece of information we want lifetime 20 years our units in the next column and this kind of makes sense things become popular and they start out growing and growing and then they slow down decline over time these numbers in this assumption seems reasonable specifically the company expects this gross margins which is revenue minus cost to be 1。

2 million in year one。 So let's call this year one margin。

 call it course something similar what you call it doesn't matter it's more important that it actually gets labeled so here's a million again maybe I want to move the cost things together but we'll figure that out move things around a little bit。

 then I want to increase at an annual rate of 10% through year 8 so this is two numbers are coming at me here 10% so increase through year so this is like。

Going to increase for your aid by how much 10% fantastic and we'll label this the rate of increase。

 Finally， it will decrease at an annual rate of 5% through year 20。

 so itll decrease our rate of decrease will be 5% go for drugs wants to develop a spreadsheet to model the 20 year cash flows assuming the cash flows other than the initial development cost are incurred at the end of their respective years using an annual discount rate of 12% that sounds important。

 put that down as well and we don't want 12 we want 12% for purposes of calculating NPV。

 the drug company wants to answer the following questions is the drug worth pursuing or should go for drugs abandoned it now and notincur the 9。

3 million development costs。 So here's the question if you're the manager。

 the situation you have a decision to make。 It's going to cost you $9。

3 million now to sort of develop this drug and it will bring in money it's an 1。

2 in the first year it's going increase by 10%。years it will decrease over its lifetime over 20 years Will I get the money back。

 Is this something that I should as a manager decide yes on So what we're gonna do is build out a table。

 we want to build out a table of cash flows and so I can show everything on the screen now that we've sort of read the question let me slide that over for a second and let's look at cash flows and we want year 20 so let's just do end of year and we'll go from one to20。

 remember I don't really want to type  one to3 let's highlight one and2 let's put the mouse on the bottom right quarter and then let's drag it down to show 20 and I'm not going to sit there and type let me shrink the size so that I can show all these numbers and this looks pretty good so there is my end of year first table and what I'm after is my gross margin。

 remember this is all dollars and in particular this is millions of dollars so I want to be very careful here that I remind myself this is in millions of dollars so I'll put it dollar capital M to say。

These are my gross margin。 It's a table， so let's try to make it readable。

 Let's merge and center perhaps the header。 let's put some borders on this thing。

 all cosmetic pieces。 they don't affect the functionality。

 but they certainly don't hurt and let's figure out what's going on here so in my year one this was given so let's link over to 1。

2 million and there it is maybe we'll center some things as we go looks a little nicer we can turn on the formatting for this as well let's see so let's use currency and we'll show one decimal just because All right so here's my question I have to figure out year two's cash flow Now I was told it's going to increase for eight years at 10% So there's two ways to do this we could break this up in the two pieces or do it all at once you want to pause the video here and see if you can figure out the formula to increase 1。

2 million by 10% pause the video see if you can figure it out ready。First of all， it's a formula。

 So equals。 I'm going to take the 1。2。 you want to do this in one shot。

 you can multiply by parentheses 1 plus the rate of increase。1 plus p7。 that will give us 1。32。

 This is perfectly fine。 I've seen some folks do this also this way where they take the number。

 And then they add 1。2 times 10%。 So they find 10% of the number as a friendly reminder of means multiply。

 then they add it together， and you get 1。2。 However you do it。

 it does not matter as long as you get the right answer。 This is a formula。

 so I'll show the formula text there it is。 Okay， now there's something going on here。

 and hopefully you're sort of yelling at me on the screen here。 If I drag this down。

 watch what happens， something gets weird。 I guess I really only want to go to year 8。

 But if I'm supposed to grow by 10% every year， I probably shouldn't get 1。551。55 every single time。

 So the dragging something went wrong。 maybe you see it， maybe you don't to see what's going on。

When I drag these cells， remember， they're all referenced。

 So my cell of 10% is going to drag down with。For example， when I click the Excel cell。

 it's now B8 instead of B7 and I'm actually using the wrong rate。

 I'm using the 5% rate of decrease to try to increase。 so let's not do that。

 Let's not have the wrong formula When I drag， let's fix this。 How do I fix this。

 how do I tell Excel to not drag as I drag we need to put the dollar signs or the absolute referencing on B7 When I do that when I do that now I can drag down to 8 and you see this nice manageable。

 reasonable 10% growth across the board So fantastic。

 I just have to be careful to drag it all the way down to 8。

 I don't want to go past that It tells me it increases through year 8 and then after that for years 9 through 20。

 I'm going to decrease。 I'm going to decrease So now I need to start to decrease this thing。

 pauseuse the video。 See if you can find the formula and be careful of the referencing to decrease my numbers by the given rate of 5% ready Here it goes。

 it's the number before minus。5% of the prior number mimicking the style of the format that we just did。

 you can certainly do this all at once and write this as F11 times parentheses 1 minus B8 that is exactly the same。

 whichever one you prefer works for me。Once you have the formula。

 don't forget to put the dollar signs on and then you can drag it down and you can see the numbers start to go up and then they start to fall。

 We have a nice model of the cash flow following the given rates of 10% and 5% increasing through year 8 and do after So this is great。

 we'll use formula text for the rest of the columns we'll expand this make this readable we have our nice table that models the cache flows There's one thing in here that I don't particularly love all the numbers in our given table of information we've sort of use。

 we have our development costs we'll get that in a second when we compute our NPV。

 but there's something about this table that I think we can do a little better。

 we actually never referenced this cell for me it's B6 the year which the increasing changes like if this changes to9 or 10 Nothing happens in our table。

 absolutely nothing happened in our table， and this is sort of a missed opportunity we always want our spreadses to be malleable to be able to be updated easily to play with different scenarios so。

Never reference this self What I'd like to do is do a little better。

 Year one is going to stay the same。 There's no change there again， if that changes。

 the table will update right if I type 1。3 million see the table update and all the numbers change so let me put back 1。

2 I'd like to know if the year changes how do I do this Well。

 let's think about a better way to do this Let's take our formula。

And check if the year is less than year 8。 So if I'm less than this given year 8。

 then I will decrease。 So this is going to be a cell that I need to also lock in。 So let's do it now。

 So if it's less than year 8， then I want to increase。 So I'll use my formula for increase。

 And if I'm greater than year 8。 let's actually decrease。 We'll use the formula for decrease。

 I'll just type it out again。 I take last year's number。

 And then I subtract last year's number times the rate of decrease。

 I have to be very careful to put the dollar signs in all over this。

 So this is a very good exercise in absolute referencing using those dollar signs。😊。

Hit enter when you're done。 Now the formula got a little more complicated to use the if formula。

 Pause this and make sure you understand how if works。 This is a fantastic use of if。

 I can now drag this formula down。 and it's smart enough。

 notice the numbers on the table didn't change。 So I have the right numbers the whole time。

 I'm just making the spreadsheet smarter， more usable。 And now watch this。

 If I go over to the givens。 And I change year 8 to year 9， be very careful。

 keep an eye out over here at year 9 change occurs。 and I start to increase at year 8。

 And then at year 9， I start to decrease。 You can play around with this and really see it's working。

 Let's pick a much larger number。 How about 15。 So now I have an increase all the way up to 15。

 and then I start to decrease。 So this is where it becomes much more usable as a model。

 I always try to give your spreadsheet。 the most functionality。

 right now I actually haven't answered the question。 The question is， is the drug worth pursuing。

 So NPV or net present value is a function Excel that will give you the price today of a stream。😊。

cash flows。 It's like how much should I pay today for money in the future。

 This is a wonderful metric that managers use to decide if a future project will bring positive value to the firm。

 Your NPV is positive means this is the value of the project positive usually means good。

 we should go for it negative means it will lose money。 So we're kind of looking for a positive NP。

 And if you have two projects or3 to compare then the project with a higher NPV will be the one that you're interested in。

 Now I say this though I like Excel。 not true I love Excel。

 but this particular function bothers me when you write NPV when you talk about net present value。

 I have to explain this in every class。 net present value always means that it's net of something net here means like something has been subtracted off I've taken the present value and I've subtract to something off when you have your net salary we compared it versus our gross salary。

 taxes have been taken off This particular function in Excel is sort of inherited in this way it's really not an NPV。

Not a net present value， It's just a present value， but for historical reasons。

 for compatibility reasons， they've not changed the title。

 So be careful when you use the NPV kind of cover up the end with your thumb and just realize this is just a present value calculation。

 It is not going to subtract off anything。 You have to do that manually So that's the last piece for us to do it's a little annoying that they still call it NPV I've yelled to everyone I can。

 but the folks who make Excel， don't listen to me So here we go All right so let's do it So I'm gonna to put this as sort of a net I'll put in parentheses because it's still part of the formula you should know it。

 but just realize it's just a present value and this will be our new formula if you haven't used this one already's slide things over a little bit。

Okay so this is the NPV formula。 So let's start typing equals NPV and open app parentheses and realize what's asking and in what order。

 First， it needs the discount rate。 What rate am I going to discount the dollars back at that was given to be 12% So we just click it there then it's asking what are your cash flows and you can highlight the entire table highlight all 20 values and hit enter it is assumed there are other options to do if you don't have money that occurs at the end of the year。

 you have to update some options on NPV， but here we're told that the values occur at the end of the year So there are other options if you want to explore this function a little further this is kind of keeping it simple but this is the present value which unfortunately Excel calls NPV So let's show the formula here fantastic So again this is sort of like revenue but in today's dollar this is money made so then if you want to find your total net present value。

 your actual net present value we have to subtract something off What are we subtracting on。

Well the development cost So we'll just copy that again。

 We'll grab that number from above from our given table。 That's the 9。3。 again。

 please keep in mind here everything here is in millions well keep the formatting consistent。

 let's change it all to currency Why not I just like a little better So there's the actual present value using a 12 discount rate using our NPV function unfortunately called NPV and then we use our development cost and now we actually find the true net present value Again。

 it will not do this for us we have to subtract so we just take our money made 11。

85 minus our cost minus our expenses and we get a very nice positive present value of 2。

55 from the reminder million way to interpret this number is as a manager if we green light this project we say go for it we will add 2。

55 million value to the firm in today's money So this answers the question is the drug worth pursuing or should we abandon it now positive。

So if the option is to go make 2。55 billion I think that's a good， it's a big guess。

 positive NPV is a good thing。 And then of course how do changes in the model change the answer to the prior question。

 we added some nice functionality to it， I'll let you guys play around with it if the lifetime is shorter if we increase through the years what would the conditions be that make the net present value negative and again once this thing turns negative we would say no let's not incur this cost So have some thumb of the model see if you can even expand it。

 enhance it give it even more functionality as you improve on your Excel skills。

 All right watch out that NPV function Great job in this example I'll see you next time。


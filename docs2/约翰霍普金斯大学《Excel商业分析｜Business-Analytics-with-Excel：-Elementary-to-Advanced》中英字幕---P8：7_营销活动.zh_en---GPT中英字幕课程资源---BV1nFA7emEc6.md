# 约翰霍普金斯大学《Excel商业分析｜Business Analytics with Excel： Elementary to Advanced》中英字幕 - P8：7_营销活动.zh_en - GPT中英字幕课程资源 - BV1nFA7emEc6

Hi， everyone， welcomelcom back。 Today， we're going to learn how to use LP modeling inside Microsoft Excel to decide the right allocation of ads to maximize the number of people that will be reached。

 If you haven't done so already， please pause in the video and read the problem。

 Try to get it set up。 Remember whenever we go through the problem。

 we always want to think about to ourselves What is our objective， Are we trying to maximize。

 or are we trying to minimize something， what are the variables， What are the decision variables。

 the things as managers that we're trying to get the answer to， and then of course。

 what are our constraints。All right， ready。 Let's begin。

 I'll read it along and maybe even highlight as we go through what are the important parts here。

 So a candidate for Mayor has allocated $40000 for last minute advertising。 Obviously。

 this number is pretty important。 That sounds like a constraint。

 that's going to be our budget constraint。 Obviously， whether with any project。

 you don't want to go over budget。😊，For last minute advertising in the days preceding the election。

 two types of ads will be used radio and television。

 So imagine you're a consultant you're the campaign manager for this particular one。

 you want to know how many types of ads to purchase and that's gonna be the right answer like what is the best possible combination of ads to buy here radio or television so for our variables。

 our decision variables we can start to creating this and typing this away here let's think about what we want to do。

 we need the number of radio ads we'll be very clear about what we call this it's okay if they're long names。

 but I'd rather be clear than not And also the number of TV ads a couple things here it wouldn't be I mean I get what you mean but if some people just put radio ads and TV ads remember Excel doesn't read Excel doesn't do I don't know English or other languages it needs a number So I need the number of radio ads the number of TV ads。

 the more explanation， the more words the clarity more clarity you can provide in your spreadsheet the better we can always make it look prettier later or rewrite things。

 but at least。I've seen a lot of people just say radio ads。

 but they don't recognize that I need to fill in a number。

 so I'm going to color these decision variable cells green。

As is custom and remember I like to put in some dummy numbers here just so I can make sure the spreadsheet is working。

 so let's pretend the answer is you know4 and5。 I don't know。

 maybe it's not maybe it is lucky you doubt it but we'll see so let's keep going each radio ad costs 200 and reaches an estimated 3000 people Allright so costs is gonna go associated to my budget and that's gonna be a constraint。

 so maybe I'll start building that here。 So we build a little constraint table down below and we're always interested in our objective。

 this will go here。 we want to maximize， hopefully you read this and you saw this。

 but we want to maximize the number of people reached so I like to put in parentheses what I'm after here just as a max I have my variables。

 I have my objective。 I have my constraints。So let's start putting in the constraints。

 Always label your constraints。 I don't want to refer like oh the first constraint that doesn't make sense。

 Here I have a budget So the way we're gonna to set this up in our table is we're gonna think about a table that goes three cells three columns pass the variables So here I have two So I'm going go all the way out to5 So my table is gonna be let's see I don't know how long is gonna be say how many rows is going be but it's certainly going be two for the variables and then three past and we always label the cells with the left hand side the sign and the right hand side So I'll abbreviate LHS for left hand side and RHS for right hand side and the sign is going be here So what do I mean by this How does this work。

Think about if the answer is for if you purchase four radio ads。

 right this is why we have dummy numbers。 we can actually talk about it。 It's going to cost you $200。

 So my budget costs my budget costs well obviously I'm gonna to have my radio ads and my TV ads。

 It's gonna be $200 times the four radio ads that I purchase。 this is just an example here。

 I don't know if this is four is the right number of five is the right number but I have four here then know what else I need to purchase。

 Well， I'm gonna to buy5 TV ads。 Well， how much of those costs。 Well， they cost $500。

 So it's $500 times5 TV ads that I bought and then you calculate whatever that is and you have to asksh yourself is that less than or equal to the actual budget did you go over budget。

 always make sure that you didn't and you want to just sort of check。

 is that okay if this is becoming a little bit of a math equation， even in inequality。

 but we want to multiply the cost 200 by the number of radio ads purchased。

 Hopefully that makes sense if I buy four radio ads at $20 bucks I multiply them together。

 So what you do is again， only put in numbers Excel。LikeumbLet's put $200 for the cost。

 the coefficient on the number of video ads and then $500 for the number of TV ads。

 The left hand side， this is a calculation。 This is a number that's computer。

 This is actually a formula okay。This is a formula and what's it gonna be Now I could sit here and click 200 times4 plus 500 times 5。

 but in Excel， there's a faster way to do that。 let's use the sum product formula。

 The sum product says I will sum and multiply these as you go you can highlight the two arrays and5 go together and then 200 and 500 go together here and you hit enter you can check that 200 times4 plus 500 times5 is 3300。

 let me remove this and I'll actually put the formula text in here for the lefthand side just to show you this is This is the only formula in our constraint table。

 This is the only formula we're gonna use everything else here is gonna be a number。

 the sign corresponds to do you want to be less than or equal or equal even or greater then doesn't matter。

 but we want to be less than or equal it's okay if we spend all our money the money is there but the key is you don't want to spend money you don't have so our formula for the lefthand side is a sum product one more time How's it working out just a shortcut I also want to just for good practice。

Let me put dollar signs here。 Let me do my absolute referencing。

 So I'll use the keyboard here to do that that's function F4 hit enter and that'll lock it in。

 notice it doesn't change the values。 it'll just set me up if I want to drag this down if I have other constraints。

 good practice。 I don't want to lock in my cells the 200 and500 that could be problematic because I do want this to scroll down as I go So we'll do our formulas with dollar signs and then the right hand side is just the budget。

 What do I want to be less than 40 remember I type the numbers in naked don't put the commas don't put the dollar signs in just type the number if you want to format it to dollar signs you certainly can although you don't So that's what this constraint looks like inside of Excel notice every cell gets a number we don't type in equations don't type in sentences Excel doesn't read can do All right let's keep going so each radio ad cost 200 that200 now in spreadsheet and reaches an estimated 3000 people。

So now my objective， this is a new one here。 I want to maximizeim this number。

 What is the thing to max， Maxim the number of people。

 Each television ad costs 500 and reaches an estimated 7000 people。

 So what you do here is you put the coefficients for each one underneath。

 So let's do that coefficients。For objective。 like what is the what's the point。

 What are we trying to do here， What do we want to maximize where you put this。

 It doesn't actually matter， but it would just only put numbers as a reminder。

 So the radio ad reaches 3000 people。 There you go。 and the number of TV ads reaches 7000 people。

 Those are obviously important numbers They should go somewhere on my spreadsheet。

 we tend to put them right below the variable they correspond to Then the objective， the max。

 which mean let's be more clear。 the number of people reached。It's okay if you go over。

 just make the calm wider and itll be deal。Keep pretty spreadsheets going along here。

This is our objective self。 This is the thing that we want。 This is the the answer。

 How do we know we have the best possible way to do this。 We usually highlight this gray。

The colors may change， but just highlighted something makes it easier to find throughout the video series here。

 we will highlight it gray。 Now， how do I know how many people it will reach。

 remember each radio ad reaches 3000 people。 So what do you do You multiply that up and then each TV ad reaches 7000 people。

 So what do you do， You multiply that up and then you add them together。 You could do it by hand。

 but let's get fancy。 Let's use the some product formula。 I'll take 4 and5。

 and then I'll do comma 3007000。Hit enterter when you're ready and you get the total number。

You can format it， make it a number， make it all pretty。Since this is people。

 we don't need decimals here， maybe a lot of comma。

And now I can really test if the spreadsheet is working， watch if I change four to a7。

 all the numbers should change and you can of course check this offline just to make sure that this is actually working so whatever the numbers are going to be。

 so I'm going go back my four but you can see the spreadsheet was working if I misclicked by accident having these dummy numbers in there will help me find that as I go along。

Alright， so anything else。 Now she has stipulated that at least 10 ads of each type be used delation a request a requirement that all sounds like a constraint。

 So let's go to the drawing board for a second before I actually put that in here。

 I have my at least 10。 Now， this is actually two constraints。 at least 10 TV。 And then of course。

 at least 10。Radio。What does that mean So my the number of radios here just my dummy variables for。

 This should be at least 10。 Which one do I want， do I want less than or do I want greater than what's the I one if I want to be at least 10。

 be careful， English is a tricky language。 If I want to be at least 10 It means I need 10 or 11 or 12。

 I need to be greater than So the one I want is greater than 10 and of course my TV ads here。

 my TV needs to be greater than equal to 10。So let's think about how we would set that up here。

 so let's label our constraints， at least 10 radio。At least。10 TV。And how am I going to copy。

 how am I going to count down， I really want to use some product one more time？

 So whenever you want to just kind of copy the number down。

 you just want that four to appear like test if it's a four， you can multiply by one。

 you think about it by one。 So if I put a one here and a one here。

 watch what happens when I multiply it together。 I'm just going drag the formula down。

And I will drag the formula text down so you can see it what's happening。Notice the left hand side。

 the thing that I want to test， the4。Howuse is calculated。

 This is the sum product of what1 times 4 plus 0。 when it's blank， there's a 0，0 times 5。

 Confi yourself that1 times 4 plus 0 times 5 is actually 4。 And for all the same reasons。

0 times 4 plus 1 times 5 is just 5。 So whenever you just want to count or you just want the number to appear。

 you just want to check against the number， you put a one in there for the coefficient。 And here。

 at least would be greater than or equal， greater than or equal。And then we put in our constraints。

 notice the sign column and the right hand side RHS column are just numbers， the formula。

 the only calculation that has to happen， and it's the same calculation every single time comes from the left hand side。

Al right， what else？ So each television ad is $500， reaches as me as $7000 people。

 The campaign mayor would like to reach as many people as possible。

 but she has stipulated that at least 10 ads of each type be used。 we took care of that。

 Also the number of radio ads must be at least as great as the number of television ads。

 Oh boy another requirement， another stipulation Let's go to the drawing board and try to figure out what that actually means。

 the number of radio ads must be at least as great as the number of TV ads。 Where can I work on that。

 So let's put this down here。 So this is the radio ads must be at least as great。

 So they have to be sort greater than equal to TV ads。 I'll use R and T to denote those variables。😊。

Okay， so this is fine， but we're going to do a little bit of rearranging here。

 normally on the left hand side we have a numbers you can do it， but we like to be consistent。

 we want the t to be on the other side。 so let's go back to a little bit of basic math here。

 You can subtract T to both sides。And you get R minus t is griddd to 0。

 These are exactly the same constraints。 This is saying when you have two numbers and their differences is positive。

 It's saying that R is bigger than t。 stare at that for a second。 Think about that。

 convince yourself that that's true。 And now what do you do here， you grab the coefficients。

 You grab the coefficients。 So what am my coefficients on the variables。 Well。

 when I have variable by itself， it's like one。 And then， of course， this is -1。😊。

So those are the numbers that are going to go into our constraint table， you always grab the numbers。

 do not， it is very common， but I guess understandable do not enter letters or sentences or variables in these cells。

Don't tell people put r some people put minus t， that doesn't make sense。 So if we want1 and minus1。

 but that's where it's coming from。 These numbers， these coefficients on the variables represent the equation。

 I copy down my formula copy down my formula one more time there it is。

 you can pause the video if you want to see it This should make sense I'm always grabbing my variables the four and5 these are probably not right just taking a guess here but I just want to make sure that everything's working let's give this constraint a name So we'll say R greater than or equal to t you can something better if you want to just remind you what it is so you can talk about it if you're checking the inequality here is less than greater than or equal one more time and then here I actually want this to be0 I want this to be0 that comes from rearranging the sentence So I always want a number on the right you try to do it with a number on the right。

I'll copy the formula text down to show the actual formula in the left hand side。

AndNow I think we've gone through so at this point we would read it one more time。

 we would check it like crazy， make sure we didn't miss a constraint。

 these constraints come at you in any particular direction， there's no rhyme or reason to them。

 so just make sure we feel good about it。Okay， I think we're good next。

 now I want the right answer right so now you can play the game like what is the right answer if I have one and if I have six I can reach 45000 people Is that good。

 I don't know， let's play so that one radio ad would cost me $2006 at $500 each well that would be $32000 that's well under my $40000 I could probably go higher know so if I go higher。

 why don't I just do 10 ads here and maybe 20 ads here okay so I'm still under budget。

 but I have some problems here because I'm failing the fourth constraint the number of radio ads is not see this negative 10 here。

 this would not be good I than zero this particular answer wouldn't work it's not a answer in our feasible region。

So we really want to find the best answer This is where you can kind of see the power of solver Sor is going to find the best answer that will maximize this satisfying all the constraints we don't really want to sit here and guess and check and say well it's the best number that I could find we'd like to guarantee that it is the best so here we go data。

Sver。And the pop up box always looks the same。Let's go through。 we're going go top to bottom here。

 we set the objective。 The spreadsheets are going get more complicated。 They're going to get larger。

 color coding really helps with this。 It is always the gray cell。

 click the cell for me it's B5 then I want to remember you can always minimize it you don't want to minimize the number of people reached that' would be pretty bad so we just make sure we have max min selected here I remind myself in the spreadsheet that it's a max and the variable cells those are our green ones so color coding helps do that so we highlight the green cells inside of the box So1。

2，3 things are set。Now， subject to the constraints inside of here， inside of this box， we hit add。

And we get this three little boxes pop up。 This is gonna be our left hand side。

 our sign and our right hand side。 So the left hand side。Is gonna be 1200。I can change the sign。

 It's a dropdown so you can always change it if you need。

 but here it works out quite nicely less than or equal and the constraint。 don't type anything。

 Never type anything。 just click， you can always make a mistake if you type it So just click that as you go and then we don't hit okay。

 It'll actually take it back。 You only hit okay at the very end。 So' a little confused。

 but you hit add and we'll do another one we'll do the left hand side and now it is greater than or equal to the right hand side。

So it lines up with our table， these are the three columns that go after our variable cells。

 let's add another one。So our left hand side is going to be this 20 that's showing here greater than or equal to the constraint。

Let's add another one， one more less one。 we take our lefthand side It is greater than or equal to our constraint and we can check this at the end。

 it's obviously easy to select the wrong box but hit OK when you're all done and there they are so1。

23，4 corresponds to one tooth notice your ability to sort of do solver to put the parameters put the constraints in the solver is only as good as your spreadsheet if you missed one of the constraints if you typed in the wrong number on your table or do something like that know then solver is gonna be wrong and the spreadsheets is going wrong and you' going to get the wrong answer So this is why you have to check along the way as you go。

Allright， other things that we could do if you obviously if you had a changer to delete it。

 they're all here if you wanted to just start over you could reset all。

 this is a checkbox it says makego constraint variables and non negative that's saying that can these variables be non negative。

 should they always be zero or above you can certainly come back and say I don't want any radio ads I don't want any TV ads perhaps that's the right answer Who knows but you certainly don't want to come back and say I want negative for radio ads I definitely don't want them to be negative that normally doesn't make any sense to have negative in these word problems So it's by default checked on solver and we usually we just leave it checked。

It' would be really weird if you came back and said I want negative3 radio ads and negative to TV ads。

 you might not hold on to that job for too long。 So De and make sure this is checked All right select a solving method。

 we're doing everything LP linear programming so please select simplex LP。

 these other algorithms are sort of not appropriate for this problem we'll talk about them later in the course but simplex LP is the one that you want and when you're ready。

 you think everything's good you hit solve。Depending on your computer。

 it can be a little slower and a little faster， but here's what you want。 solver found a solution。

 All constraints are optimally satisfied。 so we keep the solver solution， we say okay。

And we hit thank you。 And we're good to go。 Now， this is amazing。 Appciate what solver has done。

 It's come back and says the best possible answer that you could find is 1 hundred75 radio ads and 10 TV ads。

😊，You can check if you were guessing before， as we were。

 if you want to go back and look when I plugged in some random numbers。

 I did not get this answer of 595 my answer， which know even wasn't even feasible。

 wasn't even allowed based on the constraints was much lower So this use of solver takes away all guess and check work。

 It is the best possible answer。 it removes that gut feeling。

 it removes you know that sort of I think this is the best one and gives you that confidence to say this is the best one and this is a wonderful tool to have to master to be able to build these spreadsheets because you can imagine going against a manager or some other colleague with experience and this is how we've always done it the worst possible answer I hate hearing that but you come back with a more analytic approach you can defend your spreadsheet you can defend the model and this will be the best answer。

 So this is really nice。 The one thing that I'd like to have my students do is at the very end。

 I do something what's called a summary sentence。Because it's one thing to find the answer。

 but then it's another thing to communicate it back。

 a lot of people don't realize what they actually have， what they're holding。

 So remember what you're doing here， let's answer the actual question。

The number of radio ads so we should purchase。Hundred and seventy5 radio ads。

10 TV ads to reach a maximum of 595000 people。So here's where you would watch your units。

 Here's where you'd actually present the answer。 You can imagine writing an email to your boss and sending the spreadsheet。

 perhaps as an attachment as needed you would never just send someone a spreadsheet without any explanation of what's going on。

 So this summary sentence is extremely important reminds you of what you found just helps you to remind yourself of the units and does everything make sense。

 Did I stay under budget。 I spend all 40000 Do I have at least 10 radio。

 I certainly do 175 is larger than 10。 Do I have at least 10 TV。 Yes， I do。 the bare minimum here。

 and is the number of radio ads larger than number of ts。 Abutely Thank you solver。

 Thank you very much。 Here's my answer，595。Allright， fantastic。 So this is a very simple example。

 I really want you to master this one。 The constraints are pretty straightforward。

 You can imagine how does this get more complicated。

 We could introduce more complexity and the constraints。 The numbers can get larger。

 we can have more variables There's lots of ways to go from here this is the first level first foundation start here。

 master this one， build it again from scratch know if youve got something very similar could you do it save this model as a template for linear programming So if you want just call this like LP template or something from here。

 all things will grow， we'll have more constraints go down。

 we'll have more variables going across and of course the problems will get a little more complicated as we go。

😊，All right， great job on this example， we'll see you next。


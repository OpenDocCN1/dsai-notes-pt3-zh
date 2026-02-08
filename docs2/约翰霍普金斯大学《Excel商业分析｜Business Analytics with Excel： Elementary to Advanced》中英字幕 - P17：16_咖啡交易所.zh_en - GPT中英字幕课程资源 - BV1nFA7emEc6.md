# 约翰霍普金斯大学《Excel商业分析｜Business Analytics with Excel： Elementary to Advanced》中英字幕 - P17：16_咖啡交易所.zh_en - GPT中英字幕课程资源 - BV1nFA7emEc6

Hi， everyone， welcome back。 Today we're gonna do a mixed integer example。

 This is another type of LP problem， a linear programming problem。

 We've seen all the pieces of this before。 This problem， although it's short and simple。

 is going sort of put some pieces together and allow you more flexibility when doing these LP problems when using solver to find optimal solutions。

 If you haven't read the problem， please do so pause video and read it。

 Think about as you go through it。 What is the objective。 What are you trying to maximize。

 what are you trying to minimize， Think about what your variables are if you're the consultant to this cafe manager。

 What are the answers that you want to come back with。

 Last but not least think about your constraints。 What are the things that are limiting and now we've seen some more complicated or subtle problems where the constraints are both listed explicitly here there's a nice table for us or things that are sort of hidden behind the scenes in between the lines that you have to be a little bit more clever about a positive video read the problem if you have not done so already and that we can go through it together。

😊，Ready， let's begin。 Baled a cafe is especially coffee shops selling custom blends of coffee using three types of beans。

 So I'm a store owner。 I have three types of beans。

 A B and C as they're called down here in the table。

 and I sell two products 20 bags of blended coffee beans whole。 these bags。

 They're beautiful nice logo a very attractive。 I want to sell them。

 and then individual bags of grinded beans sold by the pound in bulk。 These are my two products。

 The grinded beans can be produced in any quantity。 both bags are composed of three different beans。

 again， A B and C from the table below 20 bags sell for 85 and the bags of grinded beans sell for a dollar 50 a pound have to be a little careful here because the first object that I'm selling are just number of bags。

 And then the second thing that I'm selling is of beans。

 So I have two different units going on and maybe just want to keep track of that from my understanding。

 but let's start to put down our variables here。 I have number of 20 bags。

 The 20 in the 20 is just the。😊，I don't use it for anything。

 as well be red bags or blue bags or whatever。 but I don't use the number 20 for anything。

 And then I sell pounds of beans。 I sell pounds of grinded beans。 These are two variables。

 so I will color code them green。The next thing I want to do is think about what am I trying to maximize。

 I definitely want to maximize my profit。 So this will be my objective。

 and I will remind myself that I want to maximize my profit。

 definitely do not want to minimize my profit。 And now you think about what is the profit formula。

 What is it actually equal to how do I make money for each bag that I sell。

 It's given in the problem。 These sell for $85。 I' usually put that number right below the variable cells and will format it to dollar signs for grinded beans for the。

 It's 50 a。 I'll put it in 150 and once again format that 2 signs。

 We can put some dummy numbers in our variable cells。

 I like to put dummy numbers in to make sure that the spreadsheet is working as I go along。

 There's an error I don't want to find it at the end。

 So I will completely make up numbers here and have about4 and 5。

 I'm going format the pounds of grinded beans to show couple decimals here。

 I want to see because I can sell beans in any quantity。

 So the problem says I want to know if the right answer is 5 or 5 and half pounds5 and a quarter。

I do want to see that the decimals here。 Sometimes when you type a number in the default is to show it as an integer and that could still give me the right answer。

 but then my formatting would be wrong。 and I wouldn't actually know the right number Sa me here with pounds bags'll put that number in home Allright so what is our profit function Let's color code this gray just so that we have it It's easy to see this will be a small spreadsheet compared to some other ones that we've done but let's follow best practices as we go along So if I sell four bags for 85 I would multiply those numbers together if I sell 5 of beans for 50 a pound I would multiply those numbers together and then my total profit would be the sum of all that。

 Where am I going with this you guessed it some product highlight the variable cells highlight the money that each makes close the parentheses and hit enter。

I will show the formula using the formula text function so you have it there。

 and you should play around with this。 make sure your spreadshe is working。

 make sure you understand what this thing's doing。 you can put  six in or something like that。

 and the number will update whatever your dummy number is you should hopefully see this thing update as it goes along so I have my profit function。

 Everything looks great。 now I just need to put in my constraints。 So let's make a constraint table。

 This is back to Lp problem。 So we're doing not transportation here we're not assigning anything this is back to Lp this is called mixed integer。

 You'll see why in a second as a reminder we've done these before we go three columns past the variable cells。

 I have I So I need three more D I go let's put in some borders just to make this readable and we'll make a nice little table and now think about what this is。

 So you're producing these bags of coffee or you're selling them grinded as a mix as a blend and you have three beans that come in from your supplier So I have be A B and I only have as an amount available。

Pound for a800 pounds for B and 200 for C。 That is a limiting resource。

 I can't use more than that for being A B and C。 So the number of bags that I make are the pounds that are grinded beans that I sell no matter what I do I still can't use more than 2000 so I label my table lefthand side sign and right hand side and hopefully you can see this is all gonna be less than or equal to all three are just limiting resources。

200 for a 800 for B and 200 for c What goes in to the columns of the table is the amount needed for each product So I need 30 for a 18 for B and 2 for C and I line all that up with column B which is my number 20 bags and then I do the same thing for my blends for my grinded beans in bulk5。

4 and。1 with this combination and with these dummy numbers if I have4 20 bags and each bag needs 30 How many did I use。

4 times 30 is 120 and I do the same for the pounds of grind of beans once again I multiply and then I need to add to keep track of my total so we're gonna use our favorite function our some product highlight the variable cells and then highlight the coefficient cells for me it's B2 and C2 comma B9 and C9 close the parentheses and there it is I'll show the lefthand side formula using the formula text this highlights a cell and shows the text notice once again in the lefthand side column the LHS column。

 This is the only formula in the entire constraint table everything else is typed everything else's hand entered Once I have this ready to go I can drag it down but I have to be very careful I need to put dollar signs。

 if you caught this give yourself a little pad in the back here I need to put dollar signs in you can use the function at4 feature or just type the dollar signs in they always go before the B before the two before the C before the two。

Without these， and I drag without these， I'd have a problem， I'd get the wrong cells。

 So you can always check to make sure it's working。 if you double click any formula。

 you'll see the highlighted cells that's using the calculation notice as I drag the B2 and C2 stayed exactly the same。

 but then， of course， B10 and C 1 did not So there we。

 we can drag the formula text down and we have our beautiful constraints。 I have my variables。

 I have my objective。 read the problem one more time。 make sure we're all good。

 I think I have everything I didn't copy any numbersly done that before。

 So let's go to solver data solver set your objective to the gray cell。

 This is the profit that you want to maximize。 So make sure max is selected。

 changing my variable cells。 will be my green cells。

 the two things right now that have dummy variables in there。 Subject to the following constraints。

 Now this is wonderful。 They're all less than or equal。 So let's batch upload these。

 I'll highlight all three of my left hand side less than or equal to and then I'll upload all three numbers in my right hand side。

 so we can batch。😊，Those wonderful。 And I hit okay。

 I make sure the box is checked to make unconstrained variables not negative。

 and then I set my solving method to simplex LP LP， of course， for linear programming。

 I hit solve solver found a solution。 All constraints and optimality conditions are satisfied。

 So I hit okay I say thank you， solver and solver came back with a number。 Now。

 here's the difference between a computer and a human。 the computer will get the number。

 but will never interpret the number and see if it makes sense。

 I strongly recommend once you think you have an answer write out the summary sentence write out what that email would include to your client what the PowerPoint presentation would say。

 And here we would recommend producing let's say here44。444 it's too many decimals to be useful。

 will just say one or two bags of。😊，A whole beans，20 pound bags。

And and let me pause here for a second。 And hopefully you caught it。 If you didn't catch already。

 stare at this pause， see what the problem is。 Why am I pausing here。

 And it's a key thing that's in this problem， And this is what separates this problem from the other ones。

 It says you can sell two products are 20 bags， you cannot sell0444 or whatever reasonable number of decimals you want of this particular item。

 So you can't go back to do this。 You can't do this。 And when you have this condition。

 you actually get 0。 So the max profit here is 30778， but the answer doesn't make sense。

 The answer doesn't make sense。 We missed something inside a solver。

 And what's the other constraint here。 I'm just going to put it on the table that we don't use it。

 It is that the number of 20 bags。Must be an integer。 must be an integer。 This is important。

 Only one of these variables has to be an integer in terms of the pounds of grinded beans。

 That could be any number I want。 I can have decimals there， I can have decimals there。

 So what I have to do how do you do this。 Well， the wrong way to do it a lot of students do is they'll round。

 They'll say， oh integer， you just need integer， no problem，44。44 that turns into 44。

 and I'll do this and I'm done And man， this is such a common mistake。

 Please don't be the person that does this。 when you have an integer mistake。 sorry。

 when you have an integer constraint， go to data， go to solver and add that constraint you can always go back and add to your preexisting constraints。

 I say， look， the cell that I want the B2 the number 20 bags。 This has to be an integer。

 you have to put that on。 select integer from the dropdown and that auto populates the constraint field。

 and that's how you tell solver that that number needs to be an integer。 Do not round。

Not One thing you just might want to give a quick check under your options。

 Sometimes there's a box back here that says ignore integer constraints。

 You want to make sure that's unchecked。 You certainly don't want to if tell it to be inger I need to be an integer So everything stays the same。

 I just add this constraint again I do this in solver and I hit solver found a solution once again I say thank you solve and hit so now the number of bags is the inger44 So that was the rounded answer could round no not really because why if you remember the answer before said make0 or grinded beans So if you just rounded answer you would have one right but the other one wrong So half right is all wrong So I recommend producing 4420 bags now and 20 watch units of the grinded bean mix and this produces a maximum profit of 30770。

If you remember if you said， what if I just rounded。 remember this number 30770。

 if you put0 in here and say， look， you're selling a product that you shouldn't。

 I recommend only selling 20 bags。 you're gonna have another issue because now that answer produces a profit of 3740 which is less than the maximum profit of 3770 So recommending 20 of these grinded beans meets all the constraints that you're in its the best possible mix of your beans and that produces the best possible profit go over this one mixed integer because some other the variables are integers that is okay here we only have two variables and one is an integer and one is not if you have 50 variables you could have one be an integer you could have all 50 integers or anything in between's the whole point。

 So this now allows you completely normal that this happens allows you to tackle more problems with different meanings of the variables again。

 turn the integer。Ttrainin on in solver do not round as you go along All right。

 great job on this example， I'll see you next time。


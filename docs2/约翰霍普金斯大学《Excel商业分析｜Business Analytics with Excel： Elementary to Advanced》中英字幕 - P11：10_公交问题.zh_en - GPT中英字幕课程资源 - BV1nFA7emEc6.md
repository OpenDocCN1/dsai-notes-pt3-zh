# 约翰霍普金斯大学《Excel商业分析｜Business Analytics with Excel： Elementary to Advanced》中英字幕 - P11：10_公交问题.zh_en - GPT中英字幕课程资源 - BV1nFA7emEc6

All right， everyone。 welcome back。 We're gonna do one more problem here。

 This is gonna be sort of the largest problem。 I want to say largest。

 though and not most difficult because again， we're always sort of looking for the same thing whenever we do a linear programming problem。

 What are our variables。 What are the constraintss。

 What is the objective Do we want to maximize or minimize something。

 Here's what is called the busing problem。 And part of it is just a little difficult to sort of decipher what's going on here。

 So we're gonna spend a little bit of time working through this one。 pause the video。

 read the problem if you haven't done so already， and then we'll work through it together。

 If you want to try to start to model this problem， that would be good to。Alright， let's begin。

 Hopefully you pause the video and read this one on your own。

 So what I'm gonna to do here is draw a picture to sort of help motivate this one。

 And you'll see how this one is a little different than the other ones。 First off。

 Johns Hopkins is setting up three charter schools in Baltimore City。 Yookko High School。

 Devon High School and Manny High School named after former students of mine。

 each high school has the capacity of 900 students。

 The mayor hires your company to sign except to students to these new schools。

 buses will be provided to students who live more than walking distance defined as 1。

5 miles to the school。 Baltimore City has been partitioned into five neighborhoods。

 A B C D and E Koko High School is in sector B。 Devon C Manny High School and E。 All right。

 so first off， let's draw pick never been to Baltimore。

 here's my rough sketch generally of Baltimore City， give or take。

 and for no good a reason we're going to divide it up into five segments。 So let's do that here。

 have 1，2，3，4， and we'll say  one more for5。 Great， and we're calling these neighborhoods A B D。😊。

put E over here。 fantasticantastic。 Now we have some high schools that live in these neighborhoods。

 So Kioko High school is in sector B。 so we'll put a little high school here。

 there's my school for kokko High school。 Devon High school is in sector C。

 So there's another high school here in sector C and Manny high school is in sector E one more high school Yes。

 they all look the same from Manny high school here in sector E Now if a student lives in a sector and is assigned to the high school in that sector。

 the student can walk so if I'm a little student and I live in B I can go right to B I walk I don't have to take the bus now I don't get a bus even I cant not even an option but if I get assigned to say another high school well then I have to take the bus so there's my little bus and I have to take the bus。

 So all students must be assigned a school。 you can't leave anyone out make sense。

 I want to minimize so this is the first time that we've seen this。

 I want to minimize the total student miles traveled by bus So there's lots of ways that we could bus all these kids around。

Have the table here below with the distance。 and you can imagine if we picked randomly。

 maybe it's not the best way to minima is the miles so a student mile is gonna be the number of students and basically how many miles of traveling and then we add them all up So just for the table below here。

 I have distance in miles from the sector to the school So just to read the first column I have sector A and it's five miles so the distance between a and B here is five miles my picture obviously not drawn to scale from B it's de high school and sector C it's8 miles and many high school and sector E it's six miles and I have 700 students to assign。

 So this problem is gonna show the importance of labeling your variables。

 So think about what you have to do。 I have all these students in a 700 in total and they have to get to assign a school。

 they can't be assigned to a high school and a there is no high school and a so they have to get assigned to B and E and C somehow some way and I have to do it for all 700。

 So let's think about this for a second。 How am I gonna model this problem and I have to do the same for sectors B。

C， D and E， what's the best way to do it。 Well， as usual， let's set up our variables。

 And what I'll do is I'll work maybe below this time and row 20。

 And I'm going to set these up in a particular way that hopefully this makes sense。

 before you see me write out the actual term like number of students from a to assign to high school B number of students。

 That's a little wordy。 could also do it in terms of just generic letters。

 you've seen me do that before。 X1 x2 x3 for the investment problem。 I did that。 This one here。

 I'm going be a little clever and I'm going to try to say， look。

 I'm going to assign you students from A to B from a to C from a to E。 I'm going to do this。

 I'm just going call it A B。 This is going to be my variable cell。

 And also just to mix up the template because again， this is gonna to be a little trickier。

 we're gonna go a B A C and A E。 So I'm going to label one of these but just realize what this is。

 This is the number of students to assign from A。To the high school in B you can see why I'm not going write all this out here。

 so maybe I'll merge and center just to have this and then we'll continue the pattern the entire time and that'll be what A B stands for And what I want to do is this is the variable cell that I'm after。

 how many students do I have to do What's the right number to do meeting all the constraints minimizing the total bus miles and going along So when I do it this way right I have five sectors。

 A B， C D and E and three high school how many decision variables am I going to have Well A to B A to C A to E B to B。

B to C and B to E， there's three more。 So for every sector you have three sort of decisions to make five times 3 is 15。

 So now we're gonna have problem。 and this is gonna to be the largest one we do in the entire class。

 But you can imagine they get as large as you want。 It can Excel can handle up to 200 of these。

 I just don't want you to be scared if you have to like write out 15 variables。

 Like I that is that a normal thing to do。 Is that allowed， Yes， of course， so we have B B， B， B。

 E C， B， and C， E， And then， of course， D B。D D E so we write it all out again just uses as many cells as needed and last but not least E B E and E E sometimes you could even go down the page Excel does not care if you go across a row or down a column but we're going to be consistent here we're going label this with our green cells and we can throw in some numbers here。

 some dummy numbers just to make sure our spreadsheet is working as always not a bad idea usually considered best practices to throw in some dummy numbers So the way to interpret this is with these numbers here I'll do12。

3 is I'm gonna to send one student from a off to Kyokco High school and sector B and and two students from sector A to devon High school and sector C and then three students from A to E Now obviously this is wrong this if this where the answer I would send six students and six students only that's kind of a problem because remember I have 700 students to fill so I have to figure out how to you send these seven students that's obviously a constraint but once we have this。

Variable cells set up。 we can do our objective。 So our objective here is to what This is a minimum。

 is， I think the first minimum that we've seen together in the videos done a lot of maximizing profits or return on investment。

 but now I want to minimize my student bus miles my student bus miles。

 So how do I know how many miles that it takes well now this is where the table comes in if I send a student from a to B that students traveling 5 miles And from a to sector C。

 that's 8 and then from a to E that's6。 So I'll put all of these below below here。

 and I'll mention what they are。 they come right from the table and it'll take me a second to fill this out。

 but these are miles travel the miles traveled So we have 5，8。

6 now notice it goes right to B so that0 because remember those students are walking4124，0。

7725127 and 0。 So0 corresponds to。I mean students have to walk。

 though we only care about bus miles traveled。 All right， so we check all that。 That looks great。

 now our objective is gonna be the student bus miles。 This is what we want to minimize。

 and we will color code are objective cell gray。 and how do I calculate this number for every student from A to B。

 they travel 5 miles。 So I would multiply it by all the students here。

 two students are traveling 8 miles that'll be 16。 and that would contribute to my total。

 So once again， we're using our favorite formula。 some product。

 We take all the students and all the miles that they have。 yes， they' are 15 of them。

 but that is okay， close the parentheses hit enter and everything is great。

 We'll use the formula text to show the actual formula。

 and I have my variables and I have my objective。 A lot of students struggle here。

 if you notice it's actually relatively simple so far。

 The hardest part is just deciphering the question。 A lot of students struggle just to set this up。

 even though it kind of follows the same。😊，Template so hopefully you got somewhere got a good start on how to do this。

 but you can see here the challenge of how to define the variables。

 how to label the variables that is extremely important to set up a problem。

 especially one that you want to pass off to somebody for readability So now let's do our constraints。

 Let's think about what we have。 Read the problem again。 really， what's the constraint。

 I have to send all these students out right？ so I have to send out all 700 students but also in the problem What do we want to do here。

 Each high school has a capacity of 900 students right there。

So I have to send everybody out and I can't over send。 I can't send 900。

 So it doesn't matter which one we do first， but let's do the 900 in school B。

 perhaps and 900 in school A， notice again， one sentence giving rise school C one sentence is giving rise to more than one constraint。

 that is pretty normal， So we have 900 in school B 900 school ski C in 900 in school E。 Okay。

 so how do I do this。 My constraint table always goes to my variable cells。 and then 1，2，3 more。

 we're almost getting off the page here。 Let me zoom in a little bit to C everything。

 I'll put some borders on this just to make this more readable。

 But let's think about who's getting sent to B。 let me label this first。

 So left hand side sign and then my right hand side。 and we're told。

 remember that I can't send any more。 So less than equal。

 less than equal and less than equal then 900。 These are all numbers， no formula。 Okay。

 I just now need to count。somehow who is getting sent to school B。 So think about this for a second。

 What do I want to do if I just want to count something if I just want the number to appear。

 we've seen this a couple times now you just put a one in the table。

 put a one So this will take a to B and remember B to B these are the kids from B going to B they contribute0。

 but I still like to count them I absolutely need to make sure they're counted in terms of the total I'm sending students from sector C to school and B and sector D and there's a pattern here which you can start see So if I put five ones in here corresponding D section are once do my some product formula this will be counting some product total number of students to B's see that actually happen。

 So highlight the green cells highlight across hit enter and lo and behold there are five students so far that are being sent to B And if I change something let's change a to b to B5 you can see the number over here has changed to9。

 So what this is doing's multiplying one times51 times1。So there's 6， another one times1 is7。

 there's8 and another one。 So it's multiplying and adding as we go。 I'll do the formula text。

 I'm gonna run our room here， so I'll do it up here and I'll do it just for one of them the pattern will be the same and there it is。

 So that is your formula remember as always I want to put the dollar signs in place。

 so I'll highlight it， I'll do function F4 is the keyboard shortcut you can certainly type them in directly if you'd like。

 and then I just have to keep track of all the students going to C。

 and because of the way I list these out there's a nice pattern here It's just gonna be a one to the right of everything so this will keep track of who's going to C from a who's going to C from B etc cetera。

 work your way across I'll drag our formula down and last but not least who's getting sent to the high school in sector E well we have students from a students from B students from C students from D and students from E so you get this nice little pattern here corresponding to everything and you can check。

Using our dummy numbers that these are all being added up correctly that we can check it against this cap of 900 when we actually do the right the right thing。

 Okay so that is the restriction on the number of school。

 That's the first part I also have five sectors。 I have to sign all students for the sector into the high school So I have 700 students for a so let's write that down 700 in a I got 500 and B I have 100 and C。

 I have 800 in D。 and I have 400 in5 sectors， a bunch of students that need to go each one of these is a constraint。

 you have to assign the students to a school。 They don't all have to go to a school in a different sector。

 but they have to get assigned to school Okay so how do I count how many students are being assigned from a Qword here being from a so I add up the students from a from a and from a。

 There are three possibilities corresponding to the three columns of a right there。1，2。

 and three these ones。 When I do my sum product。RightBlans are treated as zeros。

 They count up the numbers，5 plus 2 plus 3。 These are all the students from A going to B。

 all the students from A going to C， all the students from A。

 So when this number equals and this is slightly new as well equals， notice by the way。

 if you type equals and hit enter。Oh it actually works。 Okay。

 I thought sometimes you might need like the single apostrophe。 If it's not working for you。

 you can do the single apostrophe equals and that also gets it as well。

 That says I'm not actually wanting a formula。 I don't want to be less than or equal here。

 That's a problem because I don't it's not acceptable to send 600。

 I really do want to equal 700 students from a 500 students 100800 and 400。

 If you remember in solver there was a sign of equality in that dropdown menu。

 you can select equals here as you go through So we will actually use equal not less than equal here。

 and then this is the nice thing here。 there's a pattern to this。

 The first three are students from a The next three are students from B。

 the next three are students from C and you work your way across This often happens the sort of pattern in the constraint table when you get a large constraint you're often doing things different ways and different times the different pieces of the process and a pattern tends to emerge。

 It's hard to decipher It may takes a couple of times a practice to come up with good。Variable names。

 but you'll figure it out。 And of course， remember， once you make something in Excel。

 you can always go back and clean it up， make the spreadsheet more readable， minimize some things。

 remove some duplication。 That is okay。 I've done this problem many times in class。

 which is why I'm able to sort of do it directly。 But the first time we do it， know。

 you come up with an idea and then you polish it along the way。

 So we have all of our formulas cleaned up。 We have all the patterns here。

 We're counting everything and we read the question one more time just to make sure we didn't miss anything。

 we're going to go。 if you want， you can tell how difficult this would be by hand to try to figure this out。

 We're gonna jump right to solver。 So let's go to data。😊，Let's go to Sal。 And here we go。

So the spreadsheet actually is is cross long， but not that bad。

 but the color codinging certainly helps。 Our objective is the gray cell for me it's in B24。

 I want to minimize。 So this is the first time we're going do a minimum problem together。

 And I want to change the variable cells。 These are the green one。 So I highlight all 15 green cells。

 That is okay Again，200 is your max and 15 is still relatively small。 Subject to the constraints。

 So let's add some constraints together here。 I have my nice constraintstrain table。

 We can batch upload these。 The first three will be the left hand side。

 This will be saying don't assign any more than 900， please we want that to be less than or equal。

 You can certainly assign a high school less， which is not more。 So the sign will not change。

 And then the right hand side will do in a batch will do 1，2，3 will get all 900。

 So I want to add another one。 And now here comes my equality。

 remember the second one here is in equality。 And this is the5 sector。 So 1，2，3，4，5。 I want that to。

Equal and then their corresponding populations。 So that now is done。 and I hit okay。

 So there's two batches。 You can certainly do this individually。 It's kind of a pain。

 I wouldn't but you can do it individually as you go along。

 I want the checkbox to make unconstrained variables non negatives。

 And I want to change my solving method to simpleimpx LP。 and I'm ready。 and I feel good about it。

 I hit self solver found a solution。 all constraints are optimally and optimality conditions are satisfied。

 wonderful。 you say thank your you hit okay Again， this is something that I don't think anyone would been able to find by hand。

 or at least easily at all。 but with solver， it literally takes a couple clicks in a few seconds。

 And what this does。 Don't forget your summary sentence here。 What you just found is mildly amazing。

 You have minimize the bus miles traveled。 So we send 400 students we'll just do for a from a to B and the remaining remember there were a total of 700 here。

 So 400 and the remaining 300。Go to E the high school and E and you would do the same for you do the rest。

 etc ce。 stare this。 This is pretty cool。 Student in B。

 right you're gonna send all what's the way to minimize this。

 You're gonna send all the students in B to the high school and B that'll minimize the travel。

 they can walk and then you send out the rest here。 So that takes care of all of them B。

 But some high schools， unfortunately you have to send these out and you get your answer So the final answer would be for a minimum of 5400 I'll say student bus miles total miles as students are traveling on the bus and you can imagine different combinations would give really really different answers。

 if you try to mix this up just try， you can see how this objective even if you meet all the feasible conditions all the constraints it can be really large and again。

 the power of solver coming into play here。 So solver will find you the answer but it's only as good as the spreadsheet is set up your job is set the spreadsheet。

 make it readable and in a way to pass it off to someone else。

To go now do say a budget or some other forecasting。 Al right， so go over this one again。

 the hardest thing here to do is take this problem and set up the variables。 So once you have that。

 the rest kind of falls nicely into place。 Allright， great job on this example。

 We'll see you next time。😊。
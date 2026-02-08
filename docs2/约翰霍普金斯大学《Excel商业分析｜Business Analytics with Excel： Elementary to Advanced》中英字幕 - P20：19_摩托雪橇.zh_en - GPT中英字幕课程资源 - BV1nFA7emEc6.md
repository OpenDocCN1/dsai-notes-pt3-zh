# 约翰霍普金斯大学《Excel商业分析｜Business Analytics with Excel： Elementary to Advanced》中英字幕 - P20：19_摩托雪橇.zh_en - GPT中英字幕课程资源 - BV1nFA7emEc6

All right， hi everyone， welcome to our last example here for a nonlinear problem very similar to the last one。

 just a slight variation just to go through it if you want pause the video， read the question。

 see if we can set it up， grab the template from the last one or since it's a new template。

 rebuild it as we go ready Motocross of Wisconsin produces two models of snowmobiles， the X J6。

And the X J 8 in any given production planning week。

 Motocross has 40 hours available in its final testing bay。 That sounds like a constraint。

 Each Xj6 requires one hour and each Xj 8 requires two hours。 So let's put those in。

 We can already see those are coming。 We have some constraints。

 This is gonna be our hours requirement we have Xj 6 is require one hour and Xj8s require two hours we'll put in our labels of left hand side sign in our right hand side。

 We know our sign is going be less than or equal to the 40 hours available。 you good at this。

 you could already see it coming。 We'll add some borders on expand the columns and center everything。

 So it is pretty and readable。 We color code are variable cells to be green。

 how many of each one that I want。 and then revenue in thousands of dollars。

 Okay watch your units here。 given as follows。 Now revenue is going to come from a formula。

 So I have R equals and then this formula here。 X parentheses 4-。1 x。Plus y parentheses 5 minus。

2 This is a bit more complicated formula than you're used to。

 if you've done some of these business problems in other classes。

 you might notice the revenue formula tends not to be linear， so we need to somehow program that in。

 but notice though they do use just x So x here is the number of xj6s so maybe I'll to label things say like x equals the number of xj6s and y equals the number of xj8 What other pieces do I need here Now there's two ways to do this you could do some algebra and maybe distribute this across and simplify some things that's fine that's fine but I don't want to do algebra。

 I really don't want to do algebra。 I'd recommend against it if at all possible。

 I want to somehow figure out my revenue but what do I need I have x and I have y and these other terms that I need So let's label this4 minus01 x and I'm gonna need5 minus002 y I'm going label these up there and instead of putting it down below I'm just gonna put them to the right。

And you'll see why in a second。 I'm just gonna put them to the right。 Now， these are calculations。

 They are not decision variables on their own。 I don't want to find this number。

 I want to calculate this。 So let's make it， let's build it equals 4-。1 times the x number， great。

 and then 5 minus。02 times the y number。We'll center those。 and these numbers are calculated。

 And as you put in different numbers for x's and y's， well， then I have 3。8 and 4。9。

 So there are different numbers that are calculated。

 And you can play around with this and put in some dummy numbers again。

 just to make sure that your spreadsheet is working。 Then I have my objective。

 which is going to be revenue， which I want to maximize。Alright。

 so let's build out this formula again， color code the cell gray。 the formula for revenue。

 We're can grab it from the word problem。 It's going to be the x number times this other term 4。1 x。

 So I'll multiply it by D2。 And then plus my y term。Times 5 minus。02 y。 and I hit enter。

 and this is a non nonlinear formula。 Now be careful。

 Some people think this is linear because each term is linear like x by itself is linear。 the 4。

1 is linear y is linear 5 minus。02 y。 That is also linear。

 But when you multiply them together like this revenue formula does。

 you'll see you'll get an x square terms。 So I'm gonna need to use the G RG nonline program to solve this The revenue。

 I just want to remind myself that the units are in thousands。

 So I'll make a note for myself from my summary sentence。 So this here would be like 22000。

 Let's add the lefthand side formula。 Once again， some product of our variable cells。

 the two variable cells， some product and then the coefficients in the constraint and hit enter。

 This is the only constraint I have。And let's go to solver， put in our objective function。

 maximum and changing our variable cells， the two green cells。 Sub to my one lonely constraint here。

 Hi okay make sure the box is checked to make unconstrained variables non negatives。

 you don't want to come back with a negative number and then select your solving method G R G nonlinearar and hit solve and hey。

 look at that solver found a solution。 all constraints are satisfied。 And hopefully， again。

 if you caught this， give yourself a little pat in the back。

 It's gonna be weird if you come back as your summary sentence to produce， say 9。047 snowmobiles。

 Hopefully you stop right there and say how the heck do I make0047。

 So even though this is a non nonlinear example， Here is the sort of mix and blend of all the skills in this course。

 go back to solver。 what did I forget， can maybe you caught this， take the two decision variables。

 they are the number of snowmobiles。 they have to be an integer。

 So you're allowed to use all these things together。 This is perfectly fine。 and you hit okay。

And you run it one more time and now Salr found an integer solution within its tolerance。

 All constraints are satisfied。 and we hit okay so 10 and 15 are the correct answers and it will produce a revenue of $100。

5000 you can fix our summary sentence to actually have make sense。

 produce 10 Xj6 snowmobiles and 15 Xj 8 snowmobiles for a max revenue of 100000 multiply by1000 so 100500 here two of the variables。

 both decision variables were integers you can imagine a problem where some are some are not and we start putting all these skills。

 So if you got this answer， great job go over this spreadsheet， recreate it。

 make sure you understand what each piece is doing you can imagine introducing more complexity as you go along。

 All right nice job on this integer programming nonline program Great job we'll see you next time。


# UCLA《计算统计学｜Stats 102A - Computational Statistics with R 2024 Summer》中英字幕 p11 [11]Stats 102A - 2024 Summer - Video 11 - Loops.zh_en [BV1jizNBrEm2_p11]

![](img/c5091fb94e7f51f6cd3e9d78d1c27e9b_0.png)

Okay， let's talk about loops。So loops allow us to basically run a chunk of code multiple times。

 but maybe with slightly different conditions or maybe not conditions but like we can change some of the values a little bit each time we run it okay the four loop is probably the simplest and most common type of loop in R you give it a vector and it can be an atomic vector it can be a list and the forlip is going to iterate through each of those elements in that vector and evaluate the code block for each element in there so here I'm going to say4 x in one through 10 we want to cat it's basically kind of outputting to the screen x squared so it's going to start off when x equals1 and we'll do one squared and it moves on to the next element in this vector which is going to be a two。

And it puts two squared， then it goes to the next element and three squared。

 four squared5 squared all the way until it reaches 10 squared， 100。

 so cat is going to output cat x squared， followed by a space， no separators there。

 and so we get this okay one followed by space 4 space 9 space 16 all the way up to 100。



![](img/c5091fb94e7f51f6cd3e9d78d1c27e9b_2.png)

It doesn't have to be an integer vector like one colon and 10， you can give it a list here。

 and so here I've got a list of length  three， the first thing is a vector of length 3 then a vector of length 7 and then a true false vector length of two。

And we're going to say for basically why for each element in the list。For Y and L。

 what we want it to do is print out the length of y。

 so it's going to go to the first element in the list。

 which is going to be this vector length 3 and it's going to print out the length 3。

Then it goes once it's done there， then it goes to the next element in the list。

 which is this vector， ABC D EFG it's going to say what's the length 7 and it prints out7。

 then it goes to the third element in the list true false。

 what's its length2 and it prints out two so it can iterate through any vector whether it's a list or an atomic vector。



![](img/c5091fb94e7f51f6cd3e9d78d1c27e9b_4.png)

Here's another example， there's library data sets and one of the things in data sets is state names and so we can ask what are the first five？

States， an alphabetical order， we have Alabama， Alaska， Arizona， Arkansas， California。

And so if this is our vector， we can say for each state in state。 name 1 through5。

 so basically for each element here， we're going to cat to the screen the state。

 so it's going to start off with Alabama， then we're going to follow it with has。

 and then we're going to calculate the number of characters。In Alabama， which is 7。

 and then that's going to be followed by letters in its name and a new line。

 So Alabama has seven letters in its name， Alaska has six letters in its name。

 Arizona has seven letters in its name， so on and so forth。 Arkansas。

 California has 10 letters in its name。And that's your for loop。



![](img/c5091fb94e7f51f6cd3e9d78d1c27e9b_6.png)

As far as storing results from a loop， the best case scenario。

 if you know how many elements you're going to do， is to create a place to store your results。

And then fill them out rather than trying to grow the object as you go along。

 but of course you can only do this if you know exactly how many values to expect。

 so here I'm going to say， hey， I want to create 10 to the seven， so that's what 10 million things。

 I'm going to create create an empty vector repeat NA 10 million times and then I'm going to fill it in。

For basically I do sequence along， sequence along， the res for results is going to be a vector from 1 to 10 million。

 and what we want to do is we want to calculate x squared and store it into results position x because x is going to start off at1q3 and we're going to calculate。

Position one through you know 10 million and store those values and when we do that it went through 10 million and it took us 0。

64 of a second。

![](img/c5091fb94e7f51f6cd3e9d78d1c27e9b_8.png)

So it happened very quickly， okay？嗯。A little bit slower。

 but this is what you might have to do if you don't know how many results you're going to get is you just start off with kind of。

You know， one element here I just start off with zero。

And then I'm going to do the same kind of thing for x and1 through 10 million take x and square it and store it into position X and so every time I run this okay the first time I plug in a1 then the second time two squared I get four plug that in and to position two and that requires results to be resized to accommodate two values。

 then the third time it has to be resized to accommodate three values and so it takes a little bit longer。

 not drastically much longer but about you know 2。8 seconds to operate this okay so it's a little bit slower than this okay。

The worst， however， the worst offender would be to start off with some kind of empty vector and then kind of tack on your new result and copy that back into the results。

 so basically each iteration copies the current results vector taxs on combines it with the latest entry x squared and then stores that back into results。

So it requires us to kind of copy the current thing and store back in here。

 And here I'm only doing 1100th of the work， one through 10 to the 5， one through 100000。

 not 10 million。 and yet this took 13。64 seconds， Okay for 1100th of the work。

 So if I tried to do it for all。10 million， then I would take this and multiply by 100 and I would take me 1300 seconds。

 which is like。I don't know， 20 minutes or something， okay， a really long time。

We don't want to do that。Okay。Um so。

![](img/c5091fb94e7f51f6cd3e9d78d1c27e9b_10.png)

If you know how many values you need， then this is the best， if you're not sure then this is okay。

 but you should never be doing this。

![](img/c5091fb94e7f51f6cd3e9d78d1c27e9b_12.png)

Okay， a while loop is going to basically repeat until a condition in the while statement it evaluates to false okay。

 so here I've got。I start off with I is1。We're going to take 10 results here and we're going to say while I is less than or equal to 10。

 what we wanted to do is we're going to take i squared and store it into results position I。

 then we're going to increment I to number two。And then and this will run until the while statement becomes false。

 so after that if I becomes2， then we do two square position 2， then I becomes 3。

 and it keeps going and the output is 14916 up through 100 and what is the value of I when this finished okay？

Well， at the tenth0th iteration， when it stored 100， I was 10。

And 10 square is 100 and stored 100 into the 10 position， then I becomes 11。

 okay I plus 1 stores back into I I becomes 11。It goes back to the top of the while loop and now it evaluates the statement。

 I less than or equal to 10， that becomes false。This becomes false， so the loop stops running。

 it doesn't execute this code anymore， so the loop kicks out， it breaks when I becomes 11。

 so when we ask， what is the value of I， I is the value 11？Repeat。Is kind of like a while true。

 its just going to repeat forever until the break statement is encountered。

 so this is going to result in something similar， I start off with I is 1 we have a results vector of length 10 and then first we're going to take I square it stored into results position I so that's going to be one squared goes into position1。

 then we're going to add one to I。And。So I becomes 2。

And then we're going to ask if I is greater than 10 then break， so right now I is 2。

It is this is false， so we skip over the rest， we reach the end of the loop。

 we come back and we say repeatat， and so now I is 2， we do two squared。

 so 4 gets stored into the second position， I becomes3， this is false， we reach the end。

 now become I is 3， we store three squared and so on until we get to 10。At 10 squared。

We store 100 into the 10th position and we add one I becomes 11 and now we say if I is greater than 10。

 I is now 11 is 11 greater than 10， that is true so we hit break and once we hit break the loop stops okay if you don't include a break then repeat will run forever okay and if this while statement never becomes false it will run forever so sometimes you get stuck in these infinite loops because the thing that needs to happen for it to quit just never never happens。



![](img/c5091fb94e7f51f6cd3e9d78d1c27e9b_14.png)

![](img/c5091fb94e7f51f6cd3e9d78d1c27e9b_15.png)

![](img/c5091fb94e7f51f6cd3e9d78d1c27e9b_16.png)

So break is going to end the current loop， so kind of your innermost loop that's running right now。

 break is going to end that。Next will end the current iteration， but doesn't break out a loop。

 it goes to the next iteration of the loop。So here I'm going to do for I and one through 10。

 so this is the vector 1 through 1，2，3，4，5，6，7，8910。 we're going to say if I is divisible by2。

So if I mod 2 equals0， so if I is divisible by  two or if I is even， then break。Otherwise。

 keep going and when it keeps going， it's going to cat eye to the screen。

So what's going to happen Well， I starts off at one， this is false， one is not divisible by two。

 so it's going to output one to the screen， then it goes to the next thing I becomes two in the for loop。

Is two divisible by two， yes， so it hits break and then it quits so this is only going to output one to the screen。



![](img/c5091fb94e7f51f6cd3e9d78d1c27e9b_18.png)

Let's look at the next thing in the exact same code here， except instead of break， I use next。Okay。

 exact same code， but now we have next， so it starts off with I is1。Is one divisible by two。 No。

 So it skips that code chunk。 It outputs one to the screen。 It does cat one。 Then it goes。

And it says two， I is now2。Is I2 divisible a2， Yes， So it executes this thing。 It does next。

 So when it hits next， it。Quits the current iteration and goes immediately to the next iteration of the loop so it jumps to I3 is 3 divisible by  two no。

 so it skips over that code block cats three to the screen。

Then it goes it reaches the end of the code blocks it goes to the next thing44 divis by2 yes。

 as it hits next， then it jumps to5 and so what we're going to end up getting is just the odd numbers printed out to the screen because every time I is an even number it encounters next and it doesn't run the rest of the code block it jumps immediately to the next iteration of the loop。



![](img/c5091fb94e7f51f6cd3e9d78d1c27e9b_20.png)

We have a couple things like sequence length and sequence along。

 and these are helpful for creating the indexes。嗯。For basically the objects that we want Okay。

 so here if I have this list L， that's length 3， I could iterate over the elements of the list or one thing I can do is I can say sequence along L。

 and that's going to produce。A vector1，2 and3 to correspond to the elements in L。

 and then I can kind of subset L based on that so it's going to say give me the first element of x and I can say length of L is that and store that into position1 because sometimes you need to know what position you're in or which iteration you're in and so having something using sequence along as that is helpful and it's going to go through the first thing it's going to say length3。

 then the next thing length 7， next thing length 2 so that's sequence along。Consequence link。



![](img/c5091fb94e7f51f6cd3e9d78d1c27e9b_22.png)

嗯。You might say like why do I need to do that Can't I just do like length of L。

 length of L is 3 and I can just do one colon 3 and that's going to give me 1，2。

3 sequence along L will also produce 1，2，3 or you can do sequence length， length of L。

Basically give me a sequence of a certain length。Seeing one length of three。

 and that will also produce 1，2，3 and so these all seem like they're doing the same thing。

 Why do we need all of these things？

![](img/c5091fb94e7f51f6cd3e9d78d1c27e9b_24.png)

Well， the biggest difference happens when you have a length zero vector okay。

 so here L is going to be a list of length0。And if I do one colon length of L。

Then it's going to be the same as doing1 colon0 and that vector is going to be 10。

 and then if I were to try to operate， run this chunk of code， look what happens okay。

 because I'm asking for L double square bracket1 here， which doesn't exist。For this list。

 then I get a subscript out of bounds。

![](img/c5091fb94e7f51f6cd3e9d78d1c27e9b_26.png)

Okay。Meanwhile， if I have sequence length， okay？I have start of empty list and I do sequence length or sequence along。

 okay sequence along， it produces a zero length integer vector。

 And then so trying to run a four loop on a zero length vector 4 x and basically sequence along L is zero length vector。

 nothing's going to get executed if you do sequence length， of L So sequence length of0。

 you're gonna to get a zero length vector。 also， nothing's going to get executed。 no errors there。

 Allright， so nothing execute， but it doesn't produce any errors。

 whereas over here it tries to do something and you just get an error。

 So using one colon length of L can run into issues if you end up with a length0 vector。



![](img/c5091fb94e7f51f6cd3e9d78d1c27e9b_28.png)

![](img/c5091fb94e7f51f6cd3e9d78d1c27e9b_29.png)

When you deal with loops and Stean R。You might want to try to vectorize your code rather than dealing with a loop。

 okay， so loops are fine， but they are slow in R。 So rather than using a loop。

 if you can vectorize your code， it's going to be better to vectorize your code。

 So a lot of times the performance of your R code can be improved if you're able to think of a way to vectorize it。

 Now it's not always possible to vectorize the code it's not always going to be worth the effort。



![](img/c5091fb94e7f51f6cd3e9d78d1c27e9b_31.png)

OkayAnd in some cases， it's going to be better to write inefficient code that takes a little bit longer to run than getting stuck for hours trying to think of some things that's going to save you a few seconds。

 okay？So there's kind of this。Quote from Donald Canuth about premature optimization。

 premature optimizations is the root of all evil about 97% of the time。

 but he writes" yet we should not pass up our opportunities in that critical 3% if you are able to vectorize or make your code more efficient。



![](img/c5091fb94e7f51f6cd3e9d78d1c27e9b_33.png)

So here's an example。Okay， so here is a piecewise function。

This piecewise function is a negative x cubed when x is negative。

 x squared when x is between 0 and 1 and the squared of x when x is greater than 1 so here I have a function that uses if it's going to be work。

 but it's not vectorized okay it says if x is less than or equal to zero。

 the value is going to be a negative x cubed，If。Else if if x is less than1。

 I don't necessarily need to check if x is greater than0 because this is only going to get evaluated when that is false and so then the value is going to be x squared and then finally if that's not true then we'll use squared of x and this function is going to return whatever value we get okay。



![](img/c5091fb94e7f51f6cd3e9d78d1c27e9b_35.png)

If you try to use this function as is and you apply it to a vector。

 so here I'm going to create a sequence going from negative 2 to positive 2 by 0。01 and I try to。

Throw it into the function F。It's not going to work because x is this long vector and it tries to do if x is less than or equal to zero。

 we get a condition， basically a logical vector of length， you know whatever。



![](img/c5091fb94e7f51f6cd3e9d78d1c27e9b_37.png)

![](img/c5091fb94e7f51f6cd3e9d78d1c27e9b_38.png)

401 or something says condition has length greater than one， so that's not going to work okay。

 and so if I try to plot this， this is not going to exist。



![](img/c5091fb94e7f51f6cd3e9d78d1c27e9b_40.png)

What I have to do is I have to run a for loop and so I'm going to say the values I'm going to plot。

 we'll start off with kind of zero along the length of x and then we're going to say for I sequence along x。



![](img/c5091fb94e7f51f6cd3e9d78d1c27e9b_42.png)

And then I'm going to subset x to that eh value。I'm going to run f on x sub I。

 and then I'm going to store that into plot values， square bracket I。

 and then that evaluates and now it can plot it and so here I get negative x cubed。



![](img/c5091fb94e7f51f6cd3e9d78d1c27e9b_44.png)

Then x squared and then the squared of x from here。



![](img/c5091fb94e7f51f6cd3e9d78d1c27e9b_46.png)

So this is the evaluation of the function there。Okay， another thing we can do。

Is we can run an if else statement， okay？If else here I'm going to break it down first we're going to check if x is less than zero。

 if x is less than or equal to zero， then what we want is negative x cubed。If it's not。

 then check another condition， I'm going to run another nest and if Elson side there。

 and so the next thing we're going to check is if x is less than or equal to1， if that's true。

 then do x squared and if that's not true。Do the square root of x okay so basically it's the same kind of thing that we have going on here。

 but I'm running an ifL statement and you can get this real compact inside a function like this。

 but this might be a little bit tough to read， but I've got f else x less equal to zero。

 do negative x cubed if else x less than or equal to 1， do x squared otherwise do squared of x。



![](img/c5091fb94e7f51f6cd3e9d78d1c27e9b_48.png)

![](img/c5091fb94e7f51f6cd3e9d78d1c27e9b_49.png)

![](img/c5091fb94e7f51f6cd3e9d78d1c27e9b_50.png)

Then I have my sequence， my vector x from negative 2 to 2， we're going to do pi equal 0。01。

 then I can run the function on x directly， okay， I don't need a loop。

 I can just take this function F2 and run it directly on x stored into plot values。

And and it runs and it evaluates okay， and and you get that Okay， sometimes， oh， the warning is not。



![](img/c5091fb94e7f51f6cd3e9d78d1c27e9b_52.png)

![](img/c5091fb94e7f51f6cd3e9d78d1c27e9b_53.png)

For whatever reason the warning is invisible here， but sometimes you get a warning， okay？



![](img/c5091fb94e7f51f6cd3e9d78d1c27e9b_55.png)

And the way if else works is basically it evaluates。



![](img/c5091fb94e7f51f6cd3e9d78d1c27e9b_57.png)

This statement。For the entire vector of x， it also evaluates this， for the entire vector of x。

 and it evaluates this for the entire vector of x。

![](img/c5091fb94e7f51f6cd3e9d78d1c27e9b_59.png)

This square root of x only exists when x is positive。

 the entire vector of x goes from negative2 to positive2， and so for everything less than0。

 when you ask for the square root of say negative 2。

 you get an NA because the default behavior type double is it gives us just kind of equivalent to real numbers and doesn't know how to deal with complex values so it's just going to give you an NA if you ask for the square root of a negative number。



![](img/c5091fb94e7f51f6cd3e9d78d1c27e9b_61.png)

And so it evaluates for the whole thing and when you get these NAs you're going to get basically you get a warnings there okay so the FL statement evaluates the entire basically true expression and the entire false expression for the entire vector and then once it has those then it's going to select values from the true vector where the condition it evaluates to true and then it selects values from the false vector where that condition evaluates to false。

 so that's how the FL statement okay。

![](img/c5091fb94e7f51f6cd3e9d78d1c27e9b_63.png)

There's also to improve efficiency， there's also a couple vectorized operations we have row sums and column sums in R and they work very fast as far as calculating row row sums and column sums for matrices and if you have a way to kind of make use of these things。

 you can really speed up your。Your calculations。 So I'm going to create like this big large matrix。

1 million rows，100 columns。 I want to find the mean of each row。



![](img/c5091fb94e7f51f6cd3e9d78d1c27e9b_65.png)

Okay， here， if I say let's subset。To the row and find the mean， it takes us a few seconds， 3。

67 seconds to do this。 we're going to say， you know for for the number of rows， we want to do this。

 but here。Another option is to use apply， you can say apply the mean function along the margin and that takes 6。

48 seconds， but if you use row sums， basically sum of the rows and divide by the number of columns of x because we just basically want the mean of each row。

 look how fast that is 0。27 seconds， so so much much faster if you use row sums versus apply or subsetting to a row and calculating the mean okay。



![](img/c5091fb94e7f51f6cd3e9d78d1c27e9b_67.png)

![](img/c5091fb94e7f51f6cd3e9d78d1c27e9b_68.png)

Are all of the values that they calculate equal， yes， they're all equal， so if you do all equal。

 substing the row， finding the mean， applying the mean function。



![](img/c5091fb94e7f51f6cd3e9d78d1c27e9b_70.png)

Across the rows or using row sums， they all evaluate to the same so obviously if you can make use of row sums that's going to be the fastest。

 but you know sometimes you got to puzzle and think about it to come up with a solution。



![](img/c5091fb94e7f51f6cd3e9d78d1c27e9b_72.png)

![](img/c5091fb94e7f51f6cd3e9d78d1c27e9b_73.png)

![](img/c5091fb94e7f51f6cd3e9d78d1c27e9b_74.png)

All right， that's that。
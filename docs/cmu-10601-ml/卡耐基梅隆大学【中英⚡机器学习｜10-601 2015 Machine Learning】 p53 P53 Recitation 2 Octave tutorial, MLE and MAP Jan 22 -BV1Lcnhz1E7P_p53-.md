# 卡耐基梅隆大学【中英⚡机器学习｜10-601 2015 Machine Learning】 p53 P53 Recitation 2 Octave tutorial, MLE and MAP Jan 22 -BV1Lcnhz1E7P_p53-

Tial by Andrew Ing that we sent out。 it's in five or six parts。It's kind of long。

 but you can watch it on like 1。5 speed if you want to。And if you're familiar with MatTlab。

  Otave is extremely similar to Matlab。 The main difference being that it's free and open source。

So feel free to stop me if you have any questions。 I'm going to go through some。

Simple to progressively more complex。Functions and operations in octave。 So this is the。Octave G U I。

 you can also run it like there's also a command line interface。 but I thought this would be easier。

 Okay， so first of all， you can do some basic operations。 You can do like addition。Subtraction。

 you know multiplication。And division。et cetera。 And if you type just an operation like this。

 it'll print out the answer right underneath the next thing you can do is variable assignment so you can say x equals3 and now you have the value 3 stored in the variable X and you can print that value out by just typing x and if you assign x equals 3 with no semicolon at the end it'll print it out immediately but if you're writing like a function or a script that you want to run later。

 you pretty much always want to put a semicolon at the end so you don't get a whole bunch of printouts as your code is running。

So you can also do things like you know。Y equals 5。0， whatever， or you can create strings。

So single quoted strings， Z is hello。嗯。Yeah， so as I said before。

 you can print things out by just typing the variable or you can use the disk function where you can write。

Dis of a variable， which is a little nicer。 doesn't print like Z equals hello。 just print hello。

 You can also display。Slightly more complex things like using Sprintf within diskP。

 Sprintf is like a C function that just creates a string and allows you to pass in。

Like variable name， so it's something like this。嗯。So basically。If you're not familiar with S printf。

 you can look it up， but you can use things like percent D to specify integers。

 percent F to specify doubles and percent S to specify strings。

 And then so the first argument to S print F is a string。

 And then the next arguments are like the variables that you specified with those placeholders with the percentage settings in front of them。

 So if you type that， it'll display kind of a nice string that says， you know。

 that fills in the variable values in the percent D spots， etc。

So this type of thing is useful if you're trying to debug your code or something and you want to have it print something out。

Okay。So now let's talk about creating matrices and vectors。

So let's suppose I want to create a matrix A。 I can manually fill in certain values like this。

 So let's say 1，2，3，4。5，6， and the spaces indicate。That the variables are going to be in the same。

Row and the semicoons essentially start a new row。 So if I create this and then I print out a。

 you can see it's a 3 by  two matrix。And instead of spaces， you can also use commas。

 Comas and spaces are sort of interchangeable for。Creating one row。

Another useful function is the zeros， so you can。Create an all zeros matrix using this function。

3 by4 is the size of the matrix。 So that created a  three by four matrix of all zeros。

 You can also do use the I function。嗯。Which creates an identity matrix。

 so C is an identity matrix of size 4 by 4。And identity just means all ones on the diagonal。

You can also create vectors， vectors are just basically matrices where。

It's either just one row or one column， right。 And so you can just do。嗯。

Like five by one instead of five by three or whatever。And。So here I also use the ones function。

 which creates a matrix of all ones to create a matrix of all twos or threes or whatever you can just do three times ones。

 right。嗯。Another useful thing is something like this where you can create a vector with evenly spaced values。

 So this created 11 dimensional vector with like you know， 0。1。2， etc cea。😊，嗯。And finally。

 you can do something like concatenate matrices。 So if you do row。

 you can do rowwise concatenation using a comma equivalently。 So then D looks like this。 right。

 We concatenate it A and B side by side。And you can do columnwise concatenation using a semicolon。

 So if you do B， semicolon C。You can catnate B and C， so B is this， the all zeros。

 and C is that identity matrix we created before， so you cancatenate them one on top of the other。

 right？Okay， so that's pretty simple。Another useful set of useful functions are the R class of functions where you can create random numbers。

 So let's suppose you want to create a two by three matrix of uniformly distributed random numbers。

 Then we just use RAand。So these numbers by default are uniformly distributed in the 0，1 interval。

But you can change that， let's suppose you wanted。Something uniformly distributed in the one to two interval。

 right， you can just do like one plus RA。2，3。And now you've sort of changed the range of your uniform distribution。

Another useful function is Rand N， which creates Gaussian random variables。So。

I' suppose I want to create a Gaussian。Vectctor， so each element in this 5 by one vector is distributed according to a standard Gaussian。

 so normal 01。And again， we can。Change the parameters of the Gaussian by doing something like5 plus two times Rand n。

And now each element of this vector is distributed according to a Gaussian with mean 5 and standard deviation 2。

Okay， so those are very useful for generating。Random numbers。

Another useful set of commands are the size functions so you can get like so a was a  two by three matrix。

 and if you do size of a， it prints out two numbers。

 the number of rows first and then the number of columns， if you just want one of those。

 you can do size a1， which will print the number of rows and size a2。

 which will print the number of columns。And then finally， you can also use length。

Which is useful mostly for a vector， Pris the number of elements in the vector。

 If you run length on a matrix， it'll print the larger of the two sizes， which is。Not that useful。

 but。嗯。Okay。So。Sub indexing， okay so let's。Let'Cre a larger matrix， so a is now 100 by， let's say5。

So then I won't print a， but it's know，'s 100 rows and five columns。

 So let's suppose we want to just look at a single element of a。 So let's say we do a 2 comma 4。

 This will give us the element in the。Second row， fourth column of A。Then we can do a。

 suppose you want to look at the whole second row， we do a two comma colon。

 the colon means take all of the elements in either this row or this column in this case。

 since the colon is on the second argument。ItIt gets the whole row。Similarly。

 we can do like a colon three， which will get the whole columns， so it'll print like 100 values now。

 right？😊，嗯。We can also do， let's say we want the first five columns。 We can do a1 through 5。

Coma colon， and that'll print sorry， the first five rows。And then we can， you know。

 we can do different combinations of this。 we can do 1 through 5， commo 1 through 2， which we'll get。

Like the upper left part of the matrix， five rows， two columns。Finally。

 a useful thing is maybe you want specific rows， like so you want row 1，5， and 10。

 you can specify exactly those indices， and then like exactly those row indices。

 and then you could do the same thing for column indices， like suppose I want。Columns 2 and 4。

 for whatever reason。 Now， I've taken like a different subset of the matrix。

 not like the first three rows and the first two columns， but。

Exactly the ones that I specified with my indices。Questions about that？Okay。嗯。Okay， and yeah。

 and then finally， obviously， we can assign any of these things to new variables， right。

 so this assigns the first two rows of A to a new variable called suba。

So now I can print subA and you can see that we saved that， right？So this is useful。 Like。

 suppose you， you have a big data set and it's like it's your set of features。

 and you want to split it into a training and test set。 You might want to do sub indexing for that。嗯。


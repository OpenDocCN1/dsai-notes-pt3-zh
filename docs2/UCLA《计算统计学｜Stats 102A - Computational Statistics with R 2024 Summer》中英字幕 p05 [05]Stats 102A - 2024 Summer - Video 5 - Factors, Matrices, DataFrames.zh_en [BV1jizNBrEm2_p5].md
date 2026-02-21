# UCLA《计算统计学｜Stats 102A - Computational Statistics with R 2024 Summer》中英字幕 p05 [05]Stats 102A - 2024 Summer - Video 5 - Factors, Matrices, DataFrames.zh_en [BV1jizNBrEm2_p5]

![](img/2a356d4435118b8358a019b4a87d762c_0.png)

All right， let me talk about factors， matrices and data frames。

 so these are slightly more complicated structures in R so we talked about vectors。

 atomic vectors and lists。

![](img/2a356d4435118b8358a019b4a87d762c_2.png)

![](img/2a356d4435118b8358a019b4a87d762c_3.png)

A factor is used to represent categorical variables or categorical values internally a factor is just an integer vector。

 okay， it's just an integer vector， but we have attributes and the attributes are going to be basically the levels。

And then the class is going to be that it's a factor。And so here I have a character vector okay。

 well the character is MF，F， XM and F。 And so this is a character vector and I can turn this into a factor by using this function factor factor on this gender character vector and now I get。

When I ask for this gender factor， I get the values MFF， XMF okay。

And the levels in it also prints out something called levels。

 which lets us know that this is a factor one thing。You know。

 is when you print out a character director， normally get you see little quotes around the elements like this。

 okay？But here， the default printing of a factor is that it doesn't put little quote marks around it。

Here we ask what are the levels of this thing， this is just basically information that's stored in the attributes list and this will be FM and X and when you say type of okay the type of is an integer and what's happening is that internally。

The vector is going to say the integer 2， the integer 1，1，3，2， and1。 and when R prints out， it says。

 okay， I see the integer 2， we're going to get the second value from the factor which is in M it sees the values 1 and1 and says we're going to get the first value and those correspond to F it sees the integer value 3 that corresponds to x and that's what is happening when you can see internally what that is by calling as do integer on that factor and again。

 here we get 2，1，1，3，2 1 and again， when you ask for the attributes。

 you have the levels Fm and X and so the two corresponds to M the ones correspond to the F。

 the three corresponds to x。

![](img/2a356d4435118b8358a019b4a87d762c_5.png)

![](img/2a356d4435118b8358a019b4a87d762c_6.png)

When you ask R to create a factor out of a character vector like this。

 R looks over and sees all of the unique values， the unique values get put into levels。

 and by default R puts those levels in alphabetical order so F gets first position because F comes before M in the alphabet and M comes before the letter X in the alphabet。

 so we get FM and X。

![](img/2a356d4435118b8358a019b4a87d762c_8.png)

And so that's where we have the levels and the factor。



![](img/2a356d4435118b8358a019b4a87d762c_10.png)

And that's how it's stored internally， okay。

![](img/2a356d4435118b8358a019b4a87d762c_12.png)

There's a few things that could go wrong when you're dealing with factors， okay。

 if you have a vector of numbers and those get turned into factors。



![](img/2a356d4435118b8358a019b4a87d762c_14.png)

Then some weird things could happen。If I say， hey， zero，1， 10， and 5。

 and I say make a factor out of that。All right， then this X factor we get 01。

10 and 5 and we see the level 01，5 and 10 and if you ask for hey， what's the mean of this。

 it's going to give you an NA it's going to say hey。

 I can't take the mean of this thing because again factors are intended to be treated as categorical variables so you know even though it looks like numbers they're actually categorical variables you know it'd be kind of like asking。

 hey， what's your area code， you know your phone number area code。

 it looks like a number but it's actually a categorical variable it just kind of gives you like a geographic category because area codes are generally assigned by geography。

And， you know， it wouldn't really make sense to say， hey， what is the average area code， you know。

 of a group of friends， Okay， so you know one person's area code might be 818 and someone else's area code might be 310 and things like that。

 it doesn't really make sense to take the mean of those。Of the value 81，8 and 310， okay。

 that that that doesn't really make sense and in the same way。

 it doesn't make sense to take the mean of a categorical variable。



![](img/2a356d4435118b8358a019b4a87d762c_16.png)

Now， if you wanted to， you can kind of force it and you can say as numeric。



![](img/2a356d4435118b8358a019b4a87d762c_18.png)

Okay， asnumeric on the factor and then take the mean right and if you think about it 01， 10 and 5。

 that adds up to 16 and the mean should be 4， but when you say hey mean on this， we get a 2。

5 what's happening Well， when you call asnumeric。

![](img/2a356d4435118b8358a019b4a87d762c_20.png)

![](img/2a356d4435118b8358a019b4a87d762c_21.png)

On this thing， it gives us back one，2， four， and3， remember internally。



![](img/2a356d4435118b8358a019b4a87d762c_23.png)

It took these values 0，1，10 and 5， and converted them into these levels 01，5，10。

 and so zero is the first value， one is the second value。

5 is the third value and 10 is the fourth value， and so you know those values are 1，2，4 and 3。



![](img/2a356d4435118b8358a019b4a87d762c_25.png)

And all it's doing is it's taking the mean of 1，2，4 and 3， which is going to be 2。5 okay， but again。

 x underscore factor is a factor and it doesn't quite make sense Now if you did want to take the mean of 01。

10 and 5， what you can do is you can convert that factor into character。

And then you take those characters， convert them into numeric values， and then you take that。

 and you take the mean， so here we're going to turn01。

 10 and 5 into a character vector which will be quote 0， quote1， quote 10， quote 5。

And then we take turn those into numeric values， which will give us0 1，10 and 5。

 and then we could take the mean， which will give us four。



![](img/2a356d4435118b8358a019b4a87d762c_27.png)

Okay， other things about factors is if you try to assign values to a factor and it's something that's not in the list of levels。

 so in the gender factor， the list of levels that are allowed are FM and X and if you try to put something like。



![](img/2a356d4435118b8358a019b4a87d762c_29.png)

![](img/2a356d4435118b8358a019b4a87d762c_30.png)

Mail here it's going to induce an NA and so that's what that's going to happen。

 you have to kind of put in a value that actually makes sense。



![](img/2a356d4435118b8358a019b4a87d762c_32.png)

Or it is allowed。

![](img/2a356d4435118b8358a019b4a87d762c_34.png)

Okay， matrices。A matrix in R。Is basically an atomic vector。And that comes with a dimension attribute。

 a vector for the dimension attribute is a vector for the number of rows and columns。

 So here I am going to create an atomic vector of integers 1 through 10 that's going to be M。

And if I ask， hey， what's the class on this， this is an integer vector。

 now what I can do is I can use ATR to set the attribute and I'm going to set the dimension attribute。

To2 comma 5。Basically tells our I want two rows， five columns。And so now it。

Turns this atomic vector into a two dimensional data structure， and it fills it out column Y。

 so it goes one down the first column 12。Then the next column 3，4， then the next column 56， then 7，8。

 and then finally 9，10。

![](img/2a356d4435118b8358a019b4a87d762c_36.png)

And now when you ask， what are the attributes on M， it will say you have a dimension attribute。



![](img/2a356d4435118b8358a019b4a87d762c_38.png)

Which is the thing that we just created and it's got the values took two and5 in there。



![](img/2a356d4435118b8358a019b4a87d762c_40.png)

![](img/2a356d4435118b8358a019b4a87d762c_41.png)

And now if you ask what is the class of this thing where M used to be integer。

 now that RCs theres a dimension attribute， it's going to say， hey。

 this is a matrix which is kind of a subclass of an array。



![](img/2a356d4435118b8358a019b4a87d762c_43.png)

Now what you can do is you can get rid of that dimension attribute by just assigning null， okay。

 basically null says， hey， get rid of that， and it's going to get rid of the dimension attribute here。

 it's going to just kind of wipe that out and now M is back to being an atomic vector。

 one dimensional atomic vector。

![](img/2a356d4435118b8358a019b4a87d762c_45.png)

![](img/2a356d4435118b8358a019b4a87d762c_46.png)

![](img/2a356d4435118b8358a019b4a87d762c_47.png)

And if you ask with the class on this， it's going to be integer。

Arays in R are basically atomic vectors， but now the dimension attribute has a length greater than two。

And so here I have a vector A with the integers1 through 12 and here as far as the dimension attribute。

 I'm going to set assign a vector。With the values 2，3，2 okay so that's basically two rows。

 three columns and two levels or two layers or two sheets。

 however you want to think of it and it fills it out first by across the rows then through the columns and then across the sheets so we get1。

 two，3，4， five6 and the first sheet then the second sheet， 7，8 down the first column 9。

10 and the second column and 11，12 and the third column。And so so we can do that。

 you create the value and then。And then you can assign the dimension attribute。

Okay you can also create an array using the the function array basically。

 and you would provide it with， you know， the values and then the。



![](img/2a356d4435118b8358a019b4a87d762c_49.png)

The dimensions there。Right。So those are 2D。Or 3D structures， matrices and arrays。

 And then we have another two dimensional structure but this is a data frame。

 Data frames allow different value types so you can have one column that's。



![](img/2a356d4435118b8358a019b4a87d762c_51.png)

Floating point， another column with integers， or maybe these are also floating point。

 another column of floating point， you can have a column with character values。

 column of logical values， however you want it。Internally。

 a data frame is stored as a list and the lists inside that data the elements in that list are all going to be vectors that have the same length so。

Basically， this data frame trees has a list of three things， a list for gith， a list for height。

 a list for volume， and each vector has a length of 31。



![](img/2a356d4435118b8358a019b4a87d762c_53.png)

So here you can see all of that thing。You can say hey， whats the class of trees。

 it says it's a date do frame， What is the type of。Internally。

 it's stored as a list okay and then if you ask for the structure of that。

 basically it says it's a data frame， basically a list where we have three variables。

 three elements in it。In that list and each one is a vector of length 31。

 and we can see it says numeric， numeric numeric， and these are the different values in there。



![](img/2a356d4435118b8358a019b4a87d762c_55.png)

If you call as dot list on trees， you can see what we have， we have a vector for girth。

 and it's a length 31 vector， a vector for height， and it's a length 31 vector full volume and again。

 length 31 vector there。

![](img/2a356d4435118b8358a019b4a87d762c_57.png)

And then if you ask， what are the attributes， okay， the attributes， we have the name。Names。

 column names， the classes data frame， and then the row names。

 the default row names are just the integers 1 through 31。

 but you could also assign different different row names there。All right， that's that for this video。



![](img/2a356d4435118b8358a019b4a87d762c_59.png)
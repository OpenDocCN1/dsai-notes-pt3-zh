# UCLA《计算统计学｜Stats 102A - Computational Statistics with R 2024 Summer》中英字幕 p09 [09]Stats 102A - 2024 Summer - Video 9 - Subsetting 2D Structures in R.zh_en [BV1jizNBrEm2_p9]

Al right let's talk about subsetting two dimensional structures。

 so we've talked about subsetting atomic vectors and lists which are one dimensional structures now we want to talk about subsetting two dimensional structures first we'll start off with subsetting a matrix or an array right so the most common way for subsetting a matrix is that you can subset using multiple vectors。



![](img/d7c466410c075298cefd223d42aad9ba_1.png)

![](img/d7c466410c075298cefd223d42aad9ba_2.png)

But you can also subset with a single vector， you can also subset with a matrix with a matrix itself。

嗯。Basically when you subset with multiple vectors， you provide a vector for each kind of dimension separated by a comma and if you leave one of those dimensions blank。

 you're going to get back everything in it All right so here is a matrix。



![](img/d7c466410c075298cefd223d42aad9ba_4.png)

3 by three matrix， I've got the values 1，2，3，456，789。

 the rows are unnamed but the columns are named ABC。I can say， hey。

 give me rows1 and 2 comma nothing， and that's going to give me rows1 and2， all of the columns。

 so I get rows 1 and2 columns ABC。You can kind of combine。

Either logical vectors or character vectors， so here I'm going to say。As far as the rows go。

 true for the first， false for the second， true for the third。

 okay so we're going to get the first and third rows， which columns do I want。

 I want column B and column A， so we're going to get column B for the first row and column A for the first row。

 column B for third row and column A for the third row， and so we get this。嗯。

You can say I want none of the rows and I don't want the second column Okay， so here we have no rows。

And we don't have the second column。Our outputs basically just the column names， A and C。

 but no contents of the matrix itself It's a little bit strange thinking about that。

 but again here's our original matrix three rows， three columns and we're getting back none of the rows and not the second column。



![](img/d7c466410c075298cefd223d42aad9ba_6.png)

When you subset a matrix by default， it simplifies， so if you say hey is my matrix of vector。

 it's not okay。But if you say give me back the first row in matrix A。

 you get back this 147 with the names ABC， this is not a vector， I mean this is not a matrix。

 this is a vector okay and you can say， hey is this a vector and it comes back and it says true。

 that is a vector and it's just a named vector with the names A B and C for the elements 14 and7。



![](img/d7c466410c075298cefd223d42aad9ba_8.png)

诶。嗯。Remember， matrices are really just atomic vectors with a dimension attribute。

 so here I'm going to take the first 25 letters， sorry Z and I'm going to arrange them into a 5 by5 grid so here I've taken the letters A through y and I'm going to make a matrix5 rows。

And I can just say so I could say I want。Third row second column so I can do vowels3 comma 2。

 and I would get the letter H。 Okay I could also say， hey， give me。Notice I have no comma。嗯。

At the level of the single square brackets， I give it a vector with 8 and9 in it。 Okay。

 I give it a vector with 8 and 9 in it。 And so this treats the matrix as just a length 25 vector。

 And we're going to ask for the eighth and the ninth elements in that。

 So it looks at the elements down the columns。 And so it counts the eighth element。

 So ABC D E is the fifth element。F is 6， G is7， h is the eighth element， I is the ninth element。

 so we get back H and I for the eighth and ninth elements in that vector。



![](img/d7c466410c075298cefd223d42aad9ba_10.png)

You can also subset a matrix with a matrix， this is a little bit less common but it can be done so if you have a two dimensional matrix or I guess all matrix these are two dimensional but I guess a two dimensional array arrays can be higher dimensions。

 you can kind of provide coordinates， so you can say first row fifth column。First row。

 fifth column is u， then I want a third row first column。



![](img/d7c466410c075298cefd223d42aad9ba_12.png)

Third row first column C。I want second row， third cone。Second row， third column bill。



![](img/d7c466410c075298cefd223d42aad9ba_14.png)

And first row， first column and we get back the letter A。

 So here I'm going to subset the matrix vowels using this matrix with four rows。

 one row for each element and two columns kind of giving it the coordinates of which I want。

 I want row 1， column 5， row 3， column1， so on and so forth。 Okay。

 and it's going to select those elements out that way。 If you want to subset。



![](img/d7c466410c075298cefd223d42aad9ba_16.png)

![](img/d7c466410c075298cefd223d42aad9ba_17.png)

![](img/d7c466410c075298cefd223d42aad9ba_18.png)

Say a three dimensional。Aray， then you provide it with a three dimensional。

A matrix with three columns， so here's an array with the elements went through 12。Two rows。

 three columns， two layers。And I can say， give me back。Row1， second column， first layer。Row1。

 second column first layer。Is the number three。Row2， third column， second layer。

Row2 third column second layer is the number 12， and we get back those elements。

 So here I have to provide a matrix with three columns， it's got two rows in it。

 so I'm going to get back two elements from that thing。



![](img/d7c466410c075298cefd223d42aad9ba_20.png)

Let's talk about data frames Okay now data frames internally again are stored as lists so。



![](img/d7c466410c075298cefd223d42aad9ba_22.png)

You can subset a data frame kind of like the way you would subset a list。

But data frames also have this two dimensional structure。

 so you can also subset data frames kind of like the way you would subset a matrix。

 So let's create a simple data frame， I'm going to call this thing Df。We've got the columns X， Y。

 and Z。And in column X， I' got  one， two，3， four。Column Y of 4321 and column Z， I have ABCD。

So here I can say subset the data frame and I give it a logical vector。

And I put in a comma so this is going to give me the rows that correspond to true for this logical vector and the logical vector is basically take the column y mod 2 basically is it divisible by2 mod2 equals0。

 so basically is the remainder after providingiding by 2 equal to 0， so is it divisible by 2？

And if that's the case， then it will be true for basically the even rows of y。

 so where y is 4 and y is 2， that's going to be true。

 and so we're going to get back the first row and the third row where the column Y is divisible y2。



![](img/d7c466410c075298cefd223d42aad9ba_24.png)

And we put nothing here so we get back all of the columns。

You can also subset a data frame just like a list， so single bracket single square bracket will give me back a list。

And here we're going to say， I want basically the train cars that are named X and Z。

And so we get back X and Z， and it's a data frame， so we get back a data frame with the columns X and Z。

If I want to subset like a matrix， I can put in a comma， basically all of the rows， comma。

 the columns， x and z。And I get basically the same results。

 so there's not much of a difference between this and this， but。Are there。

The way we have to kind of think about this is that this is。Selecting。

Train cars and then here we're saying I want to select columns now it's just that the train cars do correspond to the columns okay。

诶。Watch what happens here， so if I do data frame1 comma 3， and then I put a comma。

 then I'm going to select the rows 1 and3， I get rows1 and three all of the columns。

If I do a data frame and I put in the vector 1 comma 3， and I have no comma after that。

Then I'm going to get columns one and three。OkaySo there's a big difference。

 so back here not a huge difference between selecting column x and z or comma x and z。

 but here if I say rows1 and3 by putting a comma here， I get rows 1 and3。

 if I leave out that comma there， I get columns one and three so that's where you're going to have quite a bit of a difference there。



![](img/d7c466410c075298cefd223d42aad9ba_26.png)

If you have named columns， okay？Subsetting by this is。

Whereas I guess subsetting in this form where you say Df single square bracket。X， okay。

 the way you subset a list， you get back a data frame Okay， so if you ask structure of this。

 you get back a data frame， whereas if you say comma column X and you select only column column X。

 it simplifies。To just an integer vector， okay？So there is a difference here if you just select one column。

 single score bracket at x will give you back basically a data frame or a list。

 and here using the comma will simplify it down to a vector。

Dollar sign notation will always kind of simplify to a vector as well。

 and then using double score bracket will also simplify down to a vector。



![](img/d7c466410c075298cefd223d42aad9ba_28.png)

A little bit more on this concept of simplify versus preserving。

 simplifying the idea that when after you subset it kind of changes form from either you a matrix down to a vector or data frame down to a vector and in other cases it might kind of preserve or you might want to preserve the fact that it's a matrix or a data frame and so how can you kind of control that okay？



![](img/d7c466410c075298cefd223d42aad9ba_30.png)

We saw this earlier， single score bracket will preserve names on an atomic vector and double score bracket will simplify it and that it drops the names。

Where a list single square bracket always preserves the nature that it's a list whereas double score bracket will extract out the elements。

Of that list and generally simplify it。

![](img/d7c466410c075298cefd223d42aad9ba_32.png)

When you're dealing with a factor okay using a single score bracket will preserve any unused levels。

 so here I have a factor with levels A and B， and even if I select just a subset of the factor where it only has one of the values in it。

It preserves the levels A and B if you put in a comma and it feels a little bit strange。

 but using single score bracket one， basically I just want the first element。

 but then I put in comma drop equals true， then it will drop unused levels。



![](img/d7c466410c075298cefd223d42aad9ba_34.png)

For a matrix all right， so a is a tiny two by two matrix with a values 1，2，3，4， 1，2，3。

4 and a  two by2 matrix， you can say I just want the first row。

 all of the columns normally that would simplify it but you can put in another comma there。

 first row all of the columns and then you put in another comma drop equals false that will preserve the matrix structure now you have a one by two matrix so you start off with a two by two matrix now you'll get a one by two matrix。

Whereas if you just kind of use single score brackets in one comma and close it off。

 then it will select that first row again， but it's going to simplify it down to an atomic vector。



![](img/d7c466410c075298cefd223d42aad9ba_36.png)

し。Okay， well， the data frame。Using a single square bracket， so here's a very simple data frame。

 two columns A and B， value two rows in it using a single square bracket will preserve。

The data frame， if you're just selecting one column okay versus if you use double square bracket。

 you'll select that first column and it will simplify it down to basically just that vector。



![](img/d7c466410c075298cefd223d42aad9ba_38.png)

Yeah。All right， so let's look at a couple examples， so here is a data frame called empty cars。

 motor trend cars， and I think these are some older vehicles。

From Motor Trend magazine and it has you know these these different vehicles and it's got information All right。

 so this is just kind of the first 10 rows of that data set okay。



![](img/d7c466410c075298cefd223d42aad9ba_40.png)

What happened when I said， hey， I want to select empty cars cylinders less than or equal to 5。

 so let's look back， there's a column， cylinders。

![](img/d7c466410c075298cefd223d42aad9ba_42.png)

And we got six cylinder， four cylinder， eight cylinder vehicles。

 and I just want vehicles that have five or fewer cylinders。

 so I want something like the dotson 710 and the Merck 240D I don't know what that is Mercury 240D okay。



![](img/d7c466410c075298cefd223d42aad9ba_44.png)

And we get back error in selecting from the data frame， empty cars， cylinders less than or equal to5。

 it says undefined columns selected Okay Well， what happened？



![](img/d7c466410c075298cefd223d42aad9ba_46.png)

Okay， what happened was that because I left out the comma。



![](img/d7c466410c075298cefd223d42aad9ba_48.png)

This is going to be a big true false vector right， a big true false vector。

 so it's going to be something like false， false， true， false， false， false， false， true， true。

 false， okay？

![](img/d7c466410c075298cefd223d42aad9ba_50.png)

And so。I have one， two， three，4，5，6，7， eight，9， 10， 11 columns， I probably have even more rows。

 so let's say I have a true at like the 15th row。If I have a true at the 15th row。

 it's going to be trying to select the 15th column。



![](img/d7c466410c075298cefd223d42aad9ba_52.png)

Because without the comma we are selecting columns so that's going I don't want the first column I want I want the third column it would select the third column then the I don't know eighth column ninth comma column and then maybe the 15th column and it's saying undefined column selected。

 that's why we're getting there。 What we have to do is we have to put in the comma there。

 and this will now correspond to which rows I want。

 So now I want the rows that correspond to cylinders less than equal to 5 and indeed we got those vehicles that have five or fewer cylinders。



![](img/d7c466410c075298cefd223d42aad9ba_54.png)

![](img/d7c466410c075298cefd223d42aad9ba_55.png)

![](img/d7c466410c075298cefd223d42aad9ba_56.png)

![](img/d7c466410c075298cefd223d42aad9ba_57.png)

。はい。Here I said empty car cylinders equal equal4， basically I want four cylinders or six cylinders and I put in the comma。

I put in the comma， so I only want those rows。 but when you look at this， I'm still selecting。

Rows that have eight cylinders， okay， and I said， I only want four or six。Four or six。

 what's going on？Okay。Well， what's going on？Is that this is an ore operator？Okay。

And it's going to coerce whatever is on the left and whatever is on the right into logical values。

 So the statement on the left will produce logical values。 We're going to get false， false， true。

 false， false， false， false， true， true， false， false， false， so on and so forth。 However。

 the right is not a logical statement。 The right is just the number 6。

 And when it gets coerced into a logical statement。

What happens Anything that's not a zero gets coerced into true。

 so basically I have this true false vector， false， false， true， false， false， false， false， true。

 or whatever， or true。And so that's just going to become true for everybody。

 so we're going to select all of the rows， so what I have to do。



![](img/d7c466410c075298cefd223d42aad9ba_59.png)

As I have to do empty car cylinders equals equals 4 or empty car cylinders equals equals6。Then。

Then I have a true false vector on the left， a true false vector on the right。

 it's going to do the or statement and now I get just the rows that have six or four okay and I have the comma there。



![](img/d7c466410c075298cefd223d42aad9ba_61.png)

![](img/d7c466410c075298cefd223d42aad9ba_62.png)

![](img/d7c466410c075298cefd223d42aad9ba_63.png)

If I say empty cars  one colon 13， I get undefined columns selected and I might have been thinking I just want the first 13 rows okay。

 so again， you have to remember to include the comma if you leave out the comma。



![](img/d7c466410c075298cefd223d42aad9ba_65.png)

![](img/d7c466410c075298cefd223d42aad9ba_66.png)

![](img/d7c466410c075298cefd223d42aad9ba_67.png)

it's going to try to select the 13th column there's no 13th column。

 so that's where we're getting undefined。Columns selected so that's important to remember and keep in mind as you are subsetting there。



![](img/d7c466410c075298cefd223d42aad9ba_69.png)

All right， and that's it for。Subting our 2D structures。


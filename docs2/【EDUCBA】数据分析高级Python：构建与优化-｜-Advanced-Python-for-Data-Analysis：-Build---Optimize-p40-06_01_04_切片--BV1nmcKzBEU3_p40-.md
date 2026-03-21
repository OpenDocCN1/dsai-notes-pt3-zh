# 【EDUCBA】数据分析高级Python：构建与优化-｜-Advanced-Python-for-Data-Analysis：-Build---Optimize-p40-06_01_04_切片--BV1nmcKzBEU3_p40-

This is not an not a very efficient way of doing it， you know why。

 because this is this is equivalent into saying something like this x of 2， okay。

 let me store it in a variable， let me call it a stamp。



![](img/2a3a0afbe16b9be21ab21cf16380514e_1.png)

![](img/2a3a0afbe16b9be21ab21cf16380514e_2.png)

Right。😊。

![](img/2a3a0afbe16b9be21ab21cf16380514e_4.png)

So this is a variable called this temporary。And temp of。T0， so if I just print， print up10。



![](img/2a3a0afbe16b9be21ab21cf16380514e_6.png)

If I print up1， what you'll get is。This particular array。 Now I want to access an element in that。

 so I will say。

![](img/2a3a0afbe16b9be21ab21cf16380514e_8.png)

Temple。10 of2 once again。Okay， and then this will give me 15。 so you have temp of2， you know。

 if I now print or if I store it in something like a and if I print a。



![](img/2a3a0afbe16b9be21ab21cf16380514e_10.png)

![](img/2a3a0afbe16b9be21ab21cf16380514e_11.png)

Finally， you get the value 15。 But as you can see， there is a particular temporary variable being created when I do x of 2。

 So when x of 2 is nothing but you are creating a temporary variable and from that temporary。



![](img/2a3a0afbe16b9be21ab21cf16380514e_13.png)

![](img/2a3a0afbe16b9be21ab21cf16380514e_14.png)

From the temporary Nai， you are indexing the second element。 It's not very efficient。 It causes。



![](img/2a3a0afbe16b9be21ab21cf16380514e_16.png)

![](img/2a3a0afbe16b9be21ab21cf16380514e_17.png)

It causes problems in the you know memory as well as time efficiency。 Rather。

 Ny provides you a better way by saying instead of saying x of 2 and 2。

 it says just index it in this manner in this way I do not create a temporary variable。

 I directly figure out for you what is a value。

![](img/2a3a0afbe16b9be21ab21cf16380514e_19.png)

![](img/2a3a0afbe16b9be21ab21cf16380514e_20.png)

And that's how I get that for you。 Hope youre able to understand that right So here we have so this is the array oh sorry this is this one is the array for now I can just print that array once again and then try and index it once up。

 Okay， so this is the array and I need to index it in such a way So if I say x of let's say x of minus1 what is that going be。

😊。

![](img/2a3a0afbe16b9be21ab21cf16380514e_22.png)

![](img/2a3a0afbe16b9be21ab21cf16380514e_23.png)

![](img/2a3a0afbe16b9be21ab21cf16380514e_24.png)

![](img/2a3a0afbe16b9be21ab21cf16380514e_25.png)

That's going to be the last row，45，54，45，58，59，40。 Now， if I say x of -1。 and if I say I want the。

 I want the。The third element in that， what is the value going to be， this is0， this is1， this is 2。

 this is 3， so 58。

![](img/2a3a0afbe16b9be21ab21cf16380514e_27.png)

Al this is going to be 50。 So this is how I index a particular value。

 which is there in the particular number pi。

![](img/2a3a0afbe16b9be21ab21cf16380514e_29.png)

![](img/2a3a0afbe16b9be21ab21cf16380514e_30.png)

Hope you're able to understand。Cool， so with this particular you know understanding this nupy area and you know about this particular indexing。

 I can also index the last element by saying x of -1 comm a minus-1 there you are you have the 14 so or you can also say x of 1 comma minus-1 what is that 19 because this is the first row and the last column in that minus-1 if I say minus-2 that's going be this 45 out here why because minus1 is the index which comes so this is the index of each of these columns are going be 0。

1，2，3，4，5 and the reverse index from the end this is minus1 this is minus-2 this minus-3 minus-4 minus-5 minus。



![](img/2a3a0afbe16b9be21ab21cf16380514e_32.png)

![](img/2a3a0afbe16b9be21ab21cf16380514e_33.png)

Right so this is the way the entire indexing works in Nai area。 Now along with indexing。

 that is a second thing that we need to see and that's all about we can what we can do is let's say indexing and after indexing let me say the next thing that I was told you that our will cover is slicing right slicing is also a very beautiful concept in in what Python or Ny has introduced its it's quite amazing to figure out how things work that way。

 So first of all get Xprint and then let's slice so slicing is nothing but。😊。



![](img/2a3a0afbe16b9be21ab21cf16380514e_35.png)

![](img/2a3a0afbe16b9be21ab21cf16380514e_36.png)

![](img/2a3a0afbe16b9be21ab21cf16380514e_37.png)

![](img/2a3a0afbe16b9be21ab21cf16380514e_38.png)

![](img/2a3a0afbe16b9be21ab21cf16380514e_39.png)

![](img/2a3a0afbe16b9be21ab21cf16380514e_40.png)

You know， cutting forth part。Or slice， take a slice out of this array。



![](img/2a3a0afbe16b9be21ab21cf16380514e_42.png)

Let's say， for example， I just want to slice this portion where no， sorry， I want this 45，78。

15 and 18。 I just want to slice this portion。 Okay， so basically， it's gonna be a box or a rectangle。

 That's it。 It cannot be something like this。 You can slice something like this because this is nothing。

 Okay， this is not a box or rectangle。 but of course， you can slice this much。 Okay， or you know。

 you can slice but you cannot slice this。 This is not， this is not allowed。 you can slice。



![](img/2a3a0afbe16b9be21ab21cf16380514e_44.png)

![](img/2a3a0afbe16b9be21ab21cf16380514e_45.png)

Portions of it。 So how do I slice it。Okay， slicing is done with the operator called us a colon operator okay you have a colon operator which can be or a slicing operator。

 it is done with colon and we can do that very well with with you know by slicing it by saying let's say for example let's do it first of all for for us you know let's do it for a1D first so that youll you'll be more comfortable。



![](img/2a3a0afbe16b9be21ab21cf16380514e_47.png)

![](img/2a3a0afbe16b9be21ab21cf16380514e_48.png)

![](img/2a3a0afbe16b9be21ab21cf16380514e_49.png)

![](img/2a3a0afbe16b9be21ab21cf16380514e_50.png)

Understanding slicing over there， and then slicing with。



![](img/2a3a0afbe16b9be21ab21cf16380514e_52.png)

Slicing with the area out here， So let's say you have one comma，2 comma3 comma，4 comma 5 oh sorry。

 let me now just put let nuts put numbers like this so that you don't get confused， right？



![](img/2a3a0afbe16b9be21ab21cf16380514e_54.png)

![](img/2a3a0afbe16b9be21ab21cf16380514e_55.png)

Cool， so now if I say why， of course， I can just access it by saying y of 5。 What is y of 5。

 that's 2。 What is 5，0，1，2，3，4 and 5 y， so that's2 So y of 5 is2。

 but if I want to slice something like say for example I want to say y off I want to say y off and I want to get this much portion 4。

5 2， I just want to slice this much。 So4 what is the element what is the index number of 4，0，1。

2 and 4 is 3 so I can say y of 3， colon and go up till go up till which element 3， this is4。

 this is5。 Now if I put 5， you know what will happen there is going to be it is just going to return to you4 comma 5 only this much why because this one is exclusive This one is inclus So all I need to say over here is y of。



![](img/2a3a0afbe16b9be21ab21cf16380514e_57.png)

![](img/2a3a0afbe16b9be21ab21cf16380514e_58.png)

![](img/2a3a0afbe16b9be21ab21cf16380514e_59.png)

![](img/2a3a0afbe16b9be21ab21cf16380514e_60.png)

![](img/2a3a0afbe16b9be21ab21cf16380514e_61.png)

![](img/2a3a0afbe16b9be21ab21cf16380514e_62.png)

![](img/2a3a0afbe16b9be21ab21cf16380514e_63.png)

![](img/2a3a0afbe16b9be21ab21cf16380514e_64.png)

I need to make it over there，3， colon6。

![](img/2a3a0afbe16b9be21ab21cf16380514e_66.png)

There we have so because6 is exclusive， I get up till2 right so this is about slicing Now if I don't put the first element。

 if I just put colon6， it starts from the zero element and goes up till the six element Allright now if I put instead of say colon 6 I would say you know I start from3 but instead of saying colon 6 I just put a colon that's it it will go from the third element that is from4 and will' go to the last that is7 so this is about how slicing works it slices how bits and pieces of the array and gives you back what you require right so that's about slicing when it comes to a 1D array now let's see how slicing will work when it comes to2ri array so this is about x and tori how will it work sorry this is a 1 d this is a Turi correct how。



![](img/2a3a0afbe16b9be21ab21cf16380514e_68.png)

![](img/2a3a0afbe16b9be21ab21cf16380514e_69.png)

![](img/2a3a0afbe16b9be21ab21cf16380514e_70.png)

![](img/2a3a0afbe16b9be21ab21cf16380514e_71.png)

![](img/2a3a0afbe16b9be21ab21cf16380514e_72.png)

![](img/2a3a0afbe16b9be21ab21cf16380514e_73.png)

![](img/2a3a0afbe16b9be21ab21cf16380514e_74.png)

This work in a the area， I will have something like this excess。



![](img/2a3a0afbe16b9be21ab21cf16380514e_76.png)

Slicing， so I told you， I can give the row number first。 So if I say2。

Coma after the comma comes the column number。 So I can say2 comma 5。 But now。

 if I want a range of row numbers， I want to slice a range of row numbers。 Let's say。 I want the。



![](img/2a3a0afbe16b9be21ab21cf16380514e_78.png)

![](img/2a3a0afbe16b9be21ab21cf16380514e_79.png)

First， throw on words， I wanted。

![](img/2a3a0afbe16b9be21ab21cf16380514e_81.png)

From this particular row from the first row basically I want these four elements， 45 78。

15 and 80 so I want to slice these four elements I want these four elements finally so I want the first row and the second row and I need which columns01。

23 I want the second column and the third column so second and third column and the first and second row now what will I say here one colon will I say2 or will I say three because it exclusive you need to say three and then this will be what I want the second yeah I want second and third so I go second will I say three or will I say4 I'll say4 there I have slice 4578。



![](img/2a3a0afbe16b9be21ab21cf16380514e_83.png)

![](img/2a3a0afbe16b9be21ab21cf16380514e_84.png)

![](img/2a3a0afbe16b9be21ab21cf16380514e_85.png)

15918。 So again， this is nothing but another numpri as you can see。

 so I have sliced out a piece of the array and I have got it out for you。

 So that's how you slice out nupyes and you can figure out multiple things that can be done with slicing up to an array right let's check out some more things that can be done instead of saying one colon 3。

 what if I say colon 3， what will happen it will start from the starting row and go up till not three。

 but it will go up till2，3 minus1 because this is exclusive。

 So till2 So it came up till this row 1 to 3， but columns are again2 to 4。 So it means2 and three。

 not the fourth1，2 and3 so this came up 15124578，1518 Now instead of instead of saying that if I had said1 colon and if I remove the three out here。

 what would have happen it would have started from here it would have started from here it will start from here。



![](img/2a3a0afbe16b9be21ab21cf16380514e_87.png)

![](img/2a3a0afbe16b9be21ab21cf16380514e_88.png)

![](img/2a3a0afbe16b9be21ab21cf16380514e_89.png)

![](img/2a3a0afbe16b9be21ab21cf16380514e_90.png)

![](img/2a3a0afbe16b9be21ab21cf16380514e_91.png)

![](img/2a3a0afbe16b9be21ab21cf16380514e_92.png)

![](img/2a3a0afbe16b9be21ab21cf16380514e_93.png)

![](img/2a3a0afbe16b9be21ab21cf16380514e_94.png)

![](img/2a3a0afbe16b9be21ab21cf16380514e_95.png)

The rows， these would have been the rows， 45， 78，1518， 4558。



![](img/2a3a0afbe16b9be21ab21cf16380514e_97.png)

Alright， what if I put something like this。 Okay， so that's about one， Okay。

 what if I don't put anything， I just put a colon all happen。

 It will select all the rows from start to end。

![](img/2a3a0afbe16b9be21ab21cf16380514e_99.png)

![](img/2a3a0afbe16b9be21ab21cf16380514e_100.png)

Okay that's that's a huge feature about this Okay so can I do that with the columns too okay so let me say column colon4 it will start from the first and go up till the third right so012 and three so it will go up till three because four is exclusive okay but start from start from all out there right and if I put a value here two and instead of4 I just put it up here it will start from here and go up to the end because all rows are included but columns are from the second column and two is inclusive correct if I finally don't put anything just put column it will return to me the entire area as a whole。



![](img/2a3a0afbe16b9be21ab21cf16380514e_102.png)

![](img/2a3a0afbe16b9be21ab21cf16380514e_103.png)

![](img/2a3a0afbe16b9be21ab21cf16380514e_104.png)

![](img/2a3a0afbe16b9be21ab21cf16380514e_105.png)

![](img/2a3a0afbe16b9be21ab21cf16380514e_106.png)

![](img/2a3a0afbe16b9be21ab21cf16380514e_107.png)

![](img/2a3a0afbe16b9be21ab21cf16380514e_108.png)

![](img/2a3a0afbe16b9be21ab21cf16380514e_109.png)

Okay， now what if okay， there is some more addition to slicing and I hope you're gonna enjoy this hugely let's say I begin with the first element。

 go up to the last element， but I'd want in a particular step size what white do I can slice with a particular step size。

 Let's have a look。😊。

![](img/2a3a0afbe16b9be21ab21cf16380514e_111.png)

![](img/2a3a0afbe16b9be21ab21cf16380514e_112.png)

![](img/2a3a0afbe16b9be21ab21cf16380514e_113.png)
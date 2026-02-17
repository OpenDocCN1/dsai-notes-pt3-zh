# CMU《机器学习导论｜Fall 2023 10-301⧸601 Introduction to Machine Learning》中英字幕（deepseek p36 Recitation_HW1_NumPy.zh_en -BV1Z2cUefE4A_p36-

Alright， so in this tutorial we are going to be going over the Python package Nai。

 So Nai is basically a library in Python， which allows us to sort of very conveniently and efficiently manipulate matrices and vectors basically。

It comes in great handy when we end up doing leanar algebra。

So let me get into like some examples of what we can do using Numpy so here's how you would install Numpy in your like on your Mac or whatever machine you're using in a virtual environment just like you install any other package P install Numpy and we're importing Numpy as N here so that's how I'm going to be using all the functionality from the NumpI package。



![](img/a35a8cd140052c25b68a637ef74e6e63_1.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_2.png)

All right so。

![](img/a35a8cd140052c25b68a637ef74e6e63_4.png)

Like I mentioned to install lumpy， Pi install， etcter， etc ceter， let's move ahead。



![](img/a35a8cd140052c25b68a637ef74e6e63_6.png)

To import， were going to import it as import N as NP and we set NP do random do seed what this basically does is it setting a seed decides。

Its kind of the order of randomness basically every time you execute the same program。

 the way the output will be the same， basically the random number chosen will be the same if you choose a particular seed explicitly like here as such as shown。



![](img/a35a8cd140052c25b68a637ef74e6e63_8.png)

So yeah the printing minimum a version， this is the version we're using。

 so to the left here's like a TSB file。

![](img/a35a8cd140052c25b68a637ef74e6e63_10.png)

Whi is basically TSV means like tab separated values。

 so the first row is kind of the headers and then of the table and we have some sort of data here。

And I've just loaded that file into like a Google sheet here。And then also in the Nai area。

 we are loading it。

![](img/a35a8cd140052c25b68a637ef74e6e63_12.png)

So here is the syntax that you use to sort of load the data and as you can see。



![](img/a35a8cd140052c25b68a637ef74e6e63_14.png)

When we print it。So title here is data I'll get into this indexing later but as you can see using Numbai we have kind of loaded the file and were able to print the file so let's get into some more details we can understand what all these numbers exactly mean。

😊。

![](img/a35a8cd140052c25b68a637ef74e6e63_16.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_17.png)

Okay， so first of all。

![](img/a35a8cd140052c25b68a637ef74e6e63_19.png)

If we consider it 2 d array in this 2 row array we're going to be considering only 2D arrays。

 so basically which have rows and columns all right so if you consider this example this one23 basically this oop okay that's not highlight correctly but basically this part is the first row second row third row and we have the first row first sorry this is the first column this is the second column and this is the third column。

And basically we index starting from zero， so this would be the zeroth， one and second basically。



![](img/a35a8cd140052c25b68a637ef74e6e63_21.png)

So。For the first row first column we first do data is equal to NP periodroid array and this is how we specify this array that I have shown above。

 this is how we explicitly plug in the values to create data as anump array and then to access the element of the first row first column。

Basically， we will access it as row comma column， so we want the0 with row0 with column。😊。

And so when we print it， we get the value as one， which is what we expected。



![](img/a35a8cd140052c25b68a637ef74e6e63_23.png)

No。So this is a way to look at just a particular single element but if you want to look at multiple elements here is like data here is one sort of syntax where you can take an entire row so what we do is for the row index we specify that we want the zero through。

😊。

![](img/a35a8cd140052c25b68a637ef74e6e63_25.png)

And then for the columns we do zero column 2， okay so that means that select all the columns from column  zero up to column2。

Okay， so because we have only column 0，1 and 2 in our data nu array。

 this means we are selecting the entire0 through。All the columns from the zero throw， basically。

 if that makes sense。And then for the zeroth column likewise would do the same thing。

Wwhich would be0 colon 2 over here and as our first index and our second index would be0 but there' is another syntax that we can use that is demonstrated here which is instead of like explicitly doing zero colon2 if you just provide colon as the index that means that you are going to be getting all the elements so here we are getting all the rows and the zero column so yeah that's the indexing here。



![](img/a35a8cd140052c25b68a637ef74e6e63_27.png)

Similarly， if you want to present the just the first two rows you don't have to give like sort of the element before the colon you can just give two after the colon to present two print the first two rows and we see like the first two rows are printed here and if you want to see all the rows after the second row。

Then we sort of put two here， so yeah。

![](img/a35a8cd140052c25b68a637ef74e6e63_29.png)

So not all the rows after the second row， all the rows after the first two rows。

 which means the second row onwards。

![](img/a35a8cd140052c25b68a637ef74e6e63_31.png)

Okay， so now you can also take non consecutive sections。



![](img/a35a8cd140052c25b68a637ef74e6e63_33.png)

So。Basically， if instead of like a particular single value or colon。

 if you want to get only the first and the third row， then youll provide a list of indices。

 so here is zero comma 2 in that row。

![](img/a35a8cd140052c25b68a637ef74e6e63_35.png)

And we are saying we're giving the colon here， so that means you want all the columns。

 so we get the row0 and row true from the matrix here。



![](img/a35a8cd140052c25b68a637ef74e6e63_37.png)

Okay。So that's like about sort of slicing if you want to find the actual size of our array。



![](img/a35a8cd140052c25b68a637ef74e6e63_39.png)

We use dot shape right it prints like the size of R and then it returns basically a tuple in Python with because over 2D array it will return as a tu of size 2 and the first element in that is going to be the number of rows and the second element is going to be the number of columns。



![](img/a35a8cd140052c25b68a637ef74e6e63_41.png)

Allright。O。

![](img/a35a8cd140052c25b68a637ef74e6e63_43.png)

So now let's look at the difference between Ny vectors and Ny arrays All so the basic one line difference is that vectors are just one dimensional al right and so that means they basically kind of index differently with this example that we were checking above was talking about a Ny array。

 not a nuy vector。

![](img/a35a8cd140052c25b68a637ef74e6e63_45.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_46.png)

So x， we've declared an nu array here as follows， which is a 4 by 4 nu array。



![](img/a35a8cd140052c25b68a637ef74e6e63_48.png)

And now what I' am taking is y， which is x0 kara colon。

 which means that we are taking the zero width row and all the column values basically so basically this is just pointing to the0 row of our numbere likewise y1 is our zero width column。

As you can see， we've printed x， which is the entire matrix here we've printed y。

 which is just the first row and y1， which is just the entire the first column and as you can see like。

Y is sort of one dimensional right so if we want to make basically there' is no concept of a row or essentially there is like node separate rows in columns here there is only like one essentially because y and y1 both are vectors there is no sort of concept of retaining which was a row which was a column because like the way you look at it here both of them just look like 1 d vector。



![](img/a35a8cd140052c25b68a637ef74e6e63_50.png)

So what we do is we are just going to just go ahead and reshape this y2。

 so reshape function basically allows you to specify as a single argument。

 the shape that you want to reshape it into。😊。

![](img/a35a8cd140052c25b68a637ef74e6e63_52.png)

IWe get into a few examples about this later， so we basically reshaped it and now if you look at y shape。

 y is still a vector。😊。

![](img/a35a8cd140052c25b68a637ef74e6e63_54.png)

But y2 is now a nu array which has one row and four columns allright so if you try to transpose y that' is not going to change anything。

 but if you try to transpose y2 it has sort of changed the way y2 looks it doesn't change the way y looks but y2 dot t the output of that is how is this。



![](img/a35a8cd140052c25b68a637ef74e6e63_56.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_57.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_58.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_59.png)

嗯。Now let us look at some useful Nier functions alright。

 so we have z which is a nuier array of size 2 coa 2 and y which is also a nu array of2 coa 2 simple2 cross 2 arrays。



![](img/a35a8cd140052c25b68a637ef74e6e63_61.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_62.png)

So now we initialize。So basically， initialization is the way thatops initialization are the way that you can。



![](img/a35a8cd140052c25b68a637ef74e6e63_64.png)

Sort of declare your matrices so if you do NP。 I it creates an identity matrix in whatever argument you provide here like for example here we've created a four cross4 matrix。

 you can create a matrix and initialize it with just all zeros or all ones so zeros and ones as the example here and again the input here is the shape of the array that you want to output it。



![](img/a35a8cd140052c25b68a637ef74e6e63_66.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_67.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_68.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_69.png)

And then you can use NPR random。Alright by default it chooses a random number between0 and 1 and the first argument again is the shape of the output array that we want so if we are printing random here and we are getting sort of this is our output array which has a random number values initialized。



![](img/a35a8cd140052c25b68a637ef74e6e63_71.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_72.png)

You can also specify a range if you don't want a default range as so。



![](img/a35a8cd140052c25b68a637ef74e6e63_74.png)

嗯。And yeah， here's like， if you want to have like。Uniform basically gives like any sort of float or decimal point value。

 but if you want to get integerious then you use randomant。



![](img/a35a8cd140052c25b68a637ef74e6e63_76.png)

I。嗯。

![](img/a35a8cd140052c25b68a637ef74e6e63_78.png)

Now well talk about reshaping arrays， which I had touched on previously。

Here is a matrix x that we have and reprinting its shape， which is4 comma4。

 we reshape it to two comma 8。 so we say that we wanted to have two rows and eight columns。

 So what it does is it takes the first。

![](img/a35a8cd140052c25b68a637ef74e6e63_80.png)

8 values。 and it puts them into the first row。Right， and then it takes the next eight values， 9。

101112，134 and 1516 and puts that into the second row。

 So now we have sort of two rows and eight columns， as you can see。😊。



![](img/a35a8cd140052c25b68a637ef74e6e63_82.png)

Another way to do it is like if you want to specify how many rows you want。

 but you don't want to specify how many columns because like here it might be a bit tedious for us to sit and count how many elements are they suppose you want to have only one row you want to just put everything in one row So what we do is we specify the number of rows as one which we specified here and then so you can provide one of these arguments like for example。

 here were preparing the column as minus-1。So that means that basically you're telling it doesn't actually make sense for the size of a matrix to be like -1 for one of the dimensions to be -1 right So -1 is basically telling the computer that just figured it out here right So if we so if we're trying to reshape x and we're saying we want one row。

 x has 16 elements。 that means the number of columns has to be 16。So that we have all the values。

 so that's basically what's happening here。

![](img/a35a8cd140052c25b68a637ef74e6e63_84.png)

Again， we have a matrix5， we're printing its shape and we're reshaping it to have four rows and just one column。

 so that's what's happening here。😊。

![](img/a35a8cd140052c25b68a637ef74e6e63_86.png)

Now we can sort of also combine two array array together。

 so theres like two popular ones are8 stack and V stack。



![](img/a35a8cd140052c25b68a637ef74e6e63_88.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_89.png)

Also looking at8 stack first， we consider this 1，2 3，4 and 5，6。

70 these two matrices that we have X and y， which we initialize here。 and then we E stack them。

 So E stack just imagine that H is horizontal。 So basically horizontally putting them together。

So you can see that we've sort of just like imagine like they've just been horizontally and like joined to each other。

 So this is how it。

![](img/a35a8cd140052c25b68a637ef74e6e63_91.png)

Is outputed and v stack basically means we're going to like vertically stack them。

 So when we vertically stack them we sort of we maintain so basically in horizontal stack the number of rows is maintained to be the same but the number of columns is increased but in vertical stack we maintain the number of columns we increase it along the rows direction so thats that。

😊。

![](img/a35a8cd140052c25b68a637ef74e6e63_93.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_94.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_95.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_96.png)

Now， considering like we're working with matrices， we want to be doing some like standard matric matrix operations。



![](img/a35a8cd140052c25b68a637ef74e6e63_98.png)

Simple addition as like shown here， x plus y。So there's two ways to do it， you can do NP。

 add or you can also even use like the plus operator and are both the same and it does evaluate to true。



![](img/a35a8cd140052c25b68a637ef74e6e63_100.png)

Now we subtract them， we can do y minus x for that。



![](img/a35a8cd140052c25b68a637ef74e6e63_102.png)

To multiply by a constant， you suppose a constant C were setting it to4 see if you do c star x。

 so NmpI internally does this thing called broadcasting。Where like。Basically sort of the。

Dimenssions are not exactly matching here， but if you do like this star。

 what it does is it does element element wise multiplication。

 so it will basically broadcast this four to all of the members of the matrix and every single number is multiplied by four。



![](img/a35a8cd140052c25b68a637ef74e6e63_104.png)

If you want to do like a matrix multiplication kind of operation， which is like you know。

 standard matrix multiplication that for example， like that you've probably seen in high school。

 it's demonstrated here。😊。

![](img/a35a8cd140052c25b68a637ef74e6e63_106.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_107.png)

There's two ways to do it NP periodot MaM， or we use the ad operator。



![](img/a35a8cd140052c25b68a637ef74e6e63_109.png)

All right， now we have like element wise multiplication。😊。



![](img/a35a8cd140052c25b68a637ef74e6e63_111.png)

This is different from regular matrix multiplication what it does basically it requires sort of that the shapes are similar or like or they or at least that they can be broadcasted which probably you can get into later but it is the first element here with the first element in x for the second element and sorry my bad the first element in x for the first element in y to output the first element in the output so basically is element wise multiplication。



![](img/a35a8cd140052c25b68a637ef74e6e63_113.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_114.png)

Now considering math mathematical operations， if you do NP at EXP。

 it takes the matrix x and it will apply。The EXP exponent。Operator operation to every single element。

 individually。

![](img/a35a8cd140052c25b68a637ef74e6e63_116.png)

So thats shown here， if you do log， it takes the log of every single element in the matrix individually。



![](img/a35a8cd140052c25b68a637ef74e6e63_118.png)

Now consider like NPPR Ht x comma Y back where we had。😊。



![](img/a35a8cd140052c25b68a637ef74e6e63_120.png)

Declared it earlier。This is just to create like， let me just show it real quick。



![](img/a35a8cd140052c25b68a637ef74e6e63_122.png)

So this is the output of its stack it makes sort of a wider matrix。

 so that's what we just call it Y underscore Df。

![](img/a35a8cd140052c25b68a637ef74e6e63_124.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_125.png)

So what we do with NP dot max。We' are using some indexing slicing here as we had discussed in the beginning of this tutorial。

 so the maximum of the first row if you want get the maximum of the first row we have to extract just the first row of the wide DF so what we do to extract the first row is we take the zeroth index and we take all the columns let me extract our first row and the max。

So NP dot max is going to give us the index。😊，Oh sorryrry， listen。

The NP dot Mac is going to give us the actual maximum value that we have。😊。



![](img/a35a8cd140052c25b68a637ef74e6e63_127.png)

And NPed ag max is going to give us where in the matrix it is present， okay？



![](img/a35a8cd140052c25b68a637ef74e6e63_129.png)

Now， considering like。Max， we can also do the similar thing with min here。

 we're doing the minimum of the second column， so。We look at our second column here。

 our minimum value is 2 and the index is at argument。



![](img/a35a8cd140052c25b68a637ef74e6e63_131.png)

All right。

![](img/a35a8cd140052c25b68a637ef74e6e63_133.png)

嗯。You can also do NP dot maximum between two nu areas， like for example， A and B or two Ns。

And then we call an NPR maximum NPR minimum， and basically it chooses element y is what the maximum and minimum is between them and it outputs that。



![](img/a35a8cd140052c25b68a637ef74e6e63_135.png)

So let's look at the sum functionality of Numpy。Consider this number area that weve defined here if you take axis equal to0。

 what it is basically going to do is it is going to add up all the elements in a single column。😊。

Basically。For every single column。 Alright， so we've added 1，3 and 5 to get 9 here and 2。

4 and 6 to get 12 here。😊，And now， if we provide access equal to one is going to sort of sum across the row。

 So it's going to add all the elements in。In a particular row， we add one and two to get three。

 three and 4 to get seven and five and six to get 11。And sort of。

 that's how you can sort of like essentially take。Somes across different axes。

And if you just do like we don't specify any access， it just sums up all the elements and outputs it。



![](img/a35a8cd140052c25b68a637ef74e6e63_137.png)

And yeah， that's it for this tutorial。

![](img/a35a8cd140052c25b68a637ef74e6e63_139.png)
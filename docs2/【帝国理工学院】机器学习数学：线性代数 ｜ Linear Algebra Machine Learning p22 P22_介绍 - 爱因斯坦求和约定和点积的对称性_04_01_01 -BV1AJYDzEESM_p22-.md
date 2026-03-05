# 【帝国理工学院】机器学习数学：线性代数 ｜ Linear Algebra Machine Learning p22 P22_介绍 - 爱因斯坦求和约定和点积的对称性_04_01_01 -BV1AJYDzEESM_p22-

![](img/0f9f6e28056b60521a61a7a8503f03a9_0.png)

Now， there's an important other way to write matrix transformations down。

 which is called the Einstein Smation Convention。And that writes down what the actual operations are on the elements of a matrix。

 which is useful when you're coding or programming。😊。

It also lets us see something neat about the dot product that I want to show you。

 and it lets us deal with non square matrices。😊，When we started。

 we said that multiplying a matrix by a vector or with another matrix is a process of taking every element in each row in turn。

 multiply it with corresponding element in each column in the other matrix and adding them all up and putting them in place。

 So let's write that down just to make that concrete。 So I'm going to write down a matrix A here。😊。

And I'm going to give it elements。 A' is an N by N matrix， and I'm going to give it elements A 1，1。

 A 2，1， all the way down to A N1。And then a1，2， all the way across to A1 N。

 and then I'll have a22 here， all the way across all the way down until I fill it all in。

 I've got A N N down here。So the first suffix on this matrix。

 or first suffix on all of these elements in the matrix is the row number。

 and the second one is the column number。Now if I want to multiply a by another matrix B。

 and that's also going to be an n by n matrix and that'll have elements B1，1， B1，2。

 across to B1 n and down to B and1 and across to B andN。

 dot dot dot dot dot dot dot dot dot if I multiply this together。

 I'm going to get another matrix which I'll call A B。

And then what I'm going to do is I'm going to take a row of a multiplied by the elements of a column of B and put those in the corresponding place。

 So let's do an example。So if I want element， let's say A B。Element2， three。

I'm going to get that by taking row2 of a multiple by column 3 of B。

 so I'm going to take row2 of a that's going to be a21， a22， and all the others up to A2 n。

And I'm going to multiply it by column 3 of B。 So that's B1，3， B，2，3。All the way to B N3。

And I'm going to add all those up。😊，And Ill have a dot dot dot in between。

So that's going to be this element， row2 column3 of AB。😊，Now， in Einstein's convention。

 what you do is you say， well， okay， this is the sum。Over some elements J of AI J， B，J K。

 where so if I add these up over all the possible Js， I'm going to get a1，1， B1，1 plus a1，2， B2。

1 and so on and so on and that's for I and K is 1， I'm going to then go around all the possible Is and Ks。

 so while Einstein then says， is he then says， well okay。

 if I've got a repeated index I won't bother with this sum and I'll just write that down as being AI J。

 BJK and that's equal to the product， A B， IK。So A B， IK is equal to AI 1， B1 k plus AI 2。

 B2 k plus A1 sorry I3， B3K and so on and so on。Until you've done all the possible Js。

 and then you do that for all the possible Is and ks。

 and that will give you your whole matrix for AB for the product。 Now， this is quite nice。

 if you are coding， you just run three loops over IJ and K and then use an accumulator on the J's here to find the elements of the product matrix AB。

 So the summation convention gives you a quick way of coding up these sorts of operations。

 Now we haven't talked about this so far。 but now we can see it。

 there's no reason so long as the matrices have the same number of entries in J。

 so we can't multiply them together， even if they're not the same shape。

 so we could multiply a two by three matrix， something with two rows and three columns。😊，So one，2，3。

1，2，3 by a three by four matrix。3 there and 4 there。 So it's got 1，2，3， four times。

And when I multiply those together， I'm going to go that row times that column。

 I've got the same number of js in each case。 So and then I'm going to be able to do that for all of the possible columns。

 So I'm going to get something with four columns。 And when I'm going to be able to do that for the two rows here。

 I'm going to be able to do that row times that one， I'm going to get a two by four matrix out。

 So it's going to have 1，2，3，4，1，2，3，4。 So I can multiply together these non square matrices if I want to。

 and I'll get in the general case， some other non square matrix。

 I'm going to have the number of rows of the one on the left and the number of columns of the one on the right。

Now， all sorts of matrix properties that you might want inverses and so on。

 Deminants all start to get messy and mucky。 and you sometimes can't even compute them when you're doing this sort of thing。

 But there are times when you want to do it。 And the Einstein Smation convention makes it very easy to see how you do it and how it's going work as long as you've got the same number of Js。

 you're good， you can multip them together。 Now， let's revisit the dot product in light of the summation convention。

 So if we've got two vectors， let's call them U and V。And we'll say use a column vector。

Having elements UI。And V's another column vector having elements V I。 And when we dot them together。

 what we're doing is we're multiplying U1 by V1， adding U2 V2 all the way up。

 So in the summation convention， that's just U I。V i。Where we repeat over all the I and add。

 but this is just like writing you as a row matrix。😡。

Pushing you over from being a vector to being a matrix with elements， U1。

 U2 all the way up to U N and multiplying it by another matrix。V1， V2， all the way up to VN。

That's the same that matrix multiplication is the same thing as the dot product。

 I just push the U vector over， and then my dot product is just like doing a matrix multiplication。

Which is sort of neat。 So there's some equivalence between a matrix transformation。

 a matrix multiplication and an dot product。 So let's look at that。Now， if I take a unit vector here。

 let's call in U hat with components U1 and U2。And let's imagine what happens if I dot him with the axis vectors。

 So if I've got an axis here， E1 hat， which would be 1，0。And I've got another axis here， E2 hat。

Which will be 01。Now， let's think about what happens when I dot U hat with E1。

 when I do the projection of U hat onto E1。 So when I drop U hat down onto the axis here。

When I do the projection of U hatt onto E1， I'm going to get a length here， just of U1。

 just of the X axis element of Uha。Now what happens if I drop project E1 onto U hat？Well。

 I'm then gonna get。This projection。And'mre going to get a length here， this projected length here。

Now， the fun thing is we can actually draw a line of symmetry here。😊。

Through these two projections where they cross。And this little triangle and this little triangle are actually the same you can go and do a bit of geometry and prove to yourself that that's true。

 so this length here， this projection，😊，There， that projection is the same length as that projection。

 which is implied by the dot product。 If I dot E1 with U hat， when I do this multiplication here。

 it's symmetric， I can flip around， and I get the same answer。

 So this shows geometrically why that's true。And if we repeat this with the other axes with E2 here and any other axes there are。

 and we'll also get the same results。 So this is why the projection is symmetric and the dot product is symmetric and why projection is the dot product。

 So there's this connection between this numerical thing。

 matrix multiplication and this geometric thing projection which is quite quite beautiful and mindblowing really。

 And that's why we talk about a matrix multiplication with a vector as being the projection of that vector onto the vectors composing the matrix。

 the columns of the matrix。😊，So what we've done in this video is look at the summation convention。

 which is a compact and computationally useful but not very visual way to write down matrix operations and that's opened up looking at funny shaped matrices and that's opened up reexamining the dot product here so that's really nice。

😊。
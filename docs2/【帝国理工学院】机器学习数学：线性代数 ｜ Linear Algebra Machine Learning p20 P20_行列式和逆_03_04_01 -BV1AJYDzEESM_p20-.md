# 【帝国理工学院】机器学习数学：线性代数 ｜ Linear Algebra Machine Learning p20 P20_行列式和逆_03_04_01 -BV1AJYDzEESM_p20-

![](img/48fc0f29b7880dbd332cf4cb0bdfd427_0.png)

In the final video in this module， we're going to look at a property of a matrix called the determinant and what happens when the matrix doesn't have linearly independent basis factors picking up on the basis factors we looked at in the last module。

😊，Let's go back and look at a simple matrix like A nor n D。😊。

What this matrix does is its scale space。 So if we have our original basis vector。

 E1 hat and E 2 hat， it scales them out by a factor of a in this direction to a n。

And by a factor of D in this direction to n D。 And we call those E1 prime and E2 prime。

Now see what I've done to the space。 It was originally this size， one by one。

 And what I've done is I've scaled the space， every vector in the space by a factor of a this way and by a factor of D this way。

 and therefore， I've scaled the space by a factor by of AD D。 all areas in the space。

 Everything's got bigger by a factor of A D。 And I call that the determinant。

Of the transformation matrix。Now， if I instead have a matrix， which is。A n B， D， instead。

 the same but with a B。 What that does is。E1 hat。Stays as it was。 It's scaled by a factor of a。

 but E2 hat goes somewhere different so。E1 hat goes to a nt。But E2 goes to BD somewhere like this。

Beiddi。Now， see what's happened to the space。 I've gone from being something like this to being something like this。

 I've made a parallelogram， but the area of the parallelgram is still AD D。

 It's its base times its perpendicular height， so the determinant is still AD D of this transformation matrix。

Now， if I have a general matrix， ABD， and it turns the original unit square into a parallelogram like this。

 it moves this vector to here， this vector to here。Then to find the area of this parallel teleogram。

 I'm going to have to do a bit of maths。 So I'm going to do that。

 and then we'll have a look at it in a moment。 So I've done the maths and it's here。

 and you can do the geometry and puzzle it out for yourself and pause it if you' like to verify that I'm correct。

 But the area of the parallel telegram here is actually a D minus B。

 And I'm going to denote the operation of finding that area with vertical lines like this and then call that finding the determinant of a。

😊，Which you probably saw in the school。Now in school， when you looked at matrices。

 you probably saw that you could find the inverse of a matrix like ABCD by flipping the terms on the leading diagonal。

And taking the minus of the off diagonal terms for a two by two。So let's do that and see what we get。

 So when we multiply that out， we get A D minus B。😊，Ining， then on the this。

 this element here is a minus B minus plus B， A。 And so we've got a minus B plus B， A。 So that's 0。

When we do this term， we get C， D minus C D。 and when we do this term here， we get C。

 B times minus B。 So that's minus B plus A D。 So that's A D minus B。 interesting。

 So that's the determinant。 So if I multiply by1 over the determinant， A D minus B。

 Then these terms will become1。And I'll get the identity matrix。

 So if this was the matrix A and I think of this and this together as being a to the -1。

Then I've got this is， in fact， when I pre multiply by one over the determinant is， in fact。

 the inverse of a。 So we proved here that that determinant that inverse you learned in school is。

 in fact， correct。 But the interesting thing is that this determinant there。

 this amount that it scales space。 if we then take this matrix。 when we do the flipping around。

 We haven't changed it scaling of space。 we need to undo that scaling and bring it back down to a scale of one。

 So the determinant here is what we need to divide the inverse matrix by in order for the it to properly be an inverse。

😊，Now we could spend another video looking at the extension of the idea of R echelon form to find out how to find determinants in the general case computationally。

 but this is both tricky to show and it's kind of pointless knowing how to do the operations isn't a useful skill anymore because we just type debt。

😊，A into our computer。And Python MAlab will do it for us from a learning perspective。

 it doesn't add much to R echelon， R echelon does actually， which is why we went through it。😊。

I'm I'm going to teach you how to find determinants in the general case if you want to know look up QR decomposition。

😡，And then follow that through。 And that's how computation that you go and find it out or in a linear algebrabook textbook is the other place to look。

 That's how you do it in the general case。Now， let's think about this matrix A here。

 It transforms E1 and E2 hat。To，2 points on the same line。 It transforms E1 hat to 1，1。

 and it transforms E 2 hat from there over to 2，2。 And they're both points on the same line。

They're just a multiple of each other。 They're not linearly independent。 What this matrix， in fact。

 does is it transforms every point of space on a line。

 and notice that the deter of that matrix is going to be 0。 If I take A D minus B。

 C determinant of a。Is naught because the area of any area has gone onto a line。 And therefore。

 that area is naught。 So however you compute it either geometrically or computationally。

 you get a determinant of naught。So if I had a3 by3 matrix with a similar situation describing a 3D space and if I had the same position where one of the new basis vectors was just a linear multiple of the other two。

 it wasn't linearly independent， then that would mean the new space was either a plane or if there was only one independent basis vector a line like we have here。

 In either case， the volume enclo would be 0。 So the determinant would be0。😊。

Now let's turn back to our row echelon form and apply that idea。😡。

Let's take this set of simultaneous equations。 sayy you can see that the third row is just the sum of the first two。

 So row 3 is equal to row 1。Plus O2。And you can see that column3。Its just given by two of column one。

Plus， column 2。If you want to pause for a moment to verify that， but it really is true。

This transformation matrix doesn't describe three independent basis factors。

 One of them is linear independent on the other two。So this doesn't describe a new 3D space。

 It collapses into a 2D space。So let's see what happens when I try to reduce this to rowashchelon form。

 If I take off the first row from the second。 Okay， so far so good。

 I've got that and my ABC stays the same。 and I take the first one off the second one I've got 12。

 take 12 of 17， I've got 5。 If I then take the first and second ones off the third one。

 I've now got zeros everywhere here。 And if I do that on here。 I take 12 and 17 or 29 get0 here。

 So now I've got 0 C equals 0， which is sort of true， but not useful。

 Now an infinite number of solutions for C in effect。 any value of C would work。

 So now I can't solve my system of equations anymore。 I don't have enough information。😊。

So if we're thinking about this from a sort of solving simultaneous equations point of view。

 my mistake was when I went into the shop to buy apples and bananas and carrots。

 the third time I went in， I just ordered a copy of my first two orders。

 so I didn't get any new information and I don't have enough data therefore to find out the solution for how much an individual apples and bananas and carrots costs。

😊，So what we've shown is that where the basis factors describing the matrix aren't linear and independent。

 then the determinant is zero， and that means I can't solve the system of simultaneous equations anymore。

😊，Which means I can't invert the matrix because I can't take one over the determinant either。

 And that means I'm stuck。 This matrix has no inverse。

So there are situations where I might want to do a transformation that collapses the number of dimensions in a space。

 but that will come at a cost。Another way of looking at this is that the inverse matrix lets me undo my transformation。

 It lets me get from the new vectors to the original vectors。

 And if I've dumped a dimension by turning a 2D space into a line， I can't undo that anymore。

 I don't have enough information because I've lost some of it during the transformation。

 I've lost that extra dimension。😊，So in general， it's worth checking before you propose a new basis vector set and then use a matrix to transform your data vectors that this is a transformation you can undo by checking that the new basis vectors are linear independent。

😊，So what we've done in this last video in this module is look at the determinant。

 how much we grow space。 We've also looked at the special case where the determinant is0。

 which means that the basis factors aren't li independent， which means the inverse doesn't exist。

In this first moduleular matrices， what we've done so far is define what a matrix is as something that transforms space。

 We've looked at different archetypes of matrices， like rotations and inverses and stretches and shears and how to combine them by doing successive transformations。

😊，Then we've looked at how to solve systems of linear equations by elimination and how to find inverses。

 and then finally we've looked at determinants of linear independence。😊。



![](img/48fc0f29b7880dbd332cf4cb0bdfd427_2.png)

![](img/48fc0f29b7880dbd332cf4cb0bdfd427_3.png)
# 【帝国理工学院】机器学习数学：线性代数 ｜ Linear Algebra Machine Learning p19 P19_从高斯消元法到求逆矩阵_03_03_02 -BV1AJYDzEESM_p19-

![](img/6848ea469c91b85406311da1aa82d6ae_0.png)

Now， let's think about how I can apply this idea of elimination to find the inverse matrix。

 which solves the more general problem， no matter what vector I write down on the right hand side。

 So have a3 by3 matrix a。And it's inverse B， which are multiplied together to give the identity matrix I。

 So before we had the matrix for a was 1，1，3，1，2，4， and 1，1，2。And B here is， is。

 I'm going actually introduce some notation。 I'm going to call B。Composive elements， B1，1， B12， B1，3。

 where the first digit represents the row。So then I'll have B2，1。

 and the second digit represents the column。 So this would then be B2，2。

 and this one would be B row 2， column 3。 I'll have B3，1， B3，2， B3，3。 So that is， that's the row。

And that's the column。equals I。What we're saying here is that B is actually the inverse of a。

 So that is if I multiply a by its inverse。 I'll get the identity。

 And actually the inverse is special because I can do it either way round。

 I can apply it to A on the right or on the left and it'll still work because I times the inverse of a is just the inverse of a。

 So it doesn't really matter which way round I do it。

 So but I'm just doing it here so that I've got some bs to play with。

 and I don't get confused with my A's and my Bs。 But for this example。

 I'm saying B is the inverse matrix of a。 Now， notice that this first column of B here is just a vector。

 it's a vector that describes what the B matrix。 the inverse of a does to space。 actually。

 it's the transformation that that vector does to the first the X axis if you like。So。

 and the identity matrix is just 1，0，0，0，1，0，0，0，1， right。So I could write this down。

 I could write down this a。That big square guy times B 1，1， B2，1， B，3，1。

And I would get just the first column of the identity matrix 1，0，0。Now。

 I could solve that by my elimination method and back substitution just in the way I did before。

 except I'll be juggling different numbers here。Then I could do it again for the second column of B。

 the second vector of B， for the second vector of the identity matrix。

 And I could do it again for the third one。 So I'd be doing that in some series， if you like。

 But here's the fun bit。 I could do it all at once。

So I'm going to do this process of elimination and back substitution。All at once。

I'm gonna do it for all the columns on the right hand side， simultaneously。

So if I take the first row here。And I take it off the second row。 As before。

 I'm gonna get rid of this one。And if I take the first row off of the third row。

 I'm gonna get rid of both this one and this one。So if I've got， put the unaltered ones down here。1。

1，3。 If I take that off of the second row， I'm gonna get 0，1，1。 And if I take that off the third row。

 I'm gonna get 0，0-1。So on the right hand side， I'm gonna have the unaltered one。Is 1，0，0。

And I've taken that off of the second row。 So I've got taken one off that。 That's -1。1，0。

 And I've taken out off of the third row as well。 So I've got -1，0，1。And， so， now。

I can multiply that third row through by -1。 And that's in the form I then want while I've got ones on the leading diggal and zeros below it。

So I multiply that through by -1， I'm going to plus there。On a minus there。Now。

 I can substitute that third row back into the second and first rows so I can take one of it off of the second row。

And I can take three of it off the first row。 So now the unalar one is the bottom one。1 oh-1。

If I take one of those off of the second row， then I've got。0，1，0 there。

 I'm gonna take that off of the second row over here。 So if take one off of -1， I get -2。

 take 0 off 1。 I've got1。 take -1 off of 0。 I've got。 I'm effectively adding one。

Then I want to do that again to the first row。 I want to take three of them off to make this guy here 0。

 So I've got then 1，1，0 there。And I want to take three of these off of the first row。

 So I take three off of one， gives me-2。Take0 off there。 And I've got to take three of -1 off 0。

 So that gives me plus 3。So we're nearly there。 I've just got this irritating one here。

 I'm got to take this row off this row， and I'll be home。So if I take my third rows un'altered。

put some brackets in。My third row is unaltered。 my second row is gonna be unaltered。1，0-1，1-2，1，1。

I take that row off of that row。 Then that altered one gives me。1，0，0。 Take the one off there。

 Take this row off of this row，-2 off of -2。 I've got to take-2。Off of -2。 So that gives me 0。

I' gotta take one off 0。 that gives me -1。 And I've gotta get to take one off3， which gives me 2。

So that's my answer。 So now I've got the identity matrix here。For A， in effect。

 I've transformed a till it's the identity matrix。I've got my B matrix。

 which I haven't really changed。 And my identity matrix over here， I've changed。

 So now I've got our identity times a B matrix is equal to this guy。

 So the identity times something is just itself。 So this is， in fact。

My answer for the inverse of A or B。So I've found a way here to find the inverse of a matrix just by doing my row elimination and then my back substitution。

Which is really cool。So what we've done is we found an inverse matrix A to the -1 here。

 And if we multiply a。Times 8， the -1。Or get the identity and prove yourself， if you like。

 just pause for a moment and have a go at doing that for yourself and verify that that times that does。

 in fact， give you the identity matrix。And in school， you probably did this a different way。

 but computationally， this way is much easier， particularly when you come to higher dimensions。

 you know，100 rows and columns or something like that。

There are computationally faster method of doing what's called a decomposition process。

And in practice， what you do in any program that you write is you simply call the solver for your problem or the function something like in。

A。Or whatever it is， and it will pick the best method by inspecting the matrix you give it and return the answer。

 But the point here is to show how these problems are actually solved in a computer and also will observe some of the properties of these methods in different circumstances that will affect the sorts of things we want to do when solving these sorts of problems。

So what we've done here is figured out how to solve both sets of linear equations in the general case by a procedure we can implement a computer really easily。

 and we've made that general by finding a general method to find the inverse of a matrix in the general case for whatever is on the right hand side of our system of equations and hopefully that's really satisfying and really nice。

😊。
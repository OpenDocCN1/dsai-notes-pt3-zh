# 【帝国理工学院】机器学习数学：线性代数 ｜ Linear Algebra Machine Learning p18 P18_解决苹果和香蕉问题 - 高斯消元法_03_03_01 -BV1AJYDzEESM_p18-

![](img/ef19f32cc52d3fe32321bd7e0c0aa865_0.png)

So now we're finally going to find a way to solve the apples and bananas problem， and along the way。

 we're going to find out about a thing called the inversea matrix and a method for finding it。

So let's go back to the apples bananas problem。 We said that I walked into a shop and I bought  two apples and 3 bananas。

 and that that cost 8 ors or whatever my currency is。 And I went to shop on another day。

 and I buy 10 apples and 1 banana。 And I got charged 13 for that。

 So I wrote that down as a matrix times a vector。And I could call that matrix A。

 and I could call this vector R， and I could call that output vector S。

 So a operates on R and gives me S。And what I want to do is I want to find out what R is what this vector A B is in order to give me the right numbers for the output vector。

Now， let's just think about this matrix A for a moment。 Let's see if I can think of another matrix。

 I'm going to call this matrix a to the -1 that when I multiply it by a gives me the identity matrix。

 and I call this matrix here， the inverse of a。😊，Because what it does to a is it exactly reverses whatever a does and gives me just the identity。

 So if I take this equation， A R equals S。 if I multiply it on the left by a to the minus-1 on both sides。

 Well what I find is is that this is just going to be the identity which is the matrix that does nothing。

 So where I'm multiply the identity by R I just get R。

 So then I've got R is equal to a to the minus1 times s。 the inverse matrix of a times S。

 So if I can find the inverse of a， the matrix where multiplied by a that gives me the inverse。

 I can find the inverse of a， I can solve my problem and I can find what my A and Br and I've solved my apples and bananas problem。

😊，Now， hold that thought about inverses for just a moment。

 So we said the inverse of a times a was the identity matrix。

 And we'll just part that up there for a moment。Now。

 I actually don't have to go all the way to the universeverse to solve the apples in anars problem。

 I can do it just by substitutions。 So let's look at a slightly more complicated problem and see what I mean。

 So I'm going to take a matrix that looks like like this，11，3。😊，1，2，4，1，1，2。

And I'm going to say that I have apples and bananas and carrots。 say， okay， they're not a fruit。

 but they're another sort of fruit like object that we eat。

 And so I'm saying that I bought one apple，1 banana and 3 carrots。 And that cost me， let's say 15。

 Another day I went in， I bought 1，2 and 4。 And that cost me 21。 And another day， I bought 1，1 and 2。

 And that cost me 13。Now， the thing to notice about a system of equations like this is that I can。

 if I take this row off of another row， I haven't changed anything， right， So I know that an apple。

 a banana and three carrots costs 15。 So if I take an apple。

 a banana and three carrots and 15 off of the next row。

 I haven't changed anything really about that row。The same for the third row。

 So I can make this problem simpler by going and doing that。 That's sort of a process of elimination。

 So if I take， if I call this row 1 row 2 and row 3， if I take row 1 off of row 2。

Then I would have take vote 1 off of vote 2。 I'll have 0，1，1。If I take row 1 off of row 3。

 I'll have 0，0 and -1。I still have A， B， and C。I've taken on the right hand side。 I've taken row 1。

 I've taken row 1 off of row 2。 I've taken 15 off of 21。 So I' have6 left。

 I've taken row 1 off of row 3。 So I'll have 15-13 is 13-15， is-2。So， interesting。

 So now I can see that actually minus C is equal to -2。

 So I can multiply that row through by  -1 here。 I'll just change pens。

And I've got a solution now for C， that C is equal to 2。So that's interesting。😊，Now。

 I've got what it's called a triangular matrix。 That is everything below the body diagonal is 0。

 And that's a very interesting sort of matrix。 I've reduced it to what's called echelon form。

All the numbers below the leading diagonal is 0。Now， I can do what's called back substitution。

 I can take my answer for C here， and I can put my answer for C back into the first two rows。

 So if I take one C equals 2， I know that one times C here is2 here。 So I can take that off there。

 and I can do the same， I can take three times that off of the first row。

 So if I go take three times it off the first row。 I'm going to get 1，1，0。ABc。

And I've taken three times the first row off of here。 So I've taken three twos off of here。

 so I'm going to get9。And if I take that third row off of the second row， I'm gonna get 0，1，0。

 And I've got two off 6 is 4。And I can complete。 I haven't changed the last row at all。

So now I know that C here is equal to 2。 I know that if I multip that row by that column。

 I've got just B is equal to 4， and I've got a plus B is equal to 9。

 but I can take my answer for B back off this first row。 So I've got then 1，0，0。0，1，0，0，0，1。ABc。

And I've taken 1， B。 I've taken four off the first row。 So that's 5。Fii。

So my solution here for my apples， bananas and carrots problem is that apples cost 5s。

 Bans cost 4s and carrots cost 2。 And that's solved the problem for me。 Very nice。

 So I didn't really have to compute the inverse at all。

But I've only found out the answer for this specific set of this specific output vector。

 So we said that this was a times R is equal to S。 I've only found it for this specific S。

If I did the inverse in a general case， I could do it for any S。 I could find R for any S。

So what I've done here is I've done what's first elimination。I've taken multiples of rows。

 and I've taken them off of each other to get to having a triangular form where the bottom corner here is zeros。

 And I've just got ones on the leading diagonal。And then I've done back substitution。😡，Back。

Substitution。I've gone back up of putting the numbers for C back into the first two rows。

 the number for B back into the first row and so on to get my solution to my problem。

 And that's very nice。 This is actually one of the most computationally efficient ways to solve this problem and it's going to work every time。

 and it's very simple to understand。 and we can do it in relatively for your operations。

 So it's really， really nice。And one thing to notice here is that in doing so。

 What I've done is I've transformed a into the identity matrix here。

 This is just the identity matrix。 This one's on the league of diagonals and 0 is everywhere else。

 So this is going to be a key to a way to find the inverse， which is what we'll look at next。😊。



![](img/ef19f32cc52d3fe32321bd7e0c0aa865_2.png)
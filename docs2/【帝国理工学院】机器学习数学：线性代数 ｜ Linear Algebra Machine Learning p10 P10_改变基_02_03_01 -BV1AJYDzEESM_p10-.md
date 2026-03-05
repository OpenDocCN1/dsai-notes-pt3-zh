# 【帝国理工学院】机器学习数学：线性代数 ｜ Linear Algebra Machine Learning p10 P10_改变基_02_03_01 -BV1AJYDzEESM_p10-

![](img/fe9cc8a6d683cdd599dfa85a675929e2_0.png)

Now， so far， we haven't really talked about the coordinate system of our vector space。

 the coordinates in which all our vectors exist。 But it turns out that in doing this thing of projecting of taking the dot product。

 we're projecting our vector onto one， which we might use as part of a new definition of the coordinate system。

 So in this video， we'll look at what we mean by our coordinate system。

 And then we'll do a few case of changing from one coordinate system to another。

 So remember that a vector like this guy R here with just an object that takes us from the origin in to some point in space。

 which could be some physical space， there could be some space of data like bedrooms and thousands of years for the house or something like that。



![](img/fe9cc8a6d683cdd599dfa85a675929e2_2.png)

What we haven't talked about so far really is the coordinate system that we use to describe space so we could use a coordinate system defined by these two vectors here。

 I't any of them names， we call them IMJ before， I'm going to give them names E1 and E2。

I'm going to define to be of unit length， so I'm going to give them a little hat。

 meaning they're of unit length。😊，And I'm going to define them to be the vectors 1，0。N 0，1。

And if I had more dimensions in my space， I could have E 3 hat， E 4， Ha， E 5 Ha， E million hat。

 whatever。 here。 The instruction then is that R。Is going to be equal to doing a vector to sum of two E1s or three E1s and then some number of E2。

 So we'll call it doing3 E1s hats plus 4 E2 hats。 And so we'll write it down as a little list，3，4。

So I is the 34 here is the instruction to do three E1 hats plus four E2 hats。

But if you think about it， my choice of E1 hat and E2 hat here is kind of arbitrary。

 It depends entirely on the way I set up the coordinate system。

 There's no reason I couldn't have set up some coordinate system but some angle to that or even used vectors to find the axes that weren't even at 90 degrees to each other were of different lengths。

 I could still have described our as being some of some vectors I used to define the space。

So I could have， say， another set of vectors B。And I'll call B1 here in the vector 21。

 and I could have another vector here， B2 as the vector minus-2，4。And I've defined it in terms of。

The coordinates E， and I could then describe R in terms of you you're using those vectors B1 and B2。

 It's just the numbers in R would be different。So we call the vectors we use to define the space。

 these guys E or these guys B。 We call them basis vectors。

 So the numbers I've used to define are only have any meaning when I know about the basis vectors。

 So R referred to these basis vectors E is 3，4， But R referred to the basis vectors B also exists。

We just don't know what the numbers are yet。 So this should be kind of amazing。

 The vector has some existence in a deep sort of mathematical sense。

 completely independently of the coordinate system we use to describe the numbers in the list describing the vector that takes us from there from the origin into there still exist independently of the numbers used in her。

 which is kind of neat right， sort of fundamentally sort of idea。 now。😊，If the new basis factors。

 these guys B are at 90 degrees to each other， then it turns out the projection product has a nice application。

We can use the projection or dot product to find out the numbers for R in the new basis。B。

 so long as we know what the B's are in terms of E。 So here I've described B1 as being 2。

1 as being E 1 plus E 2 E twice E1 plus 1， E 2。And I've described B2 as being minus2 E1s plus4 E2s。

And if I know B in terms of E， I'm going to be able to do use the projection product to find are described in terms of the B's。

But this is a big if。 The B1 and B2 have to be at 90 degrees to each other。 If they're not。

 we end up being in big trouble and need matrices to do what's called a transformation of axes from the E to the B set of basis factors。

 We'll look at matrices later。 But this will help us out a lot for now。

Using dot products in this special case， where the new basis factors are orthogonal to each other is computation a lot faster and easier。

 It's just less generic。But if you can arrange the new axis orthothgonal， you should。

cause it makes the computations much faster and easier to do。

So you can see that if I project are down on to B1。

I look down from here and project down at 90 degrees。 I get a length here for the scalar product。

 And that scalar projection is the shadow of R to B1。

 And the a number of the scalar projection describes how much of this vector I need。

 and the vector projection is gonna actually give me a vector in the direction of B1 of length equal to that projection。

Now， if I take the vector projection of R onto B2 going this way。

 I'm going to get a vector in the direction of B2 of length equal to that projection。

And if I do a vector sum of that vector projection plus this guy's vector projection。

 I'll just get R。 So if I can do those two vector projections。And add up there vector sum。

 I'll then have RB being the numbers in those two vector projections。

And so I found how to get from R in the E set of basis vectors to the B set of basis vectors。 Now。

 how do I check that these two new basis factors are at 90 degrees to each other。

 I just take the dot product。 So we said before the dot product Ca Theta was equal to the dot of two vectors together。

 So B1 and B2 divided by their length。So。If B1 dot B2 is 0， then cause theta 0 and cause theta 0。

 If they're at 90 degrees to each other If they're orthogonal。

 So I don't even need to calculate thanks。 I'll just calculate the dot product。 So B1 dot B2。

Here I take two times -2。And I add it to1 times 4。Which is -4 plus 4， which is 0。

 So these two vectors are at 90 degrees to each other。 So it's going to be safe to do the projection。

So having talked through it， let's now do it numerically。So if I wan to know what are。

Described in the basis， E。An ours pink， right。If I take R in the basis E， and I'm gonna dot him。With。

B1。And the vector projection divides by the length of B1 squared。

So R in e dotted with B1 is going to be。3。Times 2。Plus， four times 1。4our times 1。

Divided by the length of B1 squared。 So that's the sum of the squares of the components of B。

So that's 2 squared plus one squared。 So that gives me 6 plus 4 is 10 divided by 5， which is 2。

So this projection here is of length two times B1。 so that projection there， that vector。

Is going to be2 times B1。So that is， in terms of the original set of vectors B， original vectors E。

 R dot B1 over B1 squared times B1。Is the vector2 is two times the vector 2 1。Is the vector 4，2。

And I can do then now this projection onto E2 so I can do。R E。Dotted。With B2。And divide by B。

 the length of B2 squared。And R dot B2 it's three times minus2。Plus 4 times 4。

Divided by the length of B2 squared， which is-2 squared plus 4 squared。So that' 3 times -2 is 6。

-6 plus 4 times 4 is 16。 so that a -6 plus 16 is 10。

Divided by this length here is four squared is 16，2 squared is 4。 So 20。 So that's equal to a half。

So this vector projection here is that guy times B 2 so thats。

R E dot B2 over the modulus of B2 squared。 That's my half times the vector B2。

 So that's a half times the vector B2 to -2，4。Now， if I add those two together4， two this bit。

 that vector projection。Plus， this vector projection。

 So this guy is going to be a half B2 plus half-2，4 is-1，2。 If I add those together， I've got 3，4。

Which is just my original vector R 3，4 in the basis E。 So in the basis of B1 and B2， R。

 B is going be。2， a half。Very nice。2 a half。 So actually in the basis B， it's gonna be2 a half there。

So our B is two times B1 plus a half times B2。 very nice。

 So I've converted from the E set of basis vectors to the B set of basis vectors， which is very neat。

 just using a couple of dot products。😊，So this is really handy。 This is really cool。

 We've seen that our vector describing our data isn't tied to the axes that we originally used to describe it at all。

 We can red describescribe it using some other axes， some other basis vectors。😊。

So the basis factors we used to describe the space of data。

And choosing them carefully to help us solve our problem will be a very important thing in any algebra。

 And in general。And what we've seen is we can move the， the numbers in the vector。

 we used to describe a data item from one basis to another。

We can do that change just by taking the do or projection product。

In the case where the new basis factors are orthogonal to each other。


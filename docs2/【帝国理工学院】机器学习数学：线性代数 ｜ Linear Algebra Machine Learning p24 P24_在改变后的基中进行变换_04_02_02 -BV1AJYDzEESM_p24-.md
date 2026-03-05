# 【帝国理工学院】机器学习数学：线性代数 ｜ Linear Algebra Machine Learning p24 P24_在改变后的基中进行变换_04_02_02 -BV1AJYDzEESM_p24-

![](img/9e11d289546706015830349f0ec15b28_0.png)

Now， let's look at how we do the transformation of a vector that's already in a change basis。

 Last time we looked at bears basis。 Bears basis had a first axis of 3，1 and a second axis of 1，1。

And let's say I have a vector X， Y。😊，Dfined in bears basis。

 And so I want to transform it by doing something like a rotation of 45 degrees。But the problem is。

 I don't know how to write a 45 degree rotation in Bear's funny coordinate system。

 I only know how to write down a 45 degree rotation in my normal 1，0，01 system。 So in my system。

 which is 10。Iwan。A 45 degree rotation rotates 10 up like that。 So it becomes。

 if it's still a unit vector 1 over root 2，1 over root 2， that is a normalized 1，1。

 and it takes01 round。2-1 over route2，1 over route2。That is that 45 degrees there。

 that 45 degrees there。 So I can write down the rotation in my notation。

Let's call it R being a 45 degree rotation as being one over root 2 times 1，1 minus11。

 That's what a 45 degree rotation is in my world。So what I need to do is first transform the vector X Y into my basis。

 and I do that by multiplying it by B，Then I can apply my nice sensible rotation R to that vector that's now in my basis。

 So what I get here when I do R B， I've got the vector。In my。Cordinate phone。Now。

 the problem is bear doesn't care about my world。 He wants to get the rotation in his basis。

 So then I have to transform the resulting vector back into bear's basis。

 And I do that by applying B to the -1 and B to the -1。

 I get by flipping the terms on the leading diagonal。

 taking minus the offt aagonal terms and dividing by the determinant here， which is2。

 So I multiply by a half。So that then gives me the vector back。In the vector back in。Bears。

In bears for。So overall， what I've done is I've done B to the -1 times R。Times B。😡。

And what that's giving me is it's giving me the rotation in Bear's coordinate system。

 which is really neat。😊，So now what we have to do is do the sums。 And when we do that。

 RB gives us this and B to the -1 RB gives us this。 I've written them down there。

 So pause and ponder if you want to verify those on your own。

So this is what a 45 degree rotation looks like in Bs coordinate system。

 notice that it's completely different to the one in my standard basis。😊。

It isn't very easy necessarily or obvious to enter it just out of your head。

 You have to do the calculation。So if you want to do some kind of transformation。

 but in some funny basis， this equation B to the minus1 RB is going to be very useful。😊。

To step back here， the point is that if we want to transform to non or form normal coordinate systems。

 then the transformation matrices also change。And we have to be mindful of that。

 And this is the sort of algebra you see all the time。

 We've got the transformation matrix R wrapped around by B。

 B to the -1 that does the translation from my world to the world of the new basis system。

 So thanks a lot， there。 You really helped us out to understand all this stuff。😊。

So what we've done in these two videos is we've looked at how the numbers in a vector change when we change the basis。

 And we thought about the coordinate systems and how to do transformations in non orthogonal coordinate systems。

It's been quite hard work， but this really sets us up。

 for example in principal component analysis to operate in different basis systems。😊。



![](img/9e11d289546706015830349f0ec15b28_2.png)

![](img/9e11d289546706015830349f0ec15b28_3.png)
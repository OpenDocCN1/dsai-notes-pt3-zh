# 【帝国理工学院】机器学习数学：线性代数 ｜ Linear Algebra Machine Learning p16 P16_矩阵变换的类型_03_02_02 -BV1AJYDzEESM_p16-

![](img/2365e861fed9cdf3231c7bf65af60cb7_0.png)

Now， let's look at some special targets of matrices that do simple things。

 and then we'll think about how to combine them to do complicated things。First。

 let's think about a matrix that doesn't change anything。

 a matrix that's just composed of the basis vectors of the space。 So 1，0 and 0，1。

 So that if I multiply it by some vector X， Y。That's not going to change X， Y。 If I multipied it out。

 I'm going to get1 times x plus0 times y，0 times x plus1 times Y， X， Y。

So it doesn't change the vector X， Y， The， it's just composed of the basis vectors here。

And it doesn't change them。 And that's called， therefore。

 the identity matrixes the matrix that does nothing and leaves everything preserved。

And it's called I。Now， what if I have different numbers along the leading diagonal， something like 3。

0，0，2， for instance。Well， that's going to scale the x axis here by a factor of three。

 it's going to go to3 n。When I multiplied out， and the y axis is is gonna scale by a multiple of 2。

 It's gonna go from 0，1 to 0，2。 So I've scaled space this way by a factor of 3 and that way。

 by a factor of 2。 So my little unit square has gone to being a rectangle from being a square originally。

 it's scaled up。This way。Three times。 And this way， two times。And， of course。

 if the scale factor here was a fraction， if it was a third or something。

 then I'd have squished space that way。 Instead， I'd have gone that way and made it thinner and taller。

 something like that。 So a fraction then squishes space。

The next thing to think about is what happens if I've got a matrix where I， I scale by， say， -1 here。

Of what if the axes。 Well， what that's gonna do， said the original axes is it's gonna flip them around。

 So if I've got 1，0 here。And 0，1 being the other axis， of course。

 Then that's gonna scale the first one。Over here to being -10。And of the， the， the 0。

2 is gonna scale the other axis up to 0，2 here。So my original little cube goes from here。To here。

So it's changed in area by a factor of two，1 times2， but it's also flipped over。

 The X axis has gone over there。 Now， what does that mean， Well。

 if I had previously an axis system where I went using my right hand from my right hand there。

 That's my first one。 and that's my second axis around and I went counterclockwise。

 now I'm going the other way now I've got a left hand in coordinate system and I go clockwise。

 So I need to get my left hand out to describe them now。

 So I've changed the sense of the coordinate system。In flipping it over。 Now。

 the other matrix we need to think about， get another pen。Is-1，0，0-1。

And that inverts everything and inverts both axes。 It takes 1，0 to -10， and it takes 0。

1 down here to 0-1。So it flips everything in both coordinates， and that's called an inversion。

 Another matrix I can think of is 0，1，1，0。 That's kind of fun。 What that does is it takes I hat0，1。

0 here。 It takes it to 01， So it takes it to there。😊，01， that guy goes there， and it takes the other。

Access。Which was there。There is also 01。And it takes it to 10。

So what it does is it flips them around。 it's like I've put a mirror in of 45 degrees。

I could have another mirror would be 0，-1，-1，0。And that would take 1，0 here。

 and it would make it 0 minus-1。Take it down there。0-1。 and it would take this axis 0，1。

 and it would make it to-1，0。 so it would make it over there。

So that's like having a mirror plane in there。And just for completeness。

 I can think of another two mirrors， and they would be-1，0，0，1。And that flips the X axis。

 That's like a vertical mirror。 That's that guy。And I can have another one， which would be 1，0，0-1。

And that flips the horizontal axisxe is that flips this guy down， but leaves this guy unchanged。

 So those are all my mirrors。 Another thing I might want to think about is shears。

 So I wanted to keep E1 hat where it was。1，0。But move E2 hat over。 So E2 hat is 0，1。

 So I wanted to move E2 hat over。To hear， say， so I wanted to get me too primed to be equal to 1，1。

 say。Now， in which case， I just to write down my matrix， right， I can say that E1 becomes itself 1，0。

 and E2 becomes 11。 That would be the transformation matrix for that shear。

 It would be shearing the unit square over from being a little square to being a little power allgram here。

 something like that。Of course， I could share the X axis as well。

 I could do some combination of shears。 but that's basically how a shear would look。😊，Now。

 the last sort of shape change I can do after stretches， inversion， mirrors and shears is a rotation。

If I take E1 hat again。An E2 hat。If I rotate them round， well E1 hat's going to go round here。

So E1 primeed is going to be equal to 01。An E2 hat is going to go around to here。

 An E2 primeed is going to become -1，0。So that 90 degree rotation there is gonna have the transformation matrix 0。

1，-1，0。And in general， I can write down a rotation by an angle here， let's say an angle here。A the。

 I can write that down as being cause The sign，Sign The， cause Theta。

 And I need to put a minus sign in here where positive thes are actually that way。

So we did a rotation by 90， so sine of 90 is -1。And that's a general expression for a rotation in 2D。

 If I wanted to do it in 3D， I need to think about the axis I was doing it along around。

 So if I was rotating about Z， I would preserve all of the Zs if for a 3D rotation。

 something like that。But this isn't really， of course。

 about matrix rotations and matrix geometry and so on。 that would be something like crystal。 This。

 of course， about data science。 So we don't need to think too much about rotations。

 but it is interesting if we need to do things like transform faces if we want to do facial recognition。

 We'll want to do these sorts of stretches and mirrors and shears and rotations to faces to get them all facing like that rather than facing like this or some funny angle that we had from our camera that was looking at somebody。

 So we do need to do this in data science on occasion。 and that's rotations。😊。

So what we've described in this video is we've described all the possible sort of changes we can do with a matrix。

 So now we think need to think about how we do a rotation and then a stretch。

 and that's the next little part。
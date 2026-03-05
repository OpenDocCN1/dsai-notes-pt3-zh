# 【帝国理工学院】机器学习数学：线性代数 ｜ Linear Algebra Machine Learning p26 P26_格拉姆-施密特过程_04_04_01 -BV1AJYDzEESM_p26-

![](img/c668cc476cfe605ee4abbe7cbc1e2fb2_0.png)

We've said several times now that life is much easier if we can construct an north normal basis vector set。

 but we haven't talked about how to do it。 So in this video， we'll do that。

 starting from the assumption that we already have some linearly independent vectors that span the space we're interested in。

So let's say I have some vectors V。 and I've got a whole group of them， V1， V2， all the way up to VN。

 and there's enough of them that they span the space。 So let's sort of sketch them out。

 So I've got it， say a V1 here， but V2 over here。Another V3 down there somewhere。

 and they're linearly independent。 Let's assume that if you want to check linear independence。

 you can write down their columns in a matrix and check the determinant isn't zero。

 if they are linearly dependent， one of that would give you a zero determinant。

 but they aren't orthogonal to each other all of unit length。

My life would probably be easier if I could construct some ortho normal basis somehow。

 And there's a process for doing that。 She's called the Graham Schmidt process。

The Graham Schmidt process。Which is what we're going to look at now。

Let's take arbitrarily the first vector in my set， call him V1。😡。

So we take V1 in this first step she， let's call it she actually she gets to survive unscathed。

 so we're just going to normalize her and we're going to say that my eventual first basis factor E is going to be equal to v1 just normalized to be of unit length。

Just divided by that is length。 So E is just going to be some normalized version。Of v1。

And I can now think of V2。As being composed of two things， one is a component。

 and let's do this in orange。A component that's in the direction of E1 like that。

 plus a component that's perpendicular to E1。And。But the component that's in the direction of E1。

 I can find by taking the vector production of V2 onto E1。

 so I can say V2 is equal to the vector projection of V2 onto E1。Dotted together。

 And if I want to get that actually as a vector， I'll have to take E1。 and which is a unit length。

 I'd have to divide by the length of E1。 but the length of E1 is1。 sot forget it。

And if I take that off of V2。😊，Then I'll have this guy and let's call him you， too。

So I can then say that you， too。So plus U2。 So I can then rearrange this and say that u2 is equal to V2 minus this projection V2 dot E1。

Times E1。And if I normalize you too。If I take u to divided by its length。

Then I'll have a unit vector， which is going to be normal2 V1。

 So if I take a normalized version of that， let's say it's that。That will be E2。

And that will be at 90 degrees，2 e1。 so I'dll actually be there。E2， once I've moved it over。

And that will be another unit length vector normal to E1。

 so that's the first part of taking an awful normal basis。Now。

 my third vector V3 isn't a linear combination of V1 and V2。

 so V3 isn't in the plane defined by V1 and V2。 So it's not in the plane of E1 and E2 either。

 so I can project V3 down let's say something like that onto the plane。Of E2 and E1。

 And that projection will be some vector in the plane composed of E2 S and E1。

 So I can then write down that V 3。Minus。V3 dotted with E1 E1s。

 That's going to be the component of V3 that's made up of E1s。Minus V 3 dotted with E 2。E2s。

 that's the component of V of V 3 that's made up of E2s。

 And then when all that's going to be left is going be this perpendicular guy there。

 So that's going to be a perpendicular vector， which we'll call U 3。

Which is perpendicular to the plane。 And it's some funny 3D space。

 So the diagramagon gets quite messy。And then if I normalize U3。Divide by the length of U 3。

Then I'll have a unit vector， which is normal to the plane normal to the other two。

 So now I've got an awful normal basis for E1 e2 E3。

 And I can keep on going through all the Vns until I've got enough awful normal basis vectors to complete the set and span the space that I originally had。

 But I've gone from a bunch of awkward nonorgonal nonunit vectors to a bunch of nice orthogonal unit vectors and all normal basis set。

 so that's how I construct an normal normal basis set and make my life easy so that my transformation vectors are nice。

 My transformation matrices are nice， sorry And so that I can do the transposes the inverse and all those lovely things。

 So I can use dot product projections for the transformations。

 all those nice things that are going to make my life very。

 very much nicer whenever I'm doing any transformations or rotations or whatever it is I want to do with my vectors。

 So that's gonna be really nice。 This is a really nice process。

 And what we'll do next is we'll apply this will try this for an example and see how it rolls and then apply。

😊，Back to doing a transformation。

![](img/c668cc476cfe605ee4abbe7cbc1e2fb2_2.png)
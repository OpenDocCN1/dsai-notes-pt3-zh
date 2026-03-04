# 【Algorithms Lab】计算几何 ｜ Computational Geometry p09 P09_Delaunay三角剖分（Delaunay三角剖分和Voronoi图_第2部分） -BV1Jtn7zSEXD_p9-

What is adeonone triangulation？We start by defining what the deic graph is。 And for that。

 we have to go back to the notion ofvolonno diagrams。 So let's say I have a point set。

 and I have thevolno diagram of that points set。 The delony graph is now the dual graph。

Of thatvolonnoy diagram。 So what does that mean for every cell of thevolonno diagram。

 I want to have a vertex in the delony graph。 The sales of thevolno diagram correspond to the input points。

 So that means as ver sees of the delony graph， I will have simply the set P。



![](img/01b53945ac1fd83403dc4bcf44d340bb_1.png)

![](img/01b53945ac1fd83403dc4bcf44d340bb_2.png)

And now I want to have an edge between two points。If the two sail。AJa。

 by which we hear me they share an edge。

![](img/01b53945ac1fd83403dc4bcf44d340bb_4.png)

And that's。Then the tool graph of the Voonno diagram and it's called not quite thelony graph yet because the delony graph is now the straight line drawing of that graph。

 so where between any two points I take the straight edge here for instance。These two points。

They correspond to these two cells， those cells share an edge。

 so the de graph has an edge and it has simply as an edge the segment between those two points。

That is a delaney graph and let's have a look at more properties of this graph in particular we want to show that it's a plane。

Graph， meaning it has no crossings。 So what we want to show is that the de graph has no crossings。

 We can prove this by contradiction。

![](img/01b53945ac1fd83403dc4bcf44d340bb_6.png)

So let's assume it has a crossing。And there are four vertices， four points。

That somehow there's an edge between these two points， there's an edge between those two points。

And those two edges cross So if the four points look like this and what I mean by this is I have three points on the convexile and one point inside。

 even if I take a complete graph， there is no crossing。

 So this is not how these four points may look like they will look like that in the sense that the four points form a convex shape or on their convexile。



![](img/01b53945ac1fd83403dc4bcf44d340bb_8.png)

And now in this example， okay， we see there is one edge。And from that one edge。

 we can also conclude there's a joint boundary here。



![](img/01b53945ac1fd83403dc4bcf44d340bb_10.png)

I can also go from that joint boundary in the cell of this point to that point。

 I'm remaining in that cell， I can also go to infinity here while remaining in that cell。

 likewise on the other side。So I can split the plane into two halves。

 such that this point is on the one side。 This point is on the other side and。

And at the splitting line， I stay within。These two sets。Of course。

 if I have an edge between these two。😊，The same will be true。 I can split again。

But what about the joint point here for one it has to be in one of those two or on their boundary or in one of those two or on their boundary。

 the only way this this can happen is that I actually have a shared vertex here but。

In terms of adjacencies and in terms of the definition of the dey graph， I will not。



![](img/01b53945ac1fd83403dc4bcf44d340bb_12.png)

Count these as being adjacent， so the delani graph would in this case look like this。

That's why I'm so far also talking about a delonone graph and not adeloone triangulation because a deno triangulation then。

Should have triangle。 So a annoying triangulation is what I get when I take the dey graph and add edges until I have a triangulation like this。

 for instance， this is a fairly special situation I can already say， I mean。

 we have this degree4 orno vertex， which actually means that all of these four points will be on one circle。

So you already see that's a kind of a nongene position situation and these other examples that we've seen here here and here we actually already have a twinulation。

And that's why we typically simply speak of a deny triangulation。

 but to introduce a concept and because of course， in nongene position this could happen。

 we also talk about iononic graphs so far so good。Now let's look at a characterization of delaney triangles or faces of the delay graph and delay edges。

 so edges of the delay graph， and for that we first look at a characterization of vernoi vertices and bonoi edges。

And for that， they use this circle CP of Q so what is that I pick a point Q and I take the largest disk with center Q such that there is no point in the interior。



![](img/01b53945ac1fd83403dc4bcf44d340bb_14.png)

So in this case。It would look something like that。So if I now increase the radius further。

 I will include this point。But so far， it does have no point in the interior。

 Now we can characterize vnoi vertices using this。

![](img/01b53945ac1fd83403dc4bcf44d340bb_16.png)

Dis， namemly in the following way。I have that something is a vernoi vertex。Exactly。

If as the largest boy with no point in the interior actually has three points of P on the boundary。

AndSome 1，2，3。 This is now a vertex。 And why is that the case because。For a Voonno vertex。

 it's on the boundary of at least three cells， meaning it has three nearest neighbors， at least。

And all of these three will be on this。Dス。For avonoi edge， I have two nearest neighbors。

 So what does that mean， It means that。This point is on the vnoi edge of these two。

Exactly if these two points are the nearest neighbors。

 meaning if I take the largest empty circle around that point with possibly points or with points on the boundary then those two points will show up on the boundary。

 So this is a characterization ofvolnoi vertices， three points on the boundary andvolnoi edges like this circle Cp has two points on the boundary。

 So this is a statement aboutvolnoy diagrams but we're making the statement right now to characterize the Larney edges and the Lay triangles or faces of the delay triangulation。



![](img/01b53945ac1fd83403dc4bcf44d340bb_18.png)

![](img/01b53945ac1fd83403dc4bcf44d340bb_19.png)

Because what does this mean， we will have a face in the alonni。Graph here。Surrounded。By these。

Three edges， and we can characterize this face by having an empty circlecicle。

Through the vertices of that face。That so I have a points at P。And now I can say three points。

A vertices of the same phase of the annograph， even and only if I draw the circumci through those three points。

 it contains no other point in the interior of the points set。Likewise。

 something is an edge of the deit triangulation， if and only if the CP for thatvolnoy edge is empty。

 which stated differently simply says if and only if there is an empty circle。

With those two points on the boundary。 This is actually a delonone edge。

 So now we have characterized casess and the triangulations in particular。



![](img/01b53945ac1fd83403dc4bcf44d340bb_21.png)

![](img/01b53945ac1fd83403dc4bcf44d340bb_22.png)

In a delay triangulation， it's a triangle and delay edges。 So if we have a triangulation， it is。



![](img/01b53945ac1fd83403dc4bcf44d340bb_24.png)

A triangulation is a deic triangulation if and only if。😊。

For every triangle I can look at the circumcicle there's no point inside so now we know more about the structure of the line triangs also how to recognize the line triangulations。

 of course we can simply look at these circumciles。



![](img/01b53945ac1fd83403dc4bcf44d340bb_26.png)

![](img/01b53945ac1fd83403dc4bcf44d340bb_27.png)

Let's briefly talk about complexity， so how many triangles does the Lani triangulation？

Of endpoint have umost。And the options are roughly2 n divided by 3 or roughly2 n or3。

The correct answer is 2 n minus5。And the easy way to see is that。We're looking at triangles。

And those correspond。 So let's let's first look at the setting of general positions。

 Those correspond to。我内。Vertices and forvoloid vertices， we already had this pound of 2 and minus5。

But we can also drive this again simply with Os formula Next we're going to take a different perspective on the line triangulations。

 or actually we're going to look at triangulations with a different property and see that this will eventually lead us again to the line triangulations。

 Next， I'd like to talk about triangulations。

![](img/01b53945ac1fd83403dc4bcf44d340bb_29.png)

More generally and specifically about angle optimal triangulations。

 So let's first start with what is a triangulation of a point set。

So a triangulation is defined as being a maximal planar subdivision of that set of points。

 so what does that mean So it's a planar subdivisions with non crossssing and I'm using straight line segments to connect vertices and it's maximal in the sense that I'm adding as many address as possible and in that way every face will be a triangle。

So there's observations here。For one， any inner phase is a triangle。

 So any phase that I look at here that's a triangle。

 then there's also the outside so there's the outer phase。

And the outer face is simply the opposite of the convex hi。 So here this is a convexile。

 everything was in the convexile will be triangulated， and then there's the outside。



![](img/01b53945ac1fd83403dc4bcf44d340bb_31.png)

![](img/01b53945ac1fd83403dc4bcf44d340bb_32.png)

Now I would like to make a statement about the complexity of a triangulation and this I will phrase in terms of the number of vertices on the convex high and n。

And let's say n are noncolinear points so n not all on the same line。

And then I would like to say something about the number of twinwinangles and the number of edges。



![](img/01b53945ac1fd83403dc4bcf44d340bb_34.png)

So maybe that's something you can do on with pen and paper。Keep in mind。

 Use formula for this might be Oulers formula， which says for a connected plane graph。

 and this graph is connected because it's max。Number faces minus number of edges plus number of vertices is 2。

 and here we are also counting the outer phase。So if you did the computation。

 you hopefully ended up with a following numbers。

![](img/01b53945ac1fd83403dc4bcf44d340bb_36.png)

We have。2 n minus2 minus H。Trying us。

![](img/01b53945ac1fd83403dc4bcf44d340bb_38.png)

So if we have a very small convexile， the smallest convexile that you could have is three points。

 then we have 2 n minus5 triangles and if the convex hole is more complex we have even fewer triangles。



![](img/01b53945ac1fd83403dc4bcf44d340bb_40.png)

![](img/01b53945ac1fd83403dc4bcf44d340bb_41.png)

And we have3 n-3 H edges。 So we have at most 3 n-6 edges， and it's a convexile is more complex。

 fewer ones。 Now， given a point set， there's， of course， many ways to triangulate them。

 So instead of this edge， I could have used this edge。Answl。

So how do we decide which triangulation we actually would like to have for this。

 we go back to the motivation of spatial interpolation。

 So here we have height measurements we project them down to the plane。



![](img/01b53945ac1fd83403dc4bcf44d340bb_43.png)

A simple way to get interpolations was using the vonoid diagrams， this is not what we want to do now。

 but what we want to do now is we want to use a triangulation of the point set and in that way get continuous heights in the plane。

And the question that we're asking is， what is a good triangulation？

Let's have a look at an example of a point set so here we have the same point set and post drawings。

 but different triangulations so where do they differ， they define exactly the set here。



![](img/01b53945ac1fd83403dc4bcf44d340bb_45.png)

And he。

![](img/01b53945ac1fd83403dc4bcf44d340bb_47.png)

Now， which one is better？😊，That of course， depends on what actually happens in that phase。

 and we don't know。

![](img/01b53945ac1fd83403dc4bcf44d340bb_49.png)

But let's make a best guess。 So we're looking at， let's say， the same point here and there。



![](img/01b53945ac1fd83403dc4bcf44d340bb_51.png)

So if you look at those two points and on the left hand side。

 we are going to interpolate between those two and we will get a height of。

 let's say 985 here we will interpolate between those two and get a much smaller height。 Now。

 of course， we don't know which one is2。

![](img/01b53945ac1fd83403dc4bcf44d340bb_53.png)

![](img/01b53945ac1fd83403dc4bcf44d340bb_54.png)

![](img/01b53945ac1fd83403dc4bcf44d340bb_55.png)

But it seems more natural to go with the values that R。Clloser to that point。



![](img/01b53945ac1fd83403dc4bcf44d340bb_57.png)

So in this terrain here we have this ridge that goes through。

 and we have measurements fairly closely along that ridge here now there's this sudden drop and it goes up again。



![](img/01b53945ac1fd83403dc4bcf44d340bb_59.png)

Could be true。But seems unlikely。 and what。We don't like about this specific triangulation is that this point gets values from points very far away。

 which is of course relative。

![](img/01b53945ac1fd83403dc4bcf44d340bb_61.png)

But it means so one way of interpreting it is that we have a very long twinwinanglelet system。



![](img/01b53945ac1fd83403dc4bcf44d340bb_63.png)

Let's say skinny triangle。

![](img/01b53945ac1fd83403dc4bcf44d340bb_65.png)

How thin triger。So we would like to avoid those and thin triangles come from having small angles。

 so what we would like to do is avoid small angles and as an optimization criteria what we could say is and what we will say now is we want to maximize the smallest angle within the triangles and this will then be angle optimal triangulations。



![](img/01b53945ac1fd83403dc4bcf44d340bb_67.png)

![](img/01b53945ac1fd83403dc4bcf44d340bb_68.png)

![](img/01b53945ac1fd83403dc4bcf44d340bb_69.png)

![](img/01b53945ac1fd83403dc4bcf44d340bb_70.png)

So given a triangulation， we will look at the so called angle vector and the angle vector will simply list all angles sorted by increasing values Okay。

 so this is not the most exciting angle vector because all angles are 60 degrees。



![](img/01b53945ac1fd83403dc4bcf44d340bb_72.png)

This one is more interesting here we have some with 30 degrees4 and then two is 120 degrees。

And now we're going to compare triangulations based on lexxiographical ordering。

 So what were saying is we're going to look at the smallest angle in this case。

 60 and 30 and then sort them based on that value。So this one will be this one will be higher in the order。

Because it has a higher value here， if they would have both had a 60 here。

 we would have looked at the next one and the next one and the next one and so on。

 so that means it means that we're doing lexxicoographical autoing。

In terms of angle optimality and avoiding small angles。

 we would now want to say that this one is not。So good。

So we're going to take the triangulation that is。Maximum。With regard to this ordering。

So we say a triangulation is angle optimal if its angle vector is larger equal to any other angle vector of any other triangulation。

So now we want to find angle optimal triangulations and we were going to see a very simple algorithm to get them。

 and for that we are going to introduce a concept of edge flips。



![](img/01b53945ac1fd83403dc4bcf44d340bb_74.png)

So here we again have a triangulation and now we are going to say that this edge is illegal。😊。

Because if I take out this edge and replace it by the。How is it it？Then the angle vector improves。

Yeah， so this edge is illegal。 If this modest angle incident to that edge， if I can increase that by。

Flipping that。 So here's the smallest angle is 30 degrees and flipping。Gives me instead。

 these angles here。Which are 60 degrees。 So this edge would be illegal if I want to have an angle optimal triangulate。

 I would want to flip that edge。 If I flip an illegal edge， it also means that the angle vector。

 So after flipping here， the angle vector will have improved will have increased in terms of the reographical order。

Okay， so let's look at this by an example if I want to remove all illegal edges in this example。😊。

How many flips do I need，0，2， or5？Here I need three flips。

You might have answered too because you see two illegal edges and that is actually correct。

 there are two illegal edges。So why do I say that I need three flips？

So now I flipped one of the edges。Let me flip the other edge。After flipping that edge。

This edge becomes illegal， so I would have to flip that one and then after we flip something。

 So here we needed three flips to remove all illegal edges。

 So what we're going to look at next is how can we check whether an edge is illegal without explicitly comparing。

Angers。We've seen illegal addresss and characterize them by angles。

 so now we want to take a different perspective on illegal addresss and this will bring this concept of illegal addresss and then legal triangulations。

Back to the concept of theic triangulations。

![](img/01b53945ac1fd83403dc4bcf44d340bb_76.png)

So for that we start with Tus The， which is a statement about angles and relates it to circles。

 specifically you will have seen it in the following form， So if I have A and B。

And they can allow the diameter or the diameter of a circle。And now I have a third point C。

Now on the circle。Then this is the right angle。So no matter which point I pick。

 so this you will know from high school most likely。

I will want to show you a generalization of this the and it is the following。

 so instead of taking a line segment that is a diameter I'm taking arbitrary points A and B on the circle from this segment here。



![](img/01b53945ac1fd83403dc4bcf44d340bb_78.png)

Now， of course， if I take a third point， this is not necessarily a degree angle。



![](img/01b53945ac1fd83403dc4bcf44d340bb_80.png)

But the generalization that I'm using here states the following。

If I have two points on the circle P and Q， and I'm looking at the Angular P here。

And the angle of Q for Q here。Those two angles will be the same no matter where these points lie on the circle。



![](img/01b53945ac1fd83403dc4bcf44d340bb_82.png)

Furthermore， if I take a point inside the circle like R here。

 this angle here will be bigger than those two angles。😊。



![](img/01b53945ac1fd83403dc4bcf44d340bb_84.png)

And if I take one outside like S， this angle here will be smaller。

 We can use Tth's theorem to characterize whether an edge is illegal or not in the following way。



![](img/01b53945ac1fd83403dc4bcf44d340bb_86.png)

So let's say I want to know whether PQ here。Is illegal legal。And for that。

 I look at the two incident triangles， So PRQ and PQ S。

This gives me these points and S and Pq is illegal if and only if if I take the circle circle through one of those two triangles。

 so let's say through P and Q so the circle that goes through those three points and I look at where S lies。

 if S lies in the circle the edge is illegal， if it lies outside so if S would be here it would be legal。

So how can we prove that using telehen？So essentially any angle that is in this triangulation currently。

 I will want to set into a relation with an angle that I would get if I take that tri。For instance。

If you take this angle here。Now， it's the angle of。We're taking this here as a base。Of this point。

On that circle。With that edge as a base， I can set that in relation to this angle here which is larger because s is inside the so so by T terms this is larger and I can do this for all of the angles and by going through all of these calculations I see that indeed my edge was illegal or is illegal if and only if s is。



![](img/01b53945ac1fd83403dc4bcf44d340bb_88.png)

Inside， and this gives me a way to see whether an edge is ill without measuring angles。 So。

 for instance， this edge here。I can ask， is it illegal。

 so for that I draw the circumcicle through three of the vertices of an incident triangle？

The triangle on the other side， the the remaining vertex that is in that circle。

 So I know it's illegal， or if I want to。Get rid of illegal address。

 I would now flip it and would have improved my triangulation。In this example here。

 we have no illegal edges left and this we now call a legal triangulation。😊。

First natural question would be to ask， okay， I have to find this concept of legal triangulations。

 but do they actually exist to where can I always construct a legal triangulation？

The answer to this is yes， so here is a very simple algorithm and it is not necessarily efficient。

 but it will lead to a legal triangulation。 So what it does whenever there is still an illegal edge。

I will flip it， so why might this not lead to a legal triangulation？

It might not lead to have legal triangulation if I somehow have an infinite loop。

 but this cannot happen because we know that with every flip， the angle vector strictly improves。



![](img/01b53945ac1fd83403dc4bcf44d340bb_90.png)

So if the anger factor strictly increases。I will have to every time I do a flip be at a triangulation that I haven't seen so far。

 and because the number of triangulations on a point set is finite。

 this will mean that at some points as I wasm will finish。

 Let's look at the relation between legal triangulations and angle optimal triangulation。



![](img/01b53945ac1fd83403dc4bcf44d340bb_92.png)

I mean， that was our motivation to look at illegal edges and making triangulations legal。



![](img/01b53945ac1fd83403dc4bcf44d340bb_94.png)

So， of course， any angle optimal triangulation isling。 So an angle optimization is。

Maximum in relation to to the angle vector so there is no flip that could improve it。

 So angle opt triangulations are legal， but is every legal triangulations also angle optim we will see that at least in general position this actually then is the case。



![](img/01b53945ac1fd83403dc4bcf44d340bb_96.png)

And we will see this through looking at the lana triangs。

What we have namely is that if I'm opponent a set of points。

 a triangulation is legal if and only if it is a delon triangle。



![](img/01b53945ac1fd83403dc4bcf44d340bb_98.png)

So what is the relationship between legal triangulations that delay in triangulations？😊。



![](img/01b53945ac1fd83403dc4bcf44d340bb_100.png)

So let's look at this configuration here。This is not legal and it is not legal， so the H。啊。

Is not legal， because。I have this incident triangle and its vertex。Is inside the so。

So for the lo triangangle， we had a similar but stronger criterion。 there we said， okay。

 this cannot be the LA triangle because。😊，This circumcircle should be completely empty。

So not only this point shouldn't be here， but also any other point shouldn't be。

 so this is all forbidden for the line tri being delonney or for an edge then to be delony。

 so meaning that I should be able to find an empty subme circle is a stronger statement as such than being legal。



![](img/01b53945ac1fd83403dc4bcf44d340bb_102.png)

That also means in terms of the proof the one direction is straightforward。

 If a triangle is a de triangle in particular means the circumcicle is empty。

 it means that also the point S cannot be in that circumci。 The other direction is a bit more work。

 Let's assume I have this point S。

![](img/01b53945ac1fd83403dc4bcf44d340bb_104.png)

![](img/01b53945ac1fd83403dc4bcf44d340bb_105.png)

In the interior。But I do not have this triangler。 what I want to prove。Is。

That also for legal triangulations， there cannot be a point here。In this circle。

 if it's a neighboring point。 So if it if I have these edges。

 then obviously it's not legal and I'm fine。 The problematic case is if there's something in between。

So could I have a setting like that， the neighboring one is outside。

 but now there's a different one that is inside。

![](img/01b53945ac1fd83403dc4bcf44d340bb_107.png)

So the proof that this cannot happen will be approved by contradiction so suppose we have such a point and we're going to pick this setting such that this is a PQR as a triangle with a property that's the angle here。

At S is maximized。So it's a triangle with S。😊，In the circum circlecle， with maximum anger here。

 But what we get now is that we， we assume that T is now。The third point of the triangle is P and R。

 So the circumcircle of that one lies slightly above that other circumcircle So center moves along that center line here slightly。

 so it is further up here。And that in particular means that S is also inside of this one。

 And if I take now this angle， it is this angle plus that angle。



![](img/01b53945ac1fd83403dc4bcf44d340bb_109.png)

![](img/01b53945ac1fd83403dc4bcf44d340bb_110.png)

So in that angle， okay， I need to sure that that is a positive angle。

 but I can use tasome to observe that。 So I know this angle is even bigger contradicting our initial assumption of how we pick this triangle。



![](img/01b53945ac1fd83403dc4bcf44d340bb_112.png)

![](img/01b53945ac1fd83403dc4bcf44d340bb_113.png)

![](img/01b53945ac1fd83403dc4bcf44d340bb_114.png)

In conclusion， this cannot happen。 in conclusion， this means that a legal。



![](img/01b53945ac1fd83403dc4bcf44d340bb_116.png)

A triangulation is legal if and only if it's a aligned triangle。



![](img/01b53945ac1fd83403dc4bcf44d340bb_118.png)

Now， if we have points in general position， there is exactly one non triangulation4 points it。

 so it is unique。😊，That also it means。The legal triangulation for such a point that is unique。Now。

 we know that the angle optimal triangulation is legal。 If there's only one legal triangulation。

 then I know that that legal triangulation is also angle optimal。

 That means that in this setting of general position， angle optimal。

Legal and law are all the same thing， in particular meaning that the law triangulation in this setting is angle optimal and more generally also a nongene position。



![](img/01b53945ac1fd83403dc4bcf44d340bb_120.png)

![](img/01b53945ac1fd83403dc4bcf44d340bb_121.png)

The angle optimal triangulation will be legal。A legal triangulation will be a dey triangulation。

 meaning that one of the delani triangulations of the delani graph if we now are not speaking about general position will be the angle optimal triangulation。



![](img/01b53945ac1fd83403dc4bcf44d340bb_123.png)

Or an anger up my triangulation。

![](img/01b53945ac1fd83403dc4bcf44d340bb_125.png)

Nater question is if I'm in nongene position， is then every delonish triangulation still aular optimalim Op are yes。

 but the proof is more complicated， no but still the smallest angle is maximized or no and not even the smallest angle is optimalim。

The correct answer is no， but。This modest angle。Is still。Maximized。And again。

 we can prove this by the that the smallest angle is maximized。But indeed。

 not every deian triangulation in nongene position will be angered optimalim。

But the case we are most interested in is general position and then legal to law anger optimal all the same。

Next we want to look at how to compute thenet triangulation。

 we want to compute the deate triangulation and we want to do so using a randomized incremental construction。



![](img/01b53945ac1fd83403dc4bcf44d340bb_127.png)

So how will this look like what were going from compute where we look like that。

 so we will have our point set， but because we would want to have a big outer face we will add three points on the outside so this is what we're going to compute and we're going to do it in the following way we initially create a large outer triangle。



![](img/01b53945ac1fd83403dc4bcf44d340bb_129.png)

![](img/01b53945ac1fd83403dc4bcf44d340bb_130.png)

Then we randomly permute our points because we wanted to use a randomized incremental construction。

 We add them one by one。So for each point。We insert it into the current triangulation。

 making sure that we can have a triangulation and at the very end we discard。The outer points。

And what remains will be that aligned triangulation of our points set。

 So when we insert a point So here。When we insert a point， what do we need to do？



![](img/01b53945ac1fd83403dc4bcf44d340bb_132.png)

So first of all， we need to find。

![](img/01b53945ac1fd83403dc4bcf44d340bb_134.png)

The triangle that contains this point。And we have to discuss how to do that later。

If I know that triangle I can do the following， I split that triangle by placing this point here。

And adding those edges， now I have three targetss。Now， this might not be thelo triang。 So how can we。

Make sure that we get a aligned line triangulation。 So here's a very simple way of doing so。

 And we still need to prove that that is actually correct。 Name is the following。 So we do this。

 And now we check。For the opposing。Adddres or these three address。 We check whether they are legal。

 And for this， we have this。Recursive method legalize edge that we will call three times once for each edge。

 so legalizing this edge will check whether this edge is legal if it is not。

 if it's legal were done if it's not legal I would remove it so I would flip and then I would have to check those two edges。

So that's the idea here， okay， that is if if the point lies within a triangle。

 there is a special case if it lies on an edge， then we would kind of split it like。

Like that into triangles。So this， but this would be the case we're going to focus on other cases。



![](img/01b53945ac1fd83403dc4bcf44d340bb_136.png)

Essentially the same。So once more how do I now legalize an edge so this is let's say my new point。

 if I call legalize on that edge I know how to check that I can check whether the point on the other side so forming this triangle。

 whether that point is in the circum circlecle of these three。If it's inside the edge is illegal。

 if the edge is illegal， I want to flip it， so I will flip this edge getting rid of that one now possibly。

These two edges are illegal， so I will recursively call legalized edge。



![](img/01b53945ac1fd83403dc4bcf44d340bb_138.png)

On those two edges， we need to check whether all edges that we get in this way or all edges in the triangulation that we then have are actually de。

 So that is what we need to prove to show that this is correct。 So all edges that we inserted。

Those are legal and how can we see that， So let's say this is our new point。

 all edges that we inserted are actually incident to that point。 So they have this as a vertex。

And locally， that looks like this。 So here's my new point， previously。I had this。

Edge here and the circumcicle of Pj， P and P previously was empty， but now PR was added。

 So my new point。Can I find an empty circle for this edge？And that is indeed the case。

 I can start from this circumcicle of the30 points and shrink it。

Inside in the direction of PR until it includes PR。

 and in this way I get a circle that is completely within this old circle circlecle that was empty。



![](img/01b53945ac1fd83403dc4bcf44d340bb_140.png)

So it is again empty and the edge is the la。

![](img/01b53945ac1fd83403dc4bcf44d340bb_142.png)

Now， all edges on the boundary of this region， I checked whether they're legal or not。I mean。

 algorithms stopped because they were legal， so they are legal。

All edges outside are also legal because for them nothing changed and legal is a local criteria。

So now we know all edges are legal， therefore we know legal all the La， but that is the same thing。

 So all edges are in particular the L edges What remains now is to see how do I actually find which triangle to insert into and we're going to see that next we are in the midst of computing that align triangulation using a randomized incremental construction we've seen how to update that align triangulation when I have a point that I know which triangle old triangle it falls into what we haven't talked about yet is a how do we actually kind of initialize this big。



![](img/01b53945ac1fd83403dc4bcf44d340bb_144.png)

Triangle at the beginning B， how do we actually find the triangle that contains a new point And for that we were going to need a search structure。

 So let's start with this big triangle outside So we're going to have points p0 p minus-1 p minus-2。

 which somehow should be far enough away so that they don't interact with the triangulation with the de triangulation of the points set the best way or safest way of doing so is to treat these points outside symbolically so we're not actually giving them locations we're just making sure that any time we do a test like a test of is this point within the circum circlecle of some triangle we're going to treat this point as being very far away。



![](img/01b53945ac1fd83403dc4bcf44d340bb_146.png)

![](img/01b53945ac1fd83403dc4bcf44d340bb_147.png)

![](img/01b53945ac1fd83403dc4bcf44d340bb_148.png)

So these points will not be in circumstancescis so that's the utilizationization。

 what this gives us is that at the very beginning when we start our construction we have a big triangle outside so when I insert my first point I know it will be in that triangle。

And now we're going to use a search structure that kind of starts。 if I get a new point。

 I start with a big triangle。within that big triangle， I will fall into smaller triangles。



![](img/01b53945ac1fd83403dc4bcf44d340bb_150.png)

And in that way， I can。Find my way eventually to the triangle that contains the point。

 So how does this look like more specifically we're going to build a search structure where the leaves correspond to the current triangles or the triangles currently in the de triangulation and the inner nodes corresponds to triangles that have been deleted so they were there somewhere in the construction but they were deleted for instance。

 here。

![](img/01b53945ac1fd83403dc4bcf44d340bb_152.png)

I have my current triangulation and then I have these leaves。Delta 1， Dlta 2。

 Dlta 3 for the current triangles。 If I'm now inserting a new point， let's say this point PR。

 what does it mean I'm deleting。The triangle delta 1 first。I'm splitting it into three parts。

 meaning I will get three new triangles here。

![](img/01b53945ac1fd83403dc4bcf44d340bb_154.png)

Which attached to the triangle that I just deleted。 So now if I have a point that lies。

 let's say here， I will first， okay， I will first see it's in the big triangle。 At some point。

 I will work my way to figuring out that it's in Delta 1。



![](img/01b53945ac1fd83403dc4bcf44d340bb_156.png)

![](img/01b53945ac1fd83403dc4bcf44d340bb_157.png)

And then when I know that it I， it's in Dlta 1， I will have to check which of these three children contains that point。

 and then I can。Go further down。 That structure。Now in this example， I get those three triangles。

 but I would still lets say legalize this edge here， meaning I would have this flip here。😊。

So this means that this triangle up here and delta 2， those are replaced by two other triangles。

 delta 4 and Dlta 5。How do we achieve this？So this triangle here corresponds to that one and I have delta 2。

 those two will be deleted and they together cover Delta 4 Dlta 5 so I have pointers from those two triangles to Delta 4 and delta 5 and then let's say I have another flip。

Namely， these two triangles disappear and I will replaced by those two。

 then I would take data 4 and this down here is theta 3。Delta 4 and Delta 3。

 they would now be inner triangles with Delta 6 and Dlta 7。



![](img/01b53945ac1fd83403dc4bcf44d340bb_159.png)

F children。

![](img/01b53945ac1fd83403dc4bcf44d340bb_161.png)

In this way， I build the structure， and then if I have a query。😊。

It first falls into the big triangle， outer triangle， and then。



![](img/01b53945ac1fd83403dc4bcf44d340bb_163.png)

![](img/01b53945ac1fd83403dc4bcf44d340bb_164.png)

This structure will always tell me， okay， I have a triangle。

 it has some children so I test which slide I'm in and these are either three children in this case or two children in that case。



![](img/01b53945ac1fd83403dc4bcf44d340bb_166.png)

And in that way， I can eventually find the triangle that I'm currently contained。

So that's how I search， and that's how the search structure looks like。

 Now we want to show something about the complexity of our algorithm。

 specifically we want to show that the triangles that we create during the process that we only have a linear number of those triangles in particular。

 this means that the search structure will have linear size。

 So what I want to show is that the expected number of triangles created in the whole process is at most 9 n plus1。

 So it's linear。 for this。

![](img/01b53945ac1fd83403dc4bcf44d340bb_168.png)

We use backwards analysis。 So we have a given triangulation。

 Any point in that triangulation has the same probability of being the last one。

 And we ask how many triangles were inserted If a certain point， let's say PR was the last one。

 Each of these points now has the same probability， one divided if it's my the half points or。

1 divided by R of being the last point。So I can say something about the expected degree of the last point。

 because I can say something about the overall degree。

 we have that the overall number of edges is bounded by 3 n for n points or 3 R for R points。



![](img/01b53945ac1fd83403dc4bcf44d340bb_170.png)

The degree is the sum of degrees is at most two times this。

 so if I sum up all the degrees that's bounded by 6 R and then if I take the average degree so the expected degree of the last point is bounded by 6 so what does that tell me about how many triangles were createdd？

So if something， let's say something has a degree of 6。

 so this is my last point and it has a degree of 6，1，2，3，5，6。

What happened during the insertion of that point？So initially， let's say it ended up in a triangle。

I created three triangles。再 about这个 three。Now， for every。Other edge。That this vertex has afterwards。

 I needed one flip。 So with one flip， I would have had this situation。

This increases the degree by one。But it creates two new triangles。So meaning I get here plus2。

Now this gives me degree 4， I have another flip， which I mean， it also deletes some tris。

 but it creates two new ones plus So plus 2。Now I have a degree of5 and one more plus2 would give me。

In this case， a degree of6。More generally speaking。

 the number of triangles created if I insert a point of a certain degree is a following two times that degree because for every edge that I want to have I pay two。

 except for the first three edges because they kind of came for free because I just not for free and I created three triangles when I first insert。



![](img/01b53945ac1fd83403dc4bcf44d340bb_172.png)

![](img/01b53945ac1fd83403dc4bcf44d340bb_173.png)

So the number of triangles created can be bounded by 2 times degree minus3。 the expected degree is 6。

 so the expected number of triangles created is bounded by2。Time six。嗯。So that's 12 my 3。 That's 9。

 And I have the outer triangle。 So that gives me one more。 So overall。

 I get this found of 9 n plus  one on the expected number of triangles created during the construction。

 So that's an update cost。 So if I now12。😊，Completely analyze algorithm。 I also need to analyze。

How long searching takes。So this gives me A how big is the search structure and B also how much time it took to legalize all those edges。

 but what I have an accounted for is how long does it take me to find my points in the search structure？

The proof or the analysis you can find in the book。It's slightly more intricate。

 and I'm going to leave it out here， but what you get that overall your construction will run in expected order n log n time。

 So what we know now is we can compute the de integration of endpoints in expected order in log n time using a randomized incremental construction。

 We now never actually talked about how to computevoloid diagrams。



![](img/01b53945ac1fd83403dc4bcf44d340bb_175.png)

So how fast can we actually compute avolonoid hacker in linear time or also in auto end of end time。

 or do we for that actually need quatic time？

![](img/01b53945ac1fd83403dc4bcf44d340bb_177.png)

We can also compute vonoid diagrams in expected analog log and time。

 namely simply for the reason that the de triangulation contains already all the information we need to construct the vonoid diagram。

 So from the de triangulation it can in linear time go to thevolonoid diagram and in that way also get that in。



![](img/01b53945ac1fd83403dc4bcf44d340bb_179.png)

Order end log end time。 Now I always have to say expected because we saw randomized incremental construction。



![](img/01b53945ac1fd83403dc4bcf44d340bb_181.png)

Both the the log triangulation and thevoloid diagram can also be computed deterministically in order in log n time。

 so to sum things up。

![](img/01b53945ac1fd83403dc4bcf44d340bb_183.png)

We've seen how to compute all triangulations。And。As that also to know how to computevoloid diagrams in order and log n time。

Using a randomized incremental construction。

![](img/01b53945ac1fd83403dc4bcf44d340bb_185.png)
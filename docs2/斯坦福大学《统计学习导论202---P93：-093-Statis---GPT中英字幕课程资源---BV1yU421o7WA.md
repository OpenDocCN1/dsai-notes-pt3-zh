# 斯坦福大学《统计学习导论2023R语言版｜An Introduction to Statistical Learning with R》中英字幕 - P93：-093-Statistical Learning_ 12.R.2 K means Clustering.zh_en - GPT中英字幕课程资源 - BV1yU421o7WA

Okay， the next method we're going to discuss is K means clustering。

 also a very useful tool for finding clusters in the data， and it works in any dimension。

 but in order to demonstrate it for you I'm going to do it in two dimensions because we can actually look at the clusters and see how well it's done。

So first， what we're going to do is we yeah， we can actually make some fake data just for purposes of demonstration。

So this is a typical incantation when you make fake data。 So first of all， we set the seed。

 the random number seed to some using some arbitrary number，101。

 somehow my arbitrary number comes up a lot。 So I set the seed。

Then I'm going to make a matrix of random normals a two column matrix。 and I want 100 observations。

 so I'll make。I I， I in embedded inside the call to matrix。 the data comes from R norm。

 and I'm gonna make 100 times two， because I want two columns， standard normals。

And then this says there's 100 columns and sorry， 100 rows and two columns。

 okay so I generate the data。So at this point it's just a cloud of Gaussians。

 But now what I'm going to do is I'm going to make four clusters。 I'm going to generate some means。

 and I'm going to displace some of these Gaussians by shifting their means around。

 and differently for each， you know for four clusters。

 So the way I do that I'll make another random normal matrix。 In this case。

 I want8 because it's going to be four clusters each with two。😊，Means， okay。

 so I'm generating the means here。 And the year， the random normals have standard deviation 4 because I want these means to be shift around much more than the actual data they did。

 And so it's going to be a four column matrix of means。 And sorry， a four rows and two columns。Okay。

 so that's how I get the means。And now I decide which of the rows get which means。 So Im going。

Pick a random sample from the numbers 1 to 4。 I want 100 of them because I've got 100 rows and replace equals  true。

 So which is going to say which observation belongs to which cluster。

So now simply add the appropriate mean to the appropriate rows。

 So this is this is a kind of typical R vector operation that's nice and tricky and effective。

 So x mean is a four row matrix， but I'm indexing it with 100 indices。

 So that'll produce 100 row matrix with two columns so it'll pick out the right the right mean for each row。

 And I' just add it to the original x。😊，Okay， and now make a plot。 and there you have it。

 So there's a plot X。 plots first two the only are two coordinates。 and， and I give it the color。

 which is， I give it which which is for each point is a number  one to4。

 and it tells it which cluster it belongs to。And it just uses the colors 1， to 4， which are black。

 red， green and blue。 And so these are the data。 And there we see the clusters that I've imposed。

We know the clusters， but now we're going to hand these data to hierarchical clustering and not tell it what the clusters are。

 it's supposed to find them automatically and we'll use the K means algorithm。Okay。

 we're going to tell it theyre four clusters yet。If we told there were three clusters。

 we would probably find two of the clusters and then merge two of them together。Okay， so here we go。

 we call K means and we tell it four clusters and we tell it to do 15 random starts。

 Rand starts are cheap。 If you remember K means clustering starts with a random start for where the clusters are。

 and of course， if you pick a bad random start， it might find you a bad solution。

 Unlike in this case， but that's what we do anyway。And。

We can print out the the result and it prints out a number of things for you。

It prints out the cluster means it's going to be four of them because they're four clusters。

The cluster vector。 that's the assignment of each point to the cluster that clusters that it found。

 And then there's some summaries of the cluster。 So the within cluster sum of squares by cluster。

 they're four clusters。 So that's the sum of squares within each cluster that sum of squares deviations of each point around its cluster mean。

And then， and this is perhaps a more interesting。 The between summer squares to the total summer squares。

 So this is， in a sense， this is like the R squared for clustering。

 It's a per cent of variances explained by the cluster means。 And it's pretty high。

 So it suggests it's done a good job。 And then it tells us what the the。

Other components on the cluster object are。Okay， so now we're going to plot the data。嗯。

And there it is， and。We've identified the clusters that it found。

 So we plot the data with big circles。For each point。

And the colouring year is not our original cluster。 when we generated the data。 we， we， we， we。

 we made clusters。 This is the the， these are the cluster assignments found by the K means clustering algorithm。

So to see our Willer did with in terms of the original known clusters， we can include those points。

 That I made these circles a bit bigger。 So I put the points inside。And well。

 what you see now is that we have a colour mismatch。

 So we named we named the clusters 1 to 4 in some order。

 The Ka's clustering algorithm found four clusters， and it named them  one to 4。 but， of course。

 the ordering is arbitrary。 so it picked a different order。

So we can look at the clusters here and just reassign the colors。

 which is what Ill do in the next line。And now， you see。This is a more useful plot。

 So we see the outer circles are the K means clustering cluster I D and the inner points are original cluster I D。

 And you can see the mismatches。 So there's a black point。

 which actually belonged to this cluster from the original data was。

It's signed to the green cluster year。And here's a blue point that originally belonged to this cluster has been assigned to the black point。

 quitete reasonably， of course， because it's much closer to these as it turned out than than not。

So that's， that's Ka means clustering for you and just some nice graphical techniques for， for。

For having a look at the at the results， if， it's， especially if the data ist two dimensional。

 that's easy to do。
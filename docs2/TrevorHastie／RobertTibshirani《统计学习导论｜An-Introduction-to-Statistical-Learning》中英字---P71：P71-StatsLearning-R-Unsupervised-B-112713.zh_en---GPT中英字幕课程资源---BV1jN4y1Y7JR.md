# TrevorHastie／RobertTibshirani《统计学习导论｜An Introduction to Statistical Learning》中英字 - P71：P71 StatsLearning R Unsupervised B 112713.zh_en - GPT中英字幕课程资源 - BV1jN4y1Y7JR

Okay， the next the next method we're going to discuss is K means clustering。

 also a very useful tool for finding clusters in the data， and it works in any dimension。

 but in order to demonstrate it for you I'm going to do it in two dimensions because we can actually look at the clusters and see how well it's done。

😊，So first， what we're going to do is we yeah， we can actually make some fake data just for purposes of demonstration。

So this is a typical incantation when you make fake data。 So first of all， we set the seed。

 the random number seed to some using some arbitrary number， 101。

 somehow is my arbitrary number comes up a lot。 So I set the seed。

Then I'm going to make a matrix of random normals， a two column matrix。

 and I want 100 observations so I'll make。II embedded inside the call to matrix。

 the data comes from R norm， and I'm going to make 100 times two because I want two columns。

 standard normals。And then this says there's 100 columns and sorry， 100 rows and two columns。

 so I generate the data。So at this point it's just a cloud of Gaussians。

 But now what I'm going to do is I'm going to make four clusters。

 I'm going to generate some means and I'm going to displace some of these Gaussians by shifting their means around and differently for each you know for four clusters。

 So the way I do that I'll make another random normal matrix。 In this case。

 I want eight because it's going to be four clusters each with two。😊，Means， okay。

 so I'm generating the means here。 And the year， the random normals have standard deviation 4。

 because I want these means to be shift around much more than the the actual data it did。

 And so it's going to be a four column matrix of means。 And sorry， a four rows and two columns。Okay。

 so that's how I get the means。And now I decide which of the rows get which means。 So Im going。

Pick a random sample from the numbers  one to 4。 I want 100 of them because I've got 100 rows and replace equals 2。

 So which is going to say which observation belongs to which cluster。

So now simply add the appropriate mean to the appropriate rows。

 so this is a kind of typical R vector operation that's nice and tricky and effective。😊。

So x mean is a four row matrix， but I'm indexing it with 100 indices。

 so that'll produce 100 row matrix with two columns so it'll pick out the right the right mean for each row。

 and I just add it to the original x。😊，Okay， and now make a plot。And there you have it。

 So there's a plot X。 plots the first two coordinateor the only are two coordinates。 And。

 and I give it the color， which is， I give it which， which is for each point is a number  one to 4。

 And it tells it which cluster it belongs to。And it just uses the colors one to four。

 which are black。Red， green and blue。 And so these are the data and there we see the clusters that I've imposed。

We know the clusters， but now we're going to hand these data to hierarchical clustering and not tell it what the clusters are。

 and it's supposed to find them automatically and we'll use the K means algorithm。Okay。

 we're going to tell it they're forecast clusters yet。If we told there were three cluster。

 we would probably find two of the clusters and then merge two of them together。

Okay so here we go we call k means and we tell it four clusters and we tell it to do 15 random starts。

 random starts are cheap if you remember K means clustering starts with a random start for where the clusters are and of course if you pick a bad random start it might find you a bad solution unlikely in this case but that's what we do anyway。

And。We can print out the result and it prints out a number of things for you。

It prints out the cluster means it's gonna be four of them， because they're four clusters。

 The cluster vector。 that's the assignment of each point to the cluster that's clusters that it found。

 And then there's some summaries of the cluster。 So the within cluster， sum of squares by cluster。

 They four clusters。 So that's the sum of squares within each cluster。

 that sum of squares deviations of each point around its cluster mean。And then。

 and this is perhaps a more interesting。 the between summer squares to the total summer squares。

 So this is， in a sense， this is like there R squared for clustering。

 It's a percent cent of variance explained by the cluster means。 and it's pretty high。

 So it suggests it's done a good job。 And then it tells us what the the。

Other components on the cluster object are。Okay， so now we're going to plot the data。嗯。

And there it is， and。We've identified the clusters that it found。

 So we plot the data with big circles。For each point。

And the coloring year is not our original cluster。 when we generated the data。 we， we， we， we。

 we made clusters。 This is the These are the cluster assignments found by the K means clustering algorithm。

So to see how Willer did with in terms of the original known clusters。

 we can include those points that's how I made these circles a bit bigger。

 so I put the points inside。And well， what you see now is that we have a color mismat。

So we we named the clusters 1 to4 in some order， the Ka meanss clustering algorithm found four clusters and it named them one to4。

 but of course the ordering is arbitrary， so it picked a different order。

So we can look at the clusters here and just reassign the colors。

 which is what I'll do in the next line。And now， you see。This is a more useful plot。

 So we see the outer circles are the K means clustering cluster I D and the inner points are original cluster I D。

 And you can see the mismatches。 So there's a black point。

 which actually belonged to this cluster from the original data， was。

Its signed to the green cluster year。And yess a， a blue point that originally belonged to this cluster has been assigned to the black point。

 quitete reasonably， of course， because it's much closer to these as it turned out than than not。

So that's Ka means clustering for you and just some nice graphical techniques for。

For having a look at the at the results， if especially if the data ist two dimensional。

 that's easy to do。
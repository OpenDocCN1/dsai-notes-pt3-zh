# TrevorHastie／RobertTibshirani《统计学习导论｜An Introduction to Statistical Learning》中英字 - P67：P67 StatsLearning Lect12c 111113.zh_en - GPT中英字幕课程资源 - BV1jN4y1Y7JR

Okay， well， welcome back。 the second method of this section is clustering。



![](img/279576bbae9e9097ca3dbeb3a30212dc_1.png)

Whi refers to a broad set of techniques for finding subgroups or clusters in data。

 so we're trying to segment or partition the data into subgroups that are similar to each other。

 and of course we'll have to define what we mean by similar or different in order to do the partitioning and in a lot of cases the way we decide to cluster the way we decide on what's similar different depends on the context。



![](img/279576bbae9e9097ca3dbeb3a30212dc_3.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_4.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_5.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_6.png)

So how does principal components analysis which you just discuss， how does it contrast to clustering。

 Well PCA， as we've seen， looks for a low dimensional representation or view of the data that explains a good fraction of the variance right so we saw the PCA plots and we from it we drive new variables which could be used for other methods like supervised learning。



![](img/279576bbae9e9097ca3dbeb3a30212dc_8.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_9.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_10.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_11.png)

Clasroom， on the other hand， looks for homogeneous subgroups of the observations。



![](img/279576bbae9e9097ca3dbeb3a30212dc_13.png)

So not only for variance but is looking for similarity among observations。



![](img/279576bbae9e9097ca3dbeb3a30212dc_15.png)

For example， if we're trying to try to do a segmentation of a market， suppose for。



![](img/279576bbae9e9097ca3dbeb3a30212dc_17.png)

Each of a number of customers weve measured things like their income， their occupation。

 how far live to the closest urban area and so forth。

 and we we want to segment them or group them into customers that are similar with regard to these features and why do we want to do that because maybe if they're similar with regard to these features。

 then the kind of advertising we use for that subgroup will be important。

 So we use a certain kind of advertising for one subgroup like maybe young males who have a lot of money。

 one subgroup， another subgroup might be like me young okay？



![](img/279576bbae9e9097ca3dbeb3a30212dc_19.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_20.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_21.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_22.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_23.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_24.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_25.png)

Another group might maybe be。Housewives who in their 50s who their children have grown up and they like to travel。

 for example， who may want to advertise a different way to that subgroup。



![](img/279576bbae9e9097ca3dbeb3a30212dc_27.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_28.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_29.png)

So that the task of segmenting that kind of population is a key application of clustering。



![](img/279576bbae9e9097ca3dbeb3a30212dc_31.png)

So we're going to talk about two clustering methods in this section。

 although there are lots more as in most areas of statistics， there's many。

 many ways of doing things， but the two most important methods which we'll talk about are K means clustering。



![](img/279576bbae9e9097ca3dbeb3a30212dc_33.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_34.png)

In which we first will predeeffinine K the number of clusters。

 and then we have we'll see there's a way of grouping the observations into the K groups。 Then。

 of course，'ll have to define what K is。 this number of subgroups。

 and that's going to be an important and hard difficult choice。



![](img/279576bbae9e9097ca3dbeb3a30212dc_36.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_37.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_38.png)

And the second method is called hierarchical clustering。

 which we don't pre specifyify the number of clusters K， but rather we do。



![](img/279576bbae9e9097ca3dbeb3a30212dc_40.png)

We group the data in all numbers of clusters and it's done in a hierarchical aloorative fashion。

 and this is nice because we get to see the clustering for all numbers of clusters k。



![](img/279576bbae9e9097ca3dbeb3a30212dc_42.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_43.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_44.png)

Then let's start with the simplest method K means clustering。Before we describe it。

 let's see an example of the result of Ka means's clustering， so this is some simulated data。



![](img/279576bbae9e9097ca3dbeb3a30212dc_46.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_47.png)

And。It's been simulated basically in two groups。

![](img/279576bbae9e9097ca3dbeb3a30212dc_49.png)

Which are。The upper group was two features and there's a group at the top。

 some space in between and a group at the bottom。

![](img/279576bbae9e9097ca3dbeb3a30212dc_51.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_52.png)

And now when we apply K means clustering and we have to pre specify k， again。

 we'll see the procedure in a few slides。

![](img/279576bbae9e9097ca3dbeb3a30212dc_54.png)

But when we press up pre specifyify k equals 2 and we run the cluster algorithm， it produces。



![](img/279576bbae9e9097ca3dbeb3a30212dc_56.png)

The the groups indicated by the two colors， blue and gold。 So with K equals 2。

 it's found approximately the right clusters， although you might argue， well。

 does this point actually belong in the upper cluster rather than the bottom cluster。



![](img/279576bbae9e9097ca3dbeb3a30212dc_58.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_59.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_60.png)

And that's not something which you can answer just in a quantitative way， that's a subjective call。



![](img/279576bbae9e9097ca3dbeb3a30212dc_62.png)

In any case， it seems to have found the two clusters pretty correctly。

 but if I would have specified a k equals 3， it would be forced to find three groups and the three groups came means clustering found or indicated here by the green。

 the blue and the gold。 So what's done is it's broken up this apparently homogeneous cluster into two clusters。



![](img/279576bbae9e9097ca3dbeb3a30212dc_64.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_65.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_66.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_67.png)

Similarly with k equals 4， it finds the blue， the orange， the purple and the green， right。



![](img/279576bbae9e9097ca3dbeb3a30212dc_69.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_70.png)

It's broken up。 this bottom cluster looks like can three clusters。

 although it's borrowed some points from the top right there。



![](img/279576bbae9e9097ca3dbeb3a30212dc_72.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_73.png)

So you can see that the effect of k means clustering。 Well， first of all。

 you can see the effect of K is really important， because you use K to be too large。

 is's going to be forced to break up groups like this one， which。



![](img/279576bbae9e9097ca3dbeb3a30212dc_75.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_76.png)

Are fairly homogeneous。What's also interesting Rob is that variables that are somewhat responsible for clusters。

 like， for example， the second variable that we have over year also tend to have high variance because you know if they separate the data in clusters there tends to be variance So there's some connection between principal components in clustering in the more abstract scene so let's actually drill down in the details of K means clustering。

 Well first of all， we have to define sannotation for clusters or sets。

 So we'll call them c1 through C and there' are sets of indices of the observations。

 So the indices are1 through n， those are n observations。

 each of these C's is going to be a subset of one through n。

 and the subset is it's going to a partition of one through n。



![](img/279576bbae9e9097ca3dbeb3a30212dc_78.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_79.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_80.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_81.png)

Now， as we want to get formalistic， we'll say， well， the Cs， their union is one through n。

 So if if we concate them all together， they make up one through n。

 So there're a partition of one through n， and there's no intersection。

 So there's no overlap between the clusters。 So that's just a fancy way of saying were we're going to break up the points one through n into K groups which are non overlapping and cover the whole set。



![](img/279576bbae9e9097ca3dbeb3a30212dc_83.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_84.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_85.png)

Okay， and again， if the Ih observations in the K cluster。

 then I will be a member of the indices for group K。



![](img/279576bbae9e9097ca3dbeb3a30212dc_87.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_88.png)

O。

![](img/279576bbae9e9097ca3dbeb3a30212dc_90.png)

So again， we want to somehow find the partition C1 through CK， which is a good clustering。

 well what do you mean by good clustering， okay K means clustering defines good clustering to be one of which the within cluster variation is small。



![](img/279576bbae9e9097ca3dbeb3a30212dc_92.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_93.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_94.png)

OkaySo let's get back to this picture。If you ask me， well， divide this into， say two groups。

 well the notion of K means is going to use is say， well。

 I'm going to find two groups so that within each group， like within the gold。

 the variation is small within the group so that the points are close together。

 Similarlyly for this group， the points are close together。



![](img/279576bbae9e9097ca3dbeb3a30212dc_96.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_97.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_98.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_99.png)

It's kind of a very intuitive definition。Let's call the wind cluster variation of the cluster of C。

 K WCV for wind cluster variation of C， K。 iss the total variation。 For example。

 we could use square distance。

![](img/279576bbae9e9097ca3dbeb3a30212dc_101.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_102.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_103.png)

In the two directions， matter of fact， most of the time。

 we will use square distance for Cam means clustering。



![](img/279576bbae9e9097ca3dbeb3a30212dc_105.png)

So then， if we put it all together， we define the variation within a cluster to be WCV of CK。



![](img/279576bbae9e9097ca3dbeb3a30212dc_107.png)

We want to find well the total variation。

![](img/279576bbae9e9097ca3dbeb3a30212dc_109.png)

Adding up over all clusters is here。And we want to find the partitioning C1 through ZK to minimize the total within cluster variation。



![](img/279576bbae9e9097ca3dbeb3a30212dc_111.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_112.png)

嗯嗯。So we're going to assign the end data points to k clusters so that the total within cluster variation summed up over the k clusters is as small as possible。



![](img/279576bbae9e9097ca3dbeb3a30212dc_114.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_115.png)

So I said this on the previous slide， but here's in detail。

 we normally define within cluster variation to be the Euclidean distance。

 the pairwise square distance between each pair of observations in the cluster。



![](img/279576bbae9e9097ca3dbeb3a30212dc_117.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_118.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_119.png)

Add it up over the P feature so that this is the Euclidean or squared distance between observations I and I prime。



![](img/279576bbae9e9097ca3dbeb3a30212dc_121.png)

And we sum it up over all II prime in the cluster， so now this is the total paralyz distance of between every pair in the clusters CK。



![](img/279576bbae9e9097ca3dbeb3a30212dc_123.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_124.png)

And we're going to。Minimize the total of this over K， a total variation over all clusters。



![](img/279576bbae9e9097ca3dbeb3a30212dc_126.png)

And that's。Here it is。 So here's our optimization problem。 Now。 Here's the within cluster variation。

 and we're going to。

![](img/279576bbae9e9097ca3dbeb3a30212dc_128.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_129.png)

We're going to find the clusterings you went through the scale that minimizes that。



![](img/279576bbae9e9097ca3dbeb3a30212dc_131.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_132.png)

Yeah。So we have a criterion， but let's actually talk about the K meansan algorithm and then we'll sort of circle back and see why minimize the objective on the previous slide。



![](img/279576bbae9e9097ca3dbeb3a30212dc_134.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_135.png)

So how Ka means clusters works。 Well， it's got the word means in it。

 So it's going to use a mean somehow。 So it' it's actually an alterating algorithm。 first of all。

 we assign。

![](img/279576bbae9e9097ca3dbeb3a30212dc_137.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_138.png)

To each observation， a cluster from 1 to K。 So remember K is fixed， we have to decide ahead of time。

 I'm going to pick k equals for example 2 or K equals3。

 and we'll worry later about how to choose K an important value。 but let's fix K for the moment。

 So if each observation is assigned to a cluster run through K。



![](img/279576bbae9e9097ca3dbeb3a30212dc_140.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_141.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_142.png)

And then we have two steps which we alternate back and forth。



![](img/279576bbae9e9097ca3dbeb3a30212dc_144.png)

For each of the K clusters on the one hand， we compute the centroid。

 that's the average value in each feature of all the points in the centroid in the cluster。



![](img/279576bbae9e9097ca3dbeb3a30212dc_146.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_147.png)

Okay so it's the mean of in the vertical and horizontal direction of the points in that cluster。



![](img/279576bbae9e9097ca3dbeb3a30212dc_149.png)

So having compared the centroids for each of the clusters， on the other step。

 we assign each data point to the closest centroid。



![](img/279576bbae9e9097ca3dbeb3a30212dc_151.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_152.png)

And then having done that。

![](img/279576bbae9e9097ca3dbeb3a30212dc_154.png)

We have。A new set of cluster assignments C1 through ZK， we go back and we compute new centroids。



![](img/279576bbae9e9097ca3dbeb3a30212dc_156.png)

Use the new centroids， you complete new assignments and we alternate it back and forth until hopefully this thing settles down。

 and the solution is the K means cluster。

![](img/279576bbae9e9097ca3dbeb3a30212dc_158.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_159.png)

The solution we want is the assignment appoints to the groups。



![](img/279576bbae9e9097ca3dbeb3a30212dc_161.png)

So。Let me actually。

![](img/279576bbae9e9097ca3dbeb3a30212dc_163.png)

I'm going to show an example。 well let's see example and then we'll go back and see why that algorithm actually minimizes the objective that we wrote down。

 So here's an example， actually the same example we had before。



![](img/279576bbae9e9097ca3dbeb3a30212dc_165.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_166.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_167.png)

Here's our data， okay， again， it's unlabeled data right， and we've chosen k equals 3。



![](img/279576bbae9e9097ca3dbeb3a30212dc_169.png)

So in the first step， we're going to assign points at random to clusters。

 so we' have indicated by the colors。

![](img/279576bbae9e9097ca3dbeb3a30212dc_171.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_172.png)

And so each point is assigned cluster to a different color and you can see the assignment the grouping is not very good yet in other words。

 we like we're thinking that this is one group， and this is another group。

 but we don't we're nowhere near that clustering at this point。



![](img/279576bbae9e9097ca3dbeb3a30212dc_174.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_175.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_176.png)

The first step we compute the centroids， right so that these are the average of the the horizontal vertical direction of all of all the points in the gold。



![](img/279576bbae9e9097ca3dbeb3a30212dc_178.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_179.png)

Green and blue。Groups， and then here the centoids are pretty much on top of each other because the assignment was random。

 So there's no real grouping yet。

![](img/279576bbae9e9097ca3dbeb3a30212dc_181.png)

But note， don't fear the Ka cluster will work its way to a good solution。

 So now we take the centroids and we。

![](img/279576bbae9e9097ca3dbeb3a30212dc_183.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_184.png)

We find the closest points to each of the centroids。 So each point is， we ask each point。

 are you closest to the green， the purple or the orange centroid。



![](img/279576bbae9e9097ca3dbeb3a30212dc_186.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_187.png)

And now we color the points accordingly， so this is the partitioning step。



![](img/279576bbae9e9097ca3dbeb3a30212dc_189.png)

So even though those first three centroids were pretty much on top of each other。

 they weren't exactly and so that defines a fairly nice partition of the data already。

 Yeah it' it's on an almost almost perfect job in terms of well you see we'llll get to the final iterate and then given this new assignment we we find the centroids again but all the centroids are going to move a lot now right because look who the points are so for example the average of these gold points is way up here so here's the new gold centroid。

 new purple new green now the centroids are sitting really right in the middle of the clusters。



![](img/279576bbae9e9097ca3dbeb3a30212dc_191.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_192.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_193.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_194.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_195.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_196.png)

And the algorithm will going continue and make a few refinements。

 and here's the final cameian solution for this example， very intuitive algorithm。So。



![](img/279576bbae9e9097ca3dbeb3a30212dc_198.png)

Yeah。Let's go back。 Maybe they have the objectiveive function。

 which is the total within cluster variation。 we want to minimize。

 right you want to find the partitioning that minimizes this within cluster variation。 Well。

 get the question is， have we does this algorithm that we wrote down， does it achieve that。



![](img/279576bbae9e9097ca3dbeb3a30212dc_200.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_201.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_202.png)

But you can actually see that the algorithm will always decrease the value of the objective of each step。



![](img/279576bbae9e9097ca3dbeb3a30212dc_204.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_205.png)

And you might think about why that is。Well， the key to it really is that。



![](img/279576bbae9e9097ca3dbeb3a30212dc_207.png)

You can write the variation， the pairwise variation as the variation around the， the the。

Component wise means。 So， and this is really the key to k means clustering。 You think about it。

 we really didn't。 We didn't care about the centroid。s All we cared about what was the clustering。

 Well， K means clustering is done is it's it's it's。



![](img/279576bbae9e9097ca3dbeb3a30212dc_209.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_210.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_211.png)

It's put in there， it's changed this。

![](img/279576bbae9e9097ca3dbeb3a30212dc_213.png)

To an equivalent expression of all the centroid。And now Caman's clustering finds both the the component。



![](img/279576bbae9e9097ca3dbeb3a30212dc_215.png)

C13 K as well as the centroid x bar。

![](img/279576bbae9e9097ca3dbeb3a30212dc_217.png)

What it does at each step is it minimizes over CK on the one hand or minimize over cent on the other hand。

 and each of those steps is going to decrease this criterion and hence decrease this criterion。



![](img/279576bbae9e9097ca3dbeb3a30212dc_219.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_220.png)

So if you have centroidoids。Then。When you you come to update the assignment of each point。

 it's going to go to the group for which。

![](img/279576bbae9e9097ca3dbeb3a30212dc_222.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_223.png)

This distance is smallest for fixed entriess and on the other hand if all the assignments are fixed we know that the sample mean is minimizes the sum of squares and so that's why each of those tips necessarily makes the criterion go down So this is very sick we start it off with the problem involving one set of variables we it we added another set of variables which we think it make it harder。

 but it actually makes it easier right because now because when we do the joint optimization over both sets of variables。

 we get to the answer for the ones we care about the question。



![](img/279576bbae9e9097ca3dbeb3a30212dc_225.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_226.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_227.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_228.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_229.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_230.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_231.png)

So that's just the detail of the previous figure， which we talked about。 Now， oh， sorry。

 I missed a point here， which is that。

![](img/279576bbae9e9097ca3dbeb3a30212dc_233.png)

It's not this algorithm although gives you a local minimum。

 it's not guaranteed to give a global minimum。

![](img/279576bbae9e9097ca3dbeb3a30212dc_235.png)

Why not？ Well， what does that mean， Rob， a local minimum local minimum means that。



![](img/279576bbae9e9097ca3dbeb3a30212dc_237.png)

Well， the point is is that you could start the algorithm from。



![](img/279576bbae9e9097ca3dbeb3a30212dc_239.png)

Okay， okay， the local medium my guess means and calculus it means that the derivative of the function is0。

It doesn't mean that it's the lowest point of the function， so if a function is not convex。

 you can have a place where the derivative or there's a valley which is flat。

 but it's not the lowest value in the whole function。



![](img/279576bbae9e9097ca3dbeb3a30212dc_241.png)

So this algorithm will get to a local minimum we'll get to a place get to a value of the function we're trying to minimize but it won't be the lowest value necessarily。

 so we can think of this this function that we're trying to optimize as being like a big valley but it's got lots of little subvals or little ponds or whatever and you know any minimum is one of those and we can get stuck in one of those right so in the organization world。

 the idea this idea of a convex function， which is basically is only one valley。



![](img/279576bbae9e9097ca3dbeb3a30212dc_243.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_244.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_245.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_246.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_247.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_248.png)

So if you find a minimum， it's a global minimum。But this function is not convex， in other words。

 it can go up and down and have more than one valley。

 and the Camean algorithm will land you in a valley。

 but not necessarily the lowest valley because the function is not convex。



![](img/279576bbae9e9097ca3dbeb3a30212dc_250.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_251.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_252.png)

So actually here's an example， this for the same did。

 here's an example where we start the algorithm from six different starting configurations。 Remember。

 our starting configuration was we signed each point at random to one of the clusters。



![](img/279576bbae9e9097ca3dbeb3a30212dc_254.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_255.png)

And this is actually a good thing to do with Kam clustering is since we're not guaranteed to get the global minimum。



![](img/279576bbae9e9097ca3dbeb3a30212dc_257.png)

We start the algorithm at more than one place and we just examine the value of the criterion at the end in each case。

 remember starting in the algorithm was this random assignment of points to the number of clusters you're using。



![](img/279576bbae9e9097ca3dbeb3a30212dc_259.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_260.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_261.png)

So when we start the algorithm from different places we get actually quite different solutions。

 don't worry about the fact that the colors are chosen differently like these are gold and these are green。

 that the coloring is arbitrary， but the partitioning is quite different and we typically we pick the lowest value there's see this guy。

 well these looks like we got three different solutions three or four different three different solutions right I guess the ones you colored in red at the top all have exactly the same distance so they actually all the same the colorings are different but as Rob said the colorings arbitrary so these solution。

 these four panels give us the solution with lowest but the top left and the bottom right are actually different solutions again right。



![](img/279576bbae9e9097ca3dbeb3a30212dc_263.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_264.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_265.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_266.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_267.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_268.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_269.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_270.png)

![](img/279576bbae9e9097ca3dbeb3a30212dc_271.png)

Okay。So that's K means clustering， and we'll actually talk a little bit about the end how to choose K。



![](img/279576bbae9e9097ca3dbeb3a30212dc_273.png)

It would also be an issue for hierarchical clustering， which is a topic of our next segment。


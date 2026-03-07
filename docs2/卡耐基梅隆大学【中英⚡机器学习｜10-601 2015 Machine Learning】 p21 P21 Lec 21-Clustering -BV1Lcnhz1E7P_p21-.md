# 卡耐基梅隆大学【中英⚡机器学习｜10-601 2015 Machine Learning】 p21 P21 Lec 21-Clustering -BV1Lcnhz1E7P_p21-

Actually a nice chapter， a nice reading for plastering is actually the chapterpt 14。

3 of Haran improvement。 X is available online， which is nice。😊，And also， if you want to read more。

 you can also about more foundational。 You can read a chapter that wrote recently to Panjati。Okay。

 cool， so let's get started。Okay， so what is clustering so well。

I'm sure you guys know many applications of clustering。 So right， first of all。

 even before talking about applications， what it is informally。

 So informally is the goal when doing clustering is to somehow automatically partition unable data into groups of similar data points。

 So we only have unablebeled examples and we want to somehow automatically partition。

 So that similar points get into similar parts。😊，Okay， and why would you want to do that。 Well。

 there are multiple reasons。 For example， we might want to automatically organize large amount of data。

 or we might want to just understand hidden  structure in data。

 which is a bit more like unsupervised learning。 The second goal。

 or we might just want to do clustering as a preprocessing step for further analysis of the data。

Right， we might for example， you might want to， for， for an example before for visualization for。

 So people， if you want to visualize data， might want to do clustering because it might be easier to visualize that。

Okay now in terms of applications， I mean there are many。

 many applications it really I mean clustering really comes up in all field so for example just to mention a few you might want to cluster news articles or webage or search result by topic or you might want to cluster protein sequences by function or genes according to where expression profile K or might want to cluster users in a social network according their interest right and this is actually this is a popular topic these days called community detection。

😊，Okay。Or you might want to maybe cluster customers， according to their purchase history。

 I have to do better decision later on。Okay， like better pricing and so on。

 Or you might turn to cluster galaxies on nearby stars， for example。

 by using data the slowloane digital sky survey。 Okay， so many， many applications。 I mean。

 these are just the examples of applications， but really clustering comes up everywhere in all fields。

 And so it's important to understand the type of algorithms。😊，Do we have a clustering？O。

 and as I already mentioned， So actually， Tom already talked about clustering on March 4。

 but he talked about a very， very specific way of doing clustering by EM algorithm。

Which is a nice algorithm in general， but doesn't have approval guaranteeees。

 And what about the derivation that he talked about was very specific to mixture agaians。Okay。

 or probabilistic model。 And so today， we'll talk a bit more algorithmically about clustering and we talk both about kind of objective based clustering。

 So or clustering algorithms。 So we output put the partition of the data。

 and we'll also talk about hierarchical clustering。😊，Okay， cool so。

Let me start with objective based clustering。 So I'm gonna start with a little bit of a general overview of the objective based clustering case。

 And when I'm gonna focus on the K means algorithm or the K means objective。

 which is probably the most popular objective used in machine learning and also machine learning。

Okay， but what is the problem more generally， So we have a set as of endpoint。

And we also have a distance or the matrix， a dissimilarity measure specifying the distance between pairs of points。

Okay， this could be something， for example， given by the domain。

 like if we want to cluster protein sequences， we might have added distance。

 so the domain experts think its a additional distance。

 or it can be the number of keywords in common if you want to do maybe say， news article clustering。

Or it can be something based on the level coefficient if you want to do image clustering right。

 it can be something given by the main experts， but it can also just be the natural notion of distance if the points are embedded in R D。

 right， So for example， the are point in equilibriumidean space。

 where we can just define the distance between points to just be distance in the equilibriumucidean space。

Okay， and so the goal traditionally， we to objective based clustering is stop with a partition of the data。

 And now there are many types of objectives that people have considered。And let me mention one。

 the most popular one is a k means objective。 Okay。

 And here I'm writing the definition a bit more generally。

 So I'm going to specialize in a second for the Crideion case。

 which is the most popular one is the machine learning。

 But the definition can be written more generally。 And so here more generally。

 we just have as input as as of endpoint and the distance function。

Satisfying set triangle inequality。 And when the goal is to output centers， C1 C to C K。

 which might not be the data points themselves。 So to output centers。

And a partition of the point into clusters in a way to minimize sum overall point of a square distance to the nearest center。

Okay， we thought we want to do inter the came is objective。

Right want to just output a partition like this one here。 And for each part。

 you want to output a center。 Each point is assigned to nearest center and went on to minimize some of the square distances from some broad point of the square distances to very corresponding center。

Yeah， so that's the K means and here's the sum of the square distances。

 This is why using machine learning， another objective。 let me mention a couple more objectives。

 So one another one is a so called keymeian where it's the same as k means except an hour want to minimize sum of the distances of the points to the corresponding center。

😊，Yeah， so it's just linear as opposed to quadratic here。 the penalty。 Okay。

 this is more widely used in like O operations research and theoretical computer science。

 maybe in the context of say acid location， This is more commonly used。

 This is more commonly is the machine learning and other objectives， like the case center objective。

Where the goal is to find the partition of the data and want to minimize the maximum radii。Okay。

 and there are many others。 I mean， some clustering。

 the goal is to find the partition in order to minimize some of the in track clusters distance。

 inside cluster distances and so on。 but these are the most popular ones。And in particular。

 in machine learning， the most popular one is called gaminging subjective。 I be subjective over here。

Okay， and let me just specialize to to what。People like mostly machine learning。

 name meet the cameians， name me the Ouclan cameians problem。O， so in the Eide Cam in case。

 we assume that the data point are point in RD in the Eide the dimensionsal space。😊。

And so that's the input。 So we have an input a set of points。

 We now leaving the and dimensional space。 and we also have input the number of target clusters。

 We are looking for K for now we are given K。 We can discuss later。 where is K coming from Okay。

 so we have also input the number of target clusters。

 And then the goal is exactly as I mentioned earlier， is stop with K centers， C 1 C2， C K。

 They can belong to they can be any point in R D， not necessarily the input points。😊。

OkayAnd then what we want to do is just basically to assign each point to close the center out of your state centers。

 And we want to find the centers， a set of centers to the property。 But if we sum over points。

 the sum of the distances to where square distances to where corresponding centers is minimized。

Right， so it's the case subjective。 It's clear to everyone。I'm sure you have you all seen。

 came subjective。Yes。😊，It's on probably yes because it's very popular。 It's widely used。Okay。

 so that's the objective。 And so right if you think about it actually， right what we do here。

 we assign each point。 right， in this format I'm writing here is basically given set of centers C1 C to C K。

 We assign each point to its nearest center。 Very， very natural， right。😊，And then if we do so。

 basically。 So given a set of centers， maybe O， maybe a center would be。

 Let me just put some centers over here。Let me， right， so if we do so if we assignage point。

 it's cross the center， right， So when we have So when we v the center， oops。Right。

 so maybe let's just say that this are my center like center C1。Center C 2 and center C 3。

 for example， right， If I have here free clusters， right and I do assign the assign this assignment of each point to is closer center。

 then what I get is this type of vronnet partition， right。

 So when I'm gonna partition the space in this， in this way。

 like exactly like each point is assigned to its closer center， right。

 And this is called the von partition。 Okay， and you can， if you think about it。

 you can easily verify But each of the part is comebacks。😊，Okay。

So try to do this natural assignment or assignage points across the center we kind of partition the space into compact cells。

 and this is called the vonnet partition。😊，Okay， so that's the k means clustering objective。

 Now you might wonder。 can we， I mean， this what want to do right， We have is input and data points。

 They live in R T。 We want to find a set of centers to max to minimize Ka means clustering costs for those set of centers。

Okay， now， what do you guys think can we solve this problem， I mean， ideally。

 we don't to solve this problem optimally， right once we define it。Right。

 that will be I a simple normal time。Right， and what do you guys think。

 Do you think we can solve this problem in problem time。I mean， polynomial in n。

 the number of data points， D， the dimension and K， the number of target clusters。

The number of clusters we are looking for。对 guys。Do you think we can actually solve this problem。

I mean， this objective has been considered for many， many years， actually。

 in machine learning and signal processing。😊。
# 【精译】蒂宾根大学《神经数据科学》-p11-11-单细胞转录组学--BV1DEYozGEMW_p11-

🎼。

![](img/df8deda2305ec0c1cde4142db300e444_1.png)

🎼，Welcome to our next lecture in neural data science。In the summer term，2021， today。

 we will focus on a different data modality from what we have discussed so far。Today。

 we will talk about genetic data in neuroscience and focus on single cell transcriptomic measurements。

Before we talk about data analysis problems。Related to the data modality， we would like。

 I would like to briefly explain what single trans cell transcriptomics is。



![](img/df8deda2305ec0c1cde4142db300e444_3.png)

So as most of you will know， in the cell。The from the DNA。

The process of transcription generates mRNA from which the process of translation makes proteins。

So in single cell transcriptomics， we focus on measuring the mRNA content of individual cells。



![](img/df8deda2305ec0c1cde4142db300e444_5.png)

This， in many cases， can tell us about the cellular identity， the cell types。

 the kind of proteins that are transcribed or translated later on in the cell。

 So tell us a lot about the cellular identity。Over the past decade。

 a number of different approaches have been suggested to obtain these measurements from individual neurons。

Or individual cells， also in other parts of the body。These roughly work all like this。

 So in many of these approaches， the first step is to dissociate the tissue such that the individual cells are really present as individual cells in solution。

Then these individual cells are captured。There' so membrane it's lied。

And there's a process of reverse transcription that takes the mRNA and reconverts that back into C DNA。

The DNA content of the cell is then amplified。And prepared for， for sequencing。

With next generation sequencing approaches， these can then be sequenced relatively quickly。

 and then we do analysis。One example of this process can be seen here where cells enter such a microfluidic device from above。

嗯。And in， and there are also barcodes that are added to this。And then in。

 and they are immersed in oil droplets。And in these oil droplets。

This process of membrane  lilysis takes place such that the mRNA contents of an individual cell are combined with a barcode。

 such that the identity of the cell can be determined and are then later amplified and sequenced so that we get in the end。

 expression levels of many different genes in these cells。

The range of approaches that is available to do that today is actually quite large。

 and they range from rather slow approaches。

![](img/df8deda2305ec0c1cde4142db300e444_7.png)

Such as micropiing。

![](img/df8deda2305ec0c1cde4142db300e444_9.png)

Or they a capture micro dissection to very fast approaches。

 such as the my micro droplets or microfluidics approaches that I've mentioned already on the last slide。

The advantage of such micro pipepeing approaches is that one can use them on pretty much any tissue and that one can really target individual cells that one is interested in。

 So， for example， if in a certain。

![](img/df8deda2305ec0c1cde4142db300e444_11.png)

![](img/df8deda2305ec0c1cde4142db300e444_12.png)

Part of the brain， you mark with a fluorescent marker。 You mark a subpopulation of cells genetically。



![](img/df8deda2305ec0c1cde4142db300e444_14.png)

Micropipettting would allow you to target these fluorescent cells。



![](img/df8deda2305ec0c1cde4142db300e444_16.png)

Specifically and， and， and thus enrich or select the sub population。嗯。Before sequencing them。

The other hand， of course， it's quite time consuming on the。

And the other extreme of approaches are the micro drops approaches。

 like the one that I showed you in the last slide。

![](img/df8deda2305ec0c1cde4142db300e444_18.png)

These are super fast， also very cheap。 One can look at really large numbers。 So hundred of today。

 hundreds of thousands of cells for an affordable price。But on the other hand。

 one doesn't have the same amount of control over what one looks at。

Sigal cell transomics is a very fashionable topic in recent years， also in neuroscience。

 So if you look at the number of studies over the past 20 years or so that that mentioned the term。

 you can see a very sharp rise in， in recent years。

And it's not only a a sharp rise in the number of studies， but also per study。

 the number of cells that are sequenced goes up really rapidly。 So while only like 4 or。

 five years ago， it was quite common to her studies with a few thousands of cells。Today。

 many studies report cell numbers as high as a few hundred of thousands or cells or even millions。

For example， maybe some of the most prominent and also most beautiful visualizations in the field come from two studies from the Stanlinson lab。

Where they looked at the molecular architecture of the mouse nervous system。

 first in the adult animal here。 and then later on also during development。

They sequence cells from a variety of different places in the nervous system， including the brain。

 but also including the spine or even。

![](img/df8deda2305ec0c1cde4142db300e444_20.png)

![](img/df8deda2305ec0c1cde4142db300e444_21.png)

The enteric na nervous system in the digestive tract。They had。

 in total about 50000 of cells in their in their study and then went on to create such beautiful visualizations that really show you the diversity of cells in the tissues。

In a more recent study， they added a developmental dimension to that and looked at how these different islands and continents emerged during the development of the animal。

So in this， in this beautiful visualization， you see here a big neuron continent。 and you see as。

 as altitude lines in that neuron continent， you can see the different developmental stages。😊，Now。

 what are common data analysis tasks and what are the data structure that one meets when one starts to work with single cell transcriptomic measurements。

It's a bit different than what we have dealt with so far often， because in spike trains or in。Also。

 in two photon imaging data， time is always a dimension that really orders。

Th so dimensions or features of the data。That I close by。In， in terms of their， their index。

 index in the data matrix， they are also close by in time。

 So there's really like a natural order in time。 The same is true for images。 So for， for example。

 compute a model that relates spike trains to images。 There's also an intrinsic spatial dimension。

That， that defines neighborhoods。For single cell transcriptomics data。

 this is not necessarily the case。 So the， the feature dimension in this case is， is genes。



![](img/df8deda2305ec0c1cde4142db300e444_23.png)

![](img/df8deda2305ec0c1cde4142db300e444_24.png)

So in the mouse and human， we have about 25000 genes that we're working with。

 for which we can measure the expression levels， but there's no natural ordering of these genes so that the columns of the data matrix can be。

 can be permuted。 So， for example， computing convolutions on that data matrix doesn't make much sense。



![](img/df8deda2305ec0c1cde4142db300e444_26.png)

The other dimension of the data matrix is often cells。



![](img/df8deda2305ec0c1cde4142db300e444_28.png)

Can start with only 10 K cells。 Often， it's nowadays much more。But as we will see。

 it's a very sparse matrix that doesn't have a lot of entries。



![](img/df8deda2305ec0c1cde4142db300e444_30.png)

So depending on what the numbers。Are here precisely。 So if we are at the low end。

 because we have a rather small study， but then we measure 2 k thousand25000 genes。

 We're in the range that the number of samples is really smaller than the number of feature dimensions。



![](img/df8deda2305ec0c1cde4142db300e444_32.png)

![](img/df8deda2305ec0c1cde4142db300e444_33.png)

But on the other hand， nowadays， we can also get into a better sampling regime if we just measure many more cells。

Typical data analysis tags that that are done with this data matrix and that that follow initial data acquisition and then to perform quality control and some pre processingces so that one can really work well with the data and to remove technical artifacts。

Then a very common step is to do what you've just seen on。

 on the last slides is to do data visualization for exploratory analysis。And finally。

 a very common step is to try to identify cell types， So to perform a sort of clustering。Of course。

 one can also do other things with transcriptomics data。 One can， for example。

 look at developmental imagesages and order cells in according to this pseudo time one could try to relate。

Transcriptomic measurements， two more physiologically inspired models。 But for today。

 we will focus on these basic tasks。In many cases or in in many experimental paradigms。

 this data matrix comes as the so called U M count UMI count matrix。

 U MI stands for unique Mocular identifier。And these are tags that are added to the DNA fragments after reverse transcription to identify the input DNA molecule。

This is added before the amplification， and it can serve to reduce the amplification bias。

 If you look into the， the technical literature on how these experimental techniques work。

 there are quite a number of sources of potential biases that one needs to deal with。

 And these U M I are one experimental solution to that problem。

The data that we will look at in the examples or in in many of the examples today are from this paper by Kenneth Harris。

And colleagues that looked at hypopocampal neurons in C A 1 and the diversity revealed by single cell transcriptomics。

Okay， let's look at our three data analysis tasks and start with the first one pre processing。

 So first， if we have a data matrix or we take the data matrix from the study by Kenharas。

 then we find that we have in total，3600 cells， roughly and about 180 different genes。



![](img/df8deda2305ec0c1cde4142db300e444_35.png)

![](img/df8deda2305ec0c1cde4142db300e444_36.png)

So this is also what the shape of the data matrix tells you。In each of the entries。

 there the UMI count for each gene and each cell。So how often in the amplified。Version。

 how often was a given。How often was a given gene detected in each cell。

The minimum of the overall matrix is 0。 So that means there are some genes in some cells that are not detected at all。

 That's not surprising。 And the maximum count is 923。

 So that means there was at least one gene in one cell that for which we found 923 replications。Now。

 if we look at how many cells in the data matrix are actually larger than0。

 so in how many cells and gene combinations do we have an entry at all。

 then this value is actually quite small， It's only 15%。

 so it's a very sparse matrix for most genes in most cells， we don't find any expression。

These two la， the last two measurements are what we call the sequencing depth。

 That means how many counts did we find， how many gene counts did we find in a given cell across all genes。

And the cell with the smallest gene count has a sequencing depth of 111100， roughly。

 and the cell with the highest gene count has a， or U M I count has a sequencing depth of 20000。



![](img/df8deda2305ec0c1cde4142db300e444_38.png)

You can also look at the full distribution of these。



![](img/df8deda2305ec0c1cde4142db300e444_40.png)

In this in this histogram， and you can see that it starts at about 1000 or so。

 and then it has a quite a long tail to very high numbers as well。

 But the bulk of the sequencing depth is somewhere around 5000 on average。



![](img/df8deda2305ec0c1cde4142db300e444_42.png)

![](img/df8deda2305ec0c1cde4142db300e444_43.png)

But as you can imagine。Of course， that is a potential confound in our data analysis。

 because if for a given cell， we only have。We can only detect 1000 copies of， of any gene。Then。

 of course， the probability of finding a gene that is expressed at the same level as in a。

 in a cell where we detect 20000 genes will be quite different。

So let's look a little bit into more detail what this confound could be。

So because U M I counts are counts， we can first ask， is the distribution of these U M I count。

 I that actually pel。Because Poisson is the， the standard or the， the first。

 first go to distribution for count variables。So if you， if you look at these。

And I boil them in correspondence to how the corresponding Poson distributions could look like。

 Then probably what you will see is that especially at these somewhat larger ranges that the Poisson distribution tends to get quite symmetric。

 While the distribution that we find in the U M icon data is， in fact， has， in fact。

 a rather long tail。

![](img/df8deda2305ec0c1cde4142db300e444_45.png)

So probably Poson is not quite a distribution for this UM I account data。

Can make this quantitative a bit more precise by plotting the mean variance relationship。Across。

Across genes。So each dot in this plant is a gene。And we look at the mean expression across all cells and the variance in expression。



![](img/df8deda2305ec0c1cde4142db300e444_47.png)

Across all cells and plot these versus one another。



![](img/df8deda2305ec0c1cde4142db300e444_49.png)

For a pure proisson distribution。This， these points should all fall in a single line because for a point zone distribution。

 mean variances are equal。So， in fact， for many genes， we are not too far away。

But there are two sources of variability that add into that plant。



![](img/df8deda2305ec0c1cde4142db300e444_51.png)

One is biological variability， and another one is technical variability。

The biological variability is actually what we're interested in， in the end。

The biological variability comes， for example， from differences in gene expression between cell types。

 So one cell type may express a certain receptor gene because it。

 it needs to put that receptor continuously on its standr。

While another cell type is not not doing that and that is not expressing that gene。So this will。

 in certain genes， lead to true biological variability that is larger than purely what you expect from count statistics。

On the other hand， you also have technical variability that comes from this sequencing depth effect that different cells are simply stoically sequenced more often than others or amplified more often than others。

 And this is what one typically。

![](img/df8deda2305ec0c1cde4142db300e444_53.png)

So typically， what you can see， the， you can see the biological variability in these individual points that are spread out across the line。

 and the technical variability affects mostly the long tail at high means。



![](img/df8deda2305ec0c1cde4142db300e444_55.png)

![](img/df8deda2305ec0c1cde4142db300e444_56.png)

We were looking at this in another way。By taking the ratio of variance in mean。

 So this is also called the phnofactor。

![](img/df8deda2305ec0c1cde4142db300e444_58.png)

And as you know， the final factor is the variance divided by the mean。

 And if variances and mean are the same for a poisson distribution。

 then we expect the phno factor to be one。

![](img/df8deda2305ec0c1cde4142db300e444_60.png)

![](img/df8deda2305ec0c1cde4142db300e444_61.png)

![](img/df8deda2305ec0c1cde4142db300e444_62.png)

So this basically brings out the same structures in the。In the last plot， on the last slide。

So if this was all a horizontalis distribution， then these points should all be very close to a constant line here。

We do see evidence of biological variability appear in genes that are differentially expressed between different gene groups。

 And then we see the signature of the technical variability that we're interested in removing down here in this upward curving slope of the lines。

 So what this means is that for high mean counts of a gene between across cells。



![](img/df8deda2305ec0c1cde4142db300e444_64.png)

The variance increases。So we have at higher expression level。 we have also higher variance。So， Ill。

Data is what we call in statistics， over dispersed。



![](img/df8deda2305ec0c1cde4142db300e444_66.png)

Now， how does this relate to the issue of sequencing them？ So for specific gene。

 assume that the count。With which we find that gene is a product of two factors。The one。

Fact is N here。 This is the sequencing depth。 And P， this is the probability。



![](img/df8deda2305ec0c1cde4142db300e444_68.png)

Or the the fraction。Of the expression in the cell that this genes makes up。

 So let's say that you have a probability or a dis dis fraction。

 So the percentage of of genes or of M transcript that come from that particular gene in a given cell。

Is 1%。 So if we have two cells of that type。And we have for one， we have a。

A sequencing depth of 1000。 Then our expected count is 10。If we have a sequencing depth of 10000。

 then our expected count is 100。收。From the fact that we have this variation in sequencing depth that we already looked at in the beginning。

 we can deuce that we will need to have some over dispersion compared to a purely Poisson variable。

And a common distribution to model over thisperssion compared to poson。

 is so called negative binomial distribution。In a negative binomial distribution， you do assume。



![](img/df8deda2305ec0c1cde4142db300e444_70.png)

That your account follows Po sound distribution。But then the rate parameter also is a random variable that is drawn from a gamma distribution。

 And this leads to additional variability that surpasses the variability in the pure Poisson distribution and is particularly visible。



![](img/df8deda2305ec0c1cde4142db300e444_72.png)

At high， high means。The negative binomial distribution looks a bit like that。

 So here we have a a small animation， depending on the parameters of the negative binomial distribution。

 It's well suited to model these longer tails that we've also seen。In the data。Now， this is， again。

 the final factor plot that I showed you before。And if we normalize the count by sequencing depth。

 So we， in this case， simply divide its each gene by sequencing depth and then multiplay a game with a median sequencing depth。

 then much of this。Curd shape here。Actually， goes away。We can then use such a plant where we show。

 for example， the phfactor of a gene versus the mean expression level to select genes that we are particularly interested in。

 because we know that these genes independent of the exact expression level that they show higher variability than we would。



![](img/df8deda2305ec0c1cde4142db300e444_74.png)

In general， expect。So these， these are genes that are good candidates for true biological variability between different cell classes or cell types。



![](img/df8deda2305ec0c1cde4142db300e444_76.png)

If you're interested more in these topics of how to pre process。

Single cell transcriptomics data or how to compute good distributions for single cell transcriptomics data。

 Then with the goal of selecting genes for further analysis， you can also go to our recent preprint。

 which is available on bioarch in which we deal with these situations in more depth。Okay。

 so now we have done our first pre processing step。

 We have normalized the counts by sequencing depth and， and scaled them on the same scale again。嗯。

To account for one of the sources of technical variability in the data。

Another preosing step that is often done for single cell transcriptomics data is to apply a nonlinear variant stabilizing transformation。

 such as the square root of x or the lock x plus one transformation。So both of these。

Have the effect to written to bring the variance to a more similar range。This is actually useful。

 So if we do principal component analysis， for example。

 on a raw data matrix in this domain and we plot the first two principal components simply on the。

 on the raw data， the data will look somewhat like this。

 So the different colours here are different cell classes and the data is quite overlapping。



![](img/df8deda2305ec0c1cde4142db300e444_78.png)

![](img/df8deda2305ec0c1cde4142db300e444_79.png)

If we take a square root transform first。

![](img/df8deda2305ec0c1cde4142db300e444_81.png)

Before doing the PCA， you can already see that now the。



![](img/df8deda2305ec0c1cde4142db300e444_83.png)

plotloot revealed some distinct。Differences between。



![](img/df8deda2305ec0c1cde4142db300e444_85.png)

Different set clusters。

![](img/df8deda2305ec0c1cde4142db300e444_87.png)

And finally， if we apply the lock X plus one transform， which seems even better suited。

 Then these different clusters get resolved more clearly， even in a simple PC A plot。



![](img/df8deda2305ec0c1cde4142db300e444_89.png)

For this reason， applying such a nonlinear variant stabilizing transform is more or less standard for any transcriptomics analysis pipeline。

Our next goal。In， visualizing or in， in working with single cell transcriptomics data is to create a low dimensional embedding for that we can use。

 in principle PCA， but we can also use other more non nonlinear algorithms。Why do we do that？ Well。

 because of the dimensionality of the data and the lack of inherent structure it's actually very hard to look at transcriptomics data。

 Of course， we could simply make a plot where we visualize the mean expression of each gene in each cell。

 But for the eye， it's hard to see much unless we sort the data in a good way。This is， of course。

 very different when we look at images or time traces because of the in inher inherent internal structure of images and time series。

Therefore， creating these low dimensional embedding is particularly important for exploring and explorative data analysis of single cell transcriptomics data。

Now， why is that even a difficult task？ And for those of you who have listened to our machine learning one lecture or know everything about tea and related algorithms。

 you can skip the next few minutes or listen to them briefly。So。

It's difficult to make good low dimensional embedding of high dimensional data because it's not possible to preserve high dimensional distances。

 So if you look in two dimensions and you sample points from a standard Gaussian。The in。

 in two dimensions， and you look at the pairwise distances。

 then this is a histogram that you would get。If you go to 50 dimensions。Then the histogram。

 So the average distance between。Between pairs of cells is or between pairs of points is already much larger。

 It's on average 10。And if you go to even higher dimensional states， like 500 dimensions。

 then the average distance becomes much， much larger yet。

And embedding this into two dimensions while preserving all these powers distances is just simply not feasible。

So therefore， one idea behind the popular class of embedding algorithms。

 so called neighbourhood embedding algorithms is to preserve neighbours。

 not the Ab absolute distances。So one example is the popular algorithm called T distributed stoastic neighbour embeing or Tni。

And the idea is the following。 So for a given point， I。



![](img/df8deda2305ec0c1cde4142db300e444_91.png)

![](img/df8deda2305ec0c1cde4142db300e444_92.png)

You look at the nearest neighbors in a closed vicinity。



![](img/df8deda2305ec0c1cde4142db300e444_94.png)

And for these。Points， you have a loss function。That is basically the Quebec lab divergence between the power similarities in the high dimensional space So the P I Js and the pair similarities in the low dimensional space。

But you， the， the trick is。In contrast to other algorithms which really try to preserve distances。

 we here only care about the local neighborhood， mostly。

So what is the the loss that has these two components that I just mentioned。

We measure the high dimensional similarities with these exponential kernels。First， they are directed。

But we will sumatise them later。 And this， this kernel width is chosen。

 chosen via a parameter called perplexity and the perplexity。

Ses this kernel with such that there's a sufficient number of points in the local neighbour。

We measure also low dimensional similarities。 We are some kernel function。

And that kernel function in Ts。Is this koshi or T distribution kernel。With that。

 we can then compute the gradient of the loss function as well。And the interesting bit about this。

 this gradient is that it after you， you look at it for a while。

 it basically it consists of two terms， one here where similar points are attracted and another one where。

Disimilar points are repuls from one another。 So it's a attraction repuls and trade off。



![](img/df8deda2305ec0c1cde4142db300e444_96.png)

This parameter perplexity that I mentioned controls the kernel width。 So here。

We have very small perplexity here。 We have higher perplexity。

And the default in many implementations is actually around 30。

 and we compute the perplexity such as this。 So it's。

 it's due to the power of some entropy value that is given by these powerwise similarities。



![](img/df8deda2305ec0c1cde4142db300e444_98.png)

So with controlling the perplexity， you can control the。The resolution of the algorithm or how。

 how much it weighs local neighbourhoods versus global repulsion。

So here we look at the optimization process。Of Tsney。

 And if we just optimize the location of the points with respect to that loss function。

Then you can see that it really takes a while quite a lot of iteration here。

 and it goes through different phases in this optimization。

 So the data that I used here or that that we used here is the M data sets。

 So all these different clusters they correspond to different numbers。

 You can see how the structure in that dataset emerges as the。Optimization runs on。



![](img/df8deda2305ec0c1cde4142db300e444_100.png)

The problem with that optimization problem is that it's hiding on nonlinearia。So。

 and if you simply use many standard implementations， then it can。

 These T implementations can be bad at preserving global geometry。 So if we look， for example。

 in this also very high profile study shared and distinct transcaomic cell types across neo cortical areas。

Then it's a， it's a very beautiful。It's a very beautiful visualization here。😊。



![](img/df8deda2305ec0c1cde4142db300e444_102.png)

But if you look at where the gabaergic neurons are found。 So the gabaeric interne in this case。

 they are distributed in two big islands here。And here。And in between them。

 they are glutaturggic neurons。That are of course， on a global scale。

 much more dissimilar to either these gabaic neurons or these gaboic neurons。

 which are more closely related。 But yet， the algorithm places them kind of in between。



![](img/df8deda2305ec0c1cde4142db300e444_104.png)

And this is a property that is non desirableir。And one way to get the algorithm to respect such global relationships at least better is to initialize the algorithm already with a reasonably good solution。

 for example， by PCA。

![](img/df8deda2305ec0c1cde4142db300e444_106.png)

In if you initialise the algorithm with the PCA coordinates， then it's already in the。

 in the kind of in the right value for the non nonlinear optimization take takes place afterwards。

So you can see here how in this case。The optimization runs。

 So there are these three different islands from the outsideset that contain different cell classes。

Because we initialize via PC A and then the later stages of the algorithm。

 they then shape in more detail how these different island and sub islands look。



![](img/df8deda2305ec0c1cde4142db300e444_108.png)

![](img/df8deda2305ec0c1cde4142db300e444_109.png)

Okay， now we have an embedding。 And if you're interested to more details about T。

 I've linked a video for you。So the next step would be to identify cell types。

 So this basically is an instantation of clustering。

We have done clustering many times already during the selection， for example， for finding the cells。

In the electrophysiological recordings with a mixture of Gaussian algorithms。In principle， of course。

 it's possible to use such a mixture distribution here as well。

 And just adapt the distribution that is used。 So Gaussian mixture is probably not good because the counts are discrete and also the means are relatively low such that the Gaussian approximation is not。

 not a good fit。 But one could， for example， use a mixture of binomial distribution。

 which also has been proposed。We also， as in many， in the other cases that we've discussed。

 we don't know the number of clusters a priori， and many people prefer to use non parametric clustering techniques that don't make such explicit modelling assumptions as the binomial distributions you definitely need。



![](img/df8deda2305ec0c1cde4142db300e444_111.png)

An algorithm that is able to cope with the millions of cells。

 So it needs to be very efficient and also needs to be able to operate on high dimensional data。

 because even after。

![](img/df8deda2305ec0c1cde4142db300e444_113.png)

Possibly reducing。The couple of thousand genes that you're looking at after gene selection， we。

We really have informative principle component components up to 30，40，50 principal components。

So what is most popular in the field is the class of clustering algorithms that are called community detection algorithms using the canest neighbour graphs of the data。

So what is the Ken of sna graph， the Ken nearestna graph。For example。

 for this artificial data set here。Its simply a graph where for each data point。

 you connect it simply to the。10 also， depending on your K。

 to to the 10 neighbours that are most closely related with it。And in this， in this graph。

 you can see already quite a bit of structure。 So up here， the connections are very dense。

 in this island， the connections are very dense and here as well。

 And there are very few connections that go beyond the two islands。

So one could imagine that if you went and did community detection on this canous neighbour graph。

 that you would find the original clusters as these communities。



![](img/df8deda2305ec0c1cde4142db300e444_115.png)

The cost functions that are， that are often optimizeimd by such community detection algorithms in graphs for detecting clusters is something like this。

 This is called the modularity and what the modularity measures。Is the number of edges that u。



![](img/df8deda2305ec0c1cde4142db300e444_117.png)

That a certain node has or a that are that are between a pair of nodes and compares that to the number of edges that you would have in a random。



![](img/df8deda2305ec0c1cde4142db300e444_119.png)

Graph。If they are in the same communities。 So what this tries to， to get at is on average。

 really tight communities that are tightly connected or more tightly together。

Then you would expect from a random graph。There are two popular algorithms for solving such problem。

 And the first one that was proposed is called the Luva algorithm。 I've put the pseudoo code here。

And the idea behind the Luuva algorithm is the following。



![](img/df8deda2305ec0c1cde4142db300e444_121.png)

So you start with a random assignment of communities to nodes。And then in the first step。

 you visit each of the notess in random order。

![](img/df8deda2305ec0c1cde4142db300e444_123.png)

And you check。And you， you move it to， to the potentially different community。

 If this improves the cost function。 and the way you do that。

Is specified on here in this move node function。

![](img/df8deda2305ec0c1cde4142db300e444_125.png)

And here for， for each of the visited， visited nodes。



![](img/df8deda2305ec0c1cde4142db300e444_127.png)

You check if you assign it the same community as some other nodes or one of the other communities。

What is the delta in the cost function？ And if this delta is larger than 0。

 then you make the assignment。 and if not， then you， you don't。And this you iterate。If you're done。

So， if you。Through with everything， then you do an aggregation stamp。



![](img/df8deda2305ec0c1cde4142db300e444_129.png)

By which you combine all the nodes in a single community a kind of a higher level graph。



![](img/df8deda2305ec0c1cde4142db300e444_131.png)

And then you repeat the same process over and over again。And when this converges。

Then you have achieved。

![](img/df8deda2305ec0c1cde4142db300e444_133.png)

Your community detection。So here's also， again， the pseudo code for the aggregation step。

Which basically says if there's， if， if two nodes are in the same community， then。

Make them into a meta an order for the new graph。

![](img/df8deda2305ec0c1cde4142db300e444_135.png)

嗯。This simple algorithm has some issues， however， and one is， is this。

So possibly you can end up with a s situation because you visit the。

 the nodes in a random order that you have one community that is just kept together by this node 0 here and。



![](img/df8deda2305ec0c1cde4142db300e444_137.png)

The way the algorithm works。Can be better。 It can be shown that there are situations in which。

When you visit this note last， moving it。

![](img/df8deda2305ec0c1cde4142db300e444_139.png)

To another community can be beneficial。 And then you end up with a disintegrated non connected community here for the rat node。

This can be fixed by the so calledled lightden algorithm。

And the Leden algorithm just has an additional step， called refined partition。

In which it is made sure that something that this cannot happen。



![](img/df8deda2305ec0c1cde4142db300e444_141.png)

If you apply this kind of light and clustering to our standard example data set。

 our Harris data set that we've used so far。Then you can see that it comes up with a relatively reasonable clustering here。

That also matches quite well What we can see in our low dimensional visualization of that dataset set。

With that， I would like to thank you for your attention during this lecture。

 I think this area of single cell transcriptomics will in the future bring about more and more applications in neuroscience and will get really an important cornerstone of modern neuroscience。

 cellular level neuroscience。Experimental techniques。 So therefore。

 I think it's also important to think about specialized data science techniques that we need on the an analysis side and in this lecture。

 together with the exercise or the coding them that you will do at home。

 I think we've provided you with a good starting point into that direction。 So that sense。

 Thanks a lot。 And see you next week。

![](img/df8deda2305ec0c1cde4142db300e444_143.png)

![](img/df8deda2305ec0c1cde4142db300e444_144.png)
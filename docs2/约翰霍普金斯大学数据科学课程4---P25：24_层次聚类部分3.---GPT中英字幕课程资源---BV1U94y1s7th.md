# 约翰霍普金斯大学数据科学课程4：《探索性数据分析》｜exploratory-data-analysis｜ - P25：24_层次聚类部分3.zh_en - GPT中英字幕课程资源 - BV1U94y1s7th

![](img/65def8b306acfbb2e0f50ac80f5f58fe_0.png)

So the cluster denrogram that's produced by default in R is relatively nice。

 but there is possible to kind of make it a little bit nicer。 So this my P cluster function。

 which is available on the course website， you can download this straight from there。

 And once you source it into R， you can get this function。

 which in turn produces a cluster denrogram。 but then all the points in the individual clusters are a labeled by their cluster labeled and B they are colored in separately so you can see cluster one is labeled with all ones and it's。



![](img/65def8b306acfbb2e0f50ac80f5f58fe_2.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_3.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_4.png)

And it's they're colored black。 The cluster 2 is colored red and cluster 3 is colored green。



![](img/65def8b306acfbb2e0f50ac80f5f58fe_6.png)

So of course， in order to do this， you have to determine you have to specify how many clusters there are before you can actually label them one。

 two， and three， etc ceter。

![](img/65def8b306acfbb2e0f50ac80f5f58fe_8.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_9.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_10.png)

Now you can go to the R G gallery to see some kind of more interesting cluster diagrams and to look at some software that people have used to create really nice clustering diagrams。

 so if you want to look at some for example， this cluster denogram which has labels on the leaf nodes and it's colored each of the groups and has added a little bit of other information。

 you can take a look at this gallery which has a lot of other really nice plots on it too。



![](img/65def8b306acfbb2e0f50ac80f5f58fe_12.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_13.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_14.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_15.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_16.png)

So the other issue when it comes to using hierarchical clustering is how do you merge points together and so the question is you when you merge a point together。

 what represents its new location and so one is called average so average linkage and the idea is that if you take two points and their new kind of coordinate location it's just the average of their x coordinates and their y coordinates so it's kind of like roughly the center of gravity or the middle of that group of points。



![](img/65def8b306acfbb2e0f50ac80f5f58fe_18.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_19.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_20.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_21.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_22.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_23.png)

Now， that seems logical and it can and it can it will lead to a kind of a certain type of clustering result。

 the other type of。

![](img/65def8b306acfbb2e0f50ac80f5f58fe_25.png)

Of approach is called complete linkage And there the idea is that if you want to measure the distance between two clusters of points。

 then you take the farthest two points from each from the two clusters as the distance。

 So for example in this picture， if you look at the upper cluster and the low and the kind of lower left cluster。

 the distance between those two clusters is equal to the distance between the two farthest points and so that gives you the kind of complete linkage approach the average linkage。

 of course， gives you the distance between the two centers of gravity so that's the difference between the two clusteres here。

 So you can see that in the complete linkage example。



![](img/65def8b306acfbb2e0f50ac80f5f58fe_27.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_28.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_29.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_30.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_31.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_32.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_33.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_34.png)

That distance is relatively far， whereas in the average linkage example。

 the distance is somewhat shorter and so it's not like there's one right or run wrong way to do it。

 but the point is to ship that each of the two different merging approaches can give you very different results and so it's useful to try it's often useful to try both approaches to see what kind of clustering results you get in the end and whether one set makes more sense than another。



![](img/65def8b306acfbb2e0f50ac80f5f58fe_36.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_37.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_38.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_39.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_40.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_41.png)

The last function I want to highlight here is the heat map function。

 which is a really nice function for visualizing matrix data。

 So if you have an extremely large table or a large matrix of numbers that are kind of similarly scaled and you want to just take a look at them really quickly in an organized way。

 you can call the heat map function and what the heat map function does is essentially runs a hierarchical cluster analysis on the rows of the table and on the columns of the table。

 So on the。😊。

![](img/65def8b306acfbb2e0f50ac80f5f58fe_43.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_44.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_45.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_46.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_47.png)

So if you can imagine you know， the rows of the table are like observations。

 and then it runs a cluster analysis on the rows of the table and then think of the columns of of the table as as sets of observations。

 even if they're not actually。

![](img/65def8b306acfbb2e0f50ac80f5f58fe_49.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_50.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_51.png)

Observations， the columns， for example， might be variables or something like that。

 but think of them as just different observations。 you can run a cluster analysis on that too。

 And the idea with the heat map function is that it uses the hierarchical clustering function to organize the rows in the columns of the table so that you can visualize them you can visualize kind of groups or blocks of observations within the table using the image function。

 So what it does is it creates the image plot here here。

 and and it reorders the columns in the rows of the table according to the hierarchical clustering algorithm。

 So you can here you can see that for example， along the rows。

 I've got this hierarchical this cluster denogram which shows that there are probably you know three clusters and so those those rows are all grouped together and then there are only two columns in the data frame so it's not particularly interesting to do aer a hierarchical cluster analysis on that。

 But if you had many， many columns know you would reorganize the columns so that they would be kind of the closer ones would be closer together and the farther ones would be farther apart。



![](img/65def8b306acfbb2e0f50ac80f5f58fe_53.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_54.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_55.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_56.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_57.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_58.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_59.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_60.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_61.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_62.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_63.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_64.png)

And so the heat mat function is really useful for a kind of or very quickly visualizing this kind of high dimensional table data。



![](img/65def8b306acfbb2e0f50ac80f5f58fe_66.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_67.png)

So just to summarize for a hierarchical clustering。

 it's a really useful technique for looking at high dimensional data。

 it organizes the data in a kind of logical and intuitive way and in particular functions like the heat map function are really useful for kind of looking for quickly looking at table or matrix data。



![](img/65def8b306acfbb2e0f50ac80f5f58fe_69.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_70.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_71.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_72.png)

And so of course， you need to know you need to define a notion of what it means for two points to be close or far apart and you have to have a merging strategy。

 so we talked about complete linkage and average linkage so given those two things you can run the clustering algorithm will run and will produce a cluster dendurogram which shows you how the merging is done how the points got merged together through the algorithm So one of the couple of issues when it comes to higher clustering and this is often true for many clustering algorithms that the clustering picture may be unstable and so for example。

 if a few points were to change or for example， if you have some outliers then the clustering if you were to remove those points or modify them a little bit。

 then the clustering denurogram or whatever the final product maybe be could change a lot。

 and so you have to be sensitive to that possibility。



![](img/65def8b306acfbb2e0f50ac80f5f58fe_74.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_75.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_76.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_77.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_78.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_79.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_80.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_81.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_82.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_83.png)

So you might so often the useful thing is to try different metrics。

 distance metrics to make sure it's not to see how sensitive it is to the different distance metrics。

 maybe change the meing strategy to see what kind of picture comes out if you change the merging strategy and also clustering algorithms can be sensitive to the scalings of a given variable so you might if one variable。

 for example， is measured with units that are much larger than another variable。

 then next thing sometimes throw off the algorithm。

 so it may be useful to scale certain variable so that they're more comparable to each other。



![](img/65def8b306acfbb2e0f50ac80f5f58fe_85.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_86.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_87.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_88.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_89.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_90.png)

One nice thing about hierarchical clustering， at least the algorithm was discussed here is that it is deterministic so there's no random starting point。

 there's no randomness in it， if you run it once it will run and with the same parameters and the same data it will give you the same picture。



![](img/65def8b306acfbb2e0f50ac80f5f58fe_92.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_93.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_94.png)

Of course， a key question in any clustering approach is is where to cut in the general ideas you know determining how many clusters there are it's not always obvious to figure out how many clusters there are and so but there are a number of algorithms that have been proposed to try to figure that out but I think the best use of hierarchical clustering is probably just for exploratory analysis and just for looking at your data visualizing your data getting a sense of what patterns so if there are any patterns at all。

 and then you can kind of take these ideas and formalize them later in more sophisticated models so I've given some links to kind of more details about these approaches and I encourage you to take a look at them to explore further。



![](img/65def8b306acfbb2e0f50ac80f5f58fe_96.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_97.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_98.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_99.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_100.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_101.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_102.png)

![](img/65def8b306acfbb2e0f50ac80f5f58fe_103.png)
# 约翰霍普金斯大学数据科学课程3：《获取和清理数据课程（约翰霍普金斯大学）》｜data-cleaning｜ - P11：10_从hdf5读取.zh_en - GPT中英字幕课程资源 - BV1wu411P7yX

This lecture is about reading data from HDF5。

![](img/e29bb9cccc66c4b6bb9ad745fe640974_1.png)

HTF5 is used for storing large data sets， it's also used for storing structured data sets。

 and it supports storing a range of data types。

![](img/e29bb9cccc66c4b6bb9ad745fe640974_3.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_4.png)

The name HDF stands for hierarchical data format and that's because the data is stored in groups which contain zero or more data sets along with their metadata Each of these groups has a group header with a group name and a list of attributes corresponding to that group。



![](img/e29bb9cccc66c4b6bb9ad745fe640974_6.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_7.png)

They also have a group symbol table which has a list of the objects in the group。



![](img/e29bb9cccc66c4b6bb9ad745fe640974_9.png)

Data sets are then multidimensional arrays of elements along with metadata。

 they can have a header with name， data type， data space and storage layout。

 and then they also have a data array which is actually sort of the data frame you can think about it of the HDF5 element if you want to know more about the HD5 storage structure you can go to the HDF5 groups website。



![](img/e29bb9cccc66c4b6bb9ad745fe640974_11.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_12.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_13.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_14.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_15.png)

So the RHDF5 package is actually installed through bioconductor and so the way that we're going to install this package is we're going to source this URL right here and that will load the bioC light function the first time you install a package with bioC light it will also have to install the biobase packages from bioconductor and so it might take a little bit and so what we're going to do is use the bioC light command to load the RHDF5 package。



![](img/e29bb9cccc66c4b6bb9ad745fe640974_17.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_18.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_19.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_20.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_21.png)

Then once we've downloaded the package， we could just load it with the same library command that we always use。



![](img/e29bb9cccc66c4b6bb9ad745fe640974_23.png)

In this lecture we're going to actually create HDF5 files and then interact with them。

 you can actually just use HD they are HDF5 package to access data and pull it out of HDF5 data sets without having to create them yourself。

 but it's sort of easier in terms of lecturing just to show you what it looks like when we create them ourselves。



![](img/e29bb9cccc66c4b6bb9ad745fe640974_25.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_26.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_27.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_28.png)

So we're going to use the H5 create file command to create a HDF5 file set。

 which is going to be example。 H5 so this lecture is actually going to be modeled very closely on the RHDF5 tutorial which can be found at this website here that I've linked to at the very bottom of this slide。



![](img/e29bb9cccc66c4b6bb9ad745fe640974_30.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_31.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_32.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_33.png)

So once we've created that HDF5 file， then we can do is we can create groups within the file so we use H5 create group and so what that will do is it'll create within this file。

 the groupF and then we can create another group calledB and create another group that is a subgroup ofF calledFB and so what you can do then is you can actually see the groups and the names of the files that we've created if you look at H5 LS so it's like the LS command but it's listing out only the components of this particular HDF5 file。



![](img/e29bb9cccc66c4b6bb9ad745fe640974_35.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_36.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_37.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_38.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_39.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_40.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_41.png)

So then what we can do is write to the specific groups so for example we can create a matrix A and then we can use the HDH5 right command to write that matrix to a particular group。

 so again this is the file that we're looking at and then this is the group within that file。😊。



![](img/e29bb9cccc66c4b6bb9ad745fe640974_43.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_44.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_45.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_46.png)

And so we can also write we don't have to write just matrices。

 we can actually write multidimensional arrays， for example， here's a multidimensional array。

 we can actually make it add attributes， so for example， we can give it metadata like this。

 the leader attribute， which is sort of about the units。

 and then we can again use the H5 right command to write this array to a particular subgroup。



![](img/e29bb9cccc66c4b6bb9ad745fe640974_48.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_49.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_50.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_51.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_52.png)

And so again， if we list out what's going on inside this file now we have all the groups that we've created and also within those groups。

 we actually have some data sets so you can see that A is now an H5 data set and it consists of integers and then there's another data down here。

 B， which consists of floats and it gives you the dimensions of those data sets that can be multidimensional。



![](img/e29bb9cccc66c4b6bb9ad745fe640974_54.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_55.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_56.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_57.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_58.png)

So we can write a data directly also we can write actually a data to the top level group and the way that we do that is so suppose we create a data frame like this with the DF command so now we have this data frame up here and so what we can do is we can actually use the H5 right command to write that data frame directly to the top level group so instead of passing it the group that we're going to send it to we can actually just send it the variable name so then if we list out what's going on we now see that in the top level group sort of the root group you see DF and it's a data set and it gives you the dimensions of the data and so forth。



![](img/e29bb9cccc66c4b6bb9ad745fe640974_60.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_61.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_62.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_63.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_64.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_65.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_66.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_67.png)

You can then read direct data using the H5 read command so you're going to use H5 read and you're going to tell it what file you're going to be looking in。

 and then for example， you can tell it to read a very specific data set like this readF slash A。

 you can read sub data sets with by just specifying the path like this。

 you can also read data set in the top level group by just specifying the data set name。



![](img/e29bb9cccc66c4b6bb9ad745fe640974_69.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_70.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_71.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_72.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_73.png)

And so what you get back out is the data that you wrote in and so this is how you're going to read data if。

 for example， you have a data set in an H5 file and you want HF5 file and you want to get it out。

 Another advantage of the HF5 file format is that you can easily read and write in chunks So what we're going to do here actually is we're going to write again so we're going to use H5 right and we're going to be writing to the data a that's inside of our file and so what we're going to be doing is we're going to be writing the elements 1213 and 14 and we can tell it what we want to write it to that data and we run and write it to a specific part of that data So what we can do is give it indices So the index file here we'll give you indices for each of the dimensions So the first dimension we're going to say write to the first three rows in the first column of this dataset these values and so if we read the data after we've done that writing you can see that in the first three rows of the first column you get 1213 and 14 just like we wrote。



![](img/e29bb9cccc66c4b6bb9ad745fe640974_75.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_76.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_77.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_78.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_79.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_80.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_81.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_82.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_83.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_84.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_85.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_86.png)

There you can use a similar index command to read just a subcomponent of the data as well so you can pass it in index。

 which is a list that shows the different dimensions to read just for example。

 if you just wanted to read the first three elements， the first three rows or the first column。

 you can pass the same index command to H5 read。

![](img/e29bb9cccc66c4b6bb9ad745fe640974_88.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_89.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_90.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_91.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_92.png)

So some notes and further resources， one thing to keep in mind is that HDF5 can be used to optimize reading and writing from disk and R this tutorial here gives a lot more information about how to use HDF5 I've borrowed a lot of information for this lecture from that tutorial and the HDF5 group has a lot of good information in general on using HD5 if that's what you're interested in。



![](img/e29bb9cccc66c4b6bb9ad745fe640974_94.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_95.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_96.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_97.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_98.png)
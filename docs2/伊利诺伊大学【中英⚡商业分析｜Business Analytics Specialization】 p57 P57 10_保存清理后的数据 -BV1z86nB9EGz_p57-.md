# 伊利诺伊大学【中英⚡商业分析｜Business Analytics Specialization】 p57 P57 10_保存清理后的数据 -BV1z86nB9EGz_p57-

In this video， I want to focus on saving your data and file formats that are alternatives to CSV or Excel formats。

Now， there are two main reasons for considering alternative file formats。

The first reason is that once you've gone through all the effort of cleaning your data。

 you want to preserve the data types， and you want to preserve some of that data structure which may not be preserved if you save it as a CSV file or an Excel file。

The second reason for using an alternative is that CSV files and Excel files can be relatively large。

And when you're dealing with large data sets， then it can be a hassle to save data in a format that takes up so much space and may take a long time to send back and forth。



![](img/0a706534d7b42d528e18149999db60c5_1.png)

So let's go over to a Jupiter La environment and consider these alternative file formats。



![](img/0a706534d7b42d528e18149999db60c5_3.png)

I'm going to import functions from the pandas and Numpy modules。 Now。

 Ny is a programming module for performing numeric calculations。



![](img/0a706534d7b42d528e18149999db60c5_5.png)

And I'm going to use these functions to create a data frame that has three columns of 1 million rows of data。

 and each of these numbers is just randomly selected。



![](img/0a706534d7b42d528e18149999db60c5_7.png)

![](img/0a706534d7b42d528e18149999db60c5_8.png)

Now， I want to go ahead and consider not just the size of the data。

 but also the speed with which you can save and read the data because that's also important。

So what I'm going to do is save that data frame in three different file formats and measure the amount of time it takes and then also look at the size of those files on my computer。



![](img/0a706534d7b42d528e18149999db60c5_10.png)

So you can see in these code cells that I am including a cell magic。

 so when I use those 2% signs and then a key word， then Jupyter Lab can add some additional functionality。

 and in this case， we're going to time how long it takes to perform the computations in each code cell。



![](img/0a706534d7b42d528e18149999db60c5_12.png)

Alright， so let's get to it。 Let's save the data。 first of all， as a CSV file。

 So I'm going to use the2 CSV function and save the file as test underscore data do CSv。

 And I'm going to make sure and set index equals to faults so that I don't include the index values in that data。

 So let me go ahead and run this。

![](img/0a706534d7b42d528e18149999db60c5_14.png)

Okay， that took 1。48 seconds to run。

![](img/0a706534d7b42d528e18149999db60c5_16.png)

Now， let's go ahead and compare that to how long it takes to save that same data frame as a pickle file。

 Now， when you save data as a pickle file， you use a different method to pickle。

 And you also want to make sure that you use a different file extension。 instead of dot C Sv。

 In this case， I'm going to use dot X Z。 And that X Z matches the type of compression that I'm using to compress the data in this file。

 Allright， so I'll go ahead and run this。

![](img/0a706534d7b42d528e18149999db60c5_18.png)

Okay， that took quite a bit longer to run 5。75 seconds。

Let's now compare those two to a parquet file format， so I'm going to use the2 parquet method。

 and when I save this data， I'm going to use the dot parquet as the file extension。

 so I'll go ahead and run this and we'll see how long it takes。



![](img/0a706534d7b42d528e18149999db60c5_20.png)

![](img/0a706534d7b42d528e18149999db60c5_21.png)

Okay， that was by far the fastest，53 milliseconds。 All right， now that weve saved the data。

 let's go ahead and look at the size of those files on my computer。

 So I'm going to switch over to my file Expr， and I've sorted my data based on the size。

 So we can see at the top。 we've got the largest， which is the CSV file format。 And that's 57。8 MB。

 So that's pretty big if you're going to send something via email。😊。



![](img/0a706534d7b42d528e18149999db60c5_23.png)

All right， then we've got the parquet file format， which is 24。8 to megabytes still pretty big。

 but about half the size as the CSV file。And then the smallest file format is the pickle format or the dot X Z file。

 and that's only 21。6 MBte。 so slightly smaller than the partque file format。

 Let's now go ahead and consider how long it takes to read the data back in from their files on my computer as a data frame and then display the first rows of the data。

 So I'm going to start with again， the CSV format。 I'm going to use the read CSV function and use it on the test data dot CSv file。

 I'll go ahead and run that。

![](img/0a706534d7b42d528e18149999db60c5_25.png)

![](img/0a706534d7b42d528e18149999db60c5_26.png)

![](img/0a706534d7b42d528e18149999db60c5_27.png)

Okay， that only took 142 milliseconds。We'll now use the lead pickle function on our test data dot X Z file and measure how long that takes。

Okay， that was quite a bit longer， still not very long， but 645 milliseconds。

 so four or five times longer again than the CSV file。



![](img/0a706534d7b42d528e18149999db60c5_29.png)

And finally， let's try the parquet file format， so we're going to use the read parquet function on the test data dot parquet file。



![](img/0a706534d7b42d528e18149999db60c5_31.png)

Okay， and this again was the fastest， only 33。1 milliseconds。

 so parquet is fastest in terms of reading and saving data。

One other benefit that parquet has is that we can read in a subset of the columns of data。

 So let me demonstrate in this code cell here how we're going to mostly use the same function。

 But I'm going to include the argument columns and indicate that I only want columns 1 and columns 2。

 So if I run that， you can see that indeed， I only read in。



![](img/0a706534d7b42d528e18149999db60c5_33.png)

![](img/0a706534d7b42d528e18149999db60c5_34.png)

Those two columns。 and as we would expect， it took a shorter amount of timeca I'm reading in less data。

 So it only took 12 milliseconds。 All right， so at this point。

 you might have a feel for which file format is the best overall。

 Let me go ahead and summarize the results in a visualization。

 And we've got the relative performance of these three file formats in terms of saving time。

 The CV file is the middle Pickle takes the longest by far。 and parquet is the fastest by far。

Terms of size， pickle is the smallest。 CSV is the longest parquet is just slightly bigger than pickle。

And then in terms of reading time， it's very similar to the saving time where CSV is the middle。

 Pickle is way longer， and parquet is the fastest。 So in my opinion。

 I think the parquet file format wins。Most of the time， however， pickle files are the smallest。

 So if you've got a really big data set and the size with which you're storing the data is a top priority。

 then you might want to use the pickle file format。 Now。

 another thing I should mention is portability。 So if you're worried about using your data in another data analytic application like power B。

 then you want to make sure that you're able to read the data in from whatever file format you have saved it as。

And not all analytic applications can read pickle and parquet files。

 So if you're concerned about portability， then CSV files would probably be the most portable。

 With this knowledge in mind， you should now be able to make a more informed decision about the optimal way to store the data after you've cleaned it。



![](img/0a706534d7b42d528e18149999db60c5_36.png)

![](img/0a706534d7b42d528e18149999db60c5_37.png)
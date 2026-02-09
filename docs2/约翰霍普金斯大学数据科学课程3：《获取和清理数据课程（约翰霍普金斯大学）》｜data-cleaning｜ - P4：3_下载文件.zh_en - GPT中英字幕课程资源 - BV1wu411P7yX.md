# 约翰霍普金斯大学数据科学课程3：《获取和清理数据课程（约翰霍普金斯大学）》｜data-cleaning｜ - P4：3_下载文件.zh_en - GPT中英字幕课程资源 - BV1wu411P7yX

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_0.png)

One way that you might get a data set is that somebody might actually write down the numbers on a piece of paper and mail it to you。

 but more likely in this era of the internet， you are probably going to be downloading a lot of your data from the internet。

 So this lecture is about how do you use R to download files and the reason why that we want to use R to download files as opposed to pointing and clicking is because then the downloading process can be included in a processing script and so you get a more complete picture of how the data were collected and generated。



![](img/c4e14fee2b58ea66518883ae0dbc7bb7_2.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_3.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_4.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_5.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_6.png)

So the first thing to keep in mind is that we need to know what directories we're working in。

 so if you took the data sciences toolbox you learned a little bit about CD and the current working directories and moving around within the directories。



![](img/c4e14fee2b58ea66518883ae0dbc7bb7_8.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_9.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_10.png)

So the two main commands when we're dealing with directories in R are going to be getWD and set WD。

 and so getWD does exactly what you'd expect， it gets the working directory。

 it tells you what directory you're currently in and set WD actually sets a different working directory that you might want to move to。



![](img/c4e14fee2b58ea66518883ae0dbc7bb7_12.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_13.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_14.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_15.png)

So one way that you can do that is you can actually use it move relative so for example。

 if you do sendwv dot dot slash like this， what'll end up happening is you'll move it up one directory so remember when you're talking about directory structure directory is up if it's a superet if it's above the directory that you're currently in。



![](img/c4e14fee2b58ea66518883ae0dbc7bb7_17.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_18.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_19.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_20.png)

You can also use absolute paths， so for example， you can type set WD user JT leak data and what that will do is that'll move you into that directory that you've specified there exactly。



![](img/c4e14fee2b58ea66518883ae0dbc7bb7_22.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_23.png)

So an important distinction in Windows is that you have to use back slashes rather than forward slashes。

 so this is an example of the way that a path might look in a Windows machine as opposed to a Mac or a Linux machine。

 so if you need more help with that go check out the data science toolbox lectures。



![](img/c4e14fee2b58ea66518883ae0dbc7bb7_25.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_26.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_27.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_28.png)

So one thing that we might want to do is before we collect a bit of data is to create a directory for that data to fall into so file dot exists is a function in R so if you are in a directory and you type file dot exists directory name like this。

 it will look within that directory and see if there's a subdirecty called directory name。



![](img/c4e14fee2b58ea66518883ae0dbc7bb7_30.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_31.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_32.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_33.png)

And so if it does exist， it will return true and if it doesn't exist， it will return false。



![](img/c4e14fee2b58ea66518883ae0dbc7bb7_35.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_36.png)

And so Dra。t create like this will actually create a directory if it doesn't exist。

 so here's a little bit of code that checks to see if there's a data directory so it says if the data subdirecty exists。

 then this will return a true， and so what will end up happening is this will be false and nothing will happen。



![](img/c4e14fee2b58ea66518883ae0dbc7bb7_38.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_39.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_40.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_41.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_42.png)

If the data directory doesn't exist， this will return false and this exclamation point will negate it and so that will be true and so then it will create a directory called data so you'll be seeing a command a lot like this throughout the lecture and that's where you create a data directory if it doesn't already exist。



![](img/c4e14fee2b58ea66518883ae0dbc7bb7_44.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_45.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_46.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_47.png)

So the main way that we get data from the internet if we're talking about files is with the download file function and so the download file function downloads a file from the internet。

 you can do this by hand， of course you can go to the website that you're interested in and click and press download but if you do it by using download that file it'll actually improve the reproducibility if you've taken that class you'll understand what I mean by that and if not it will just you can imagine intuitively it's easier to keep track of everything that you've done if you've included the download process as part of your script。



![](img/c4e14fee2b58ea66518883ae0dbc7bb7_49.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_50.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_51.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_52.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_53.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_54.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_55.png)

The important parameters are the URL， so that's the place that you're going to be getting the data from。

 the best file is the destination file where that data is going to go。

 and then the method so we'll talk a little bit about why the method needs to be specified。

 particularly when dealing with ACTPS。

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_57.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_58.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_59.png)

So it's useful for downloading tap unlimitedlimit CSV files， Excel files。

 a whole bunch of other different files from the internet。

 so it's sort of agnostic to the file type that you might be downloading。



![](img/c4e14fee2b58ea66518883ae0dbc7bb7_61.png)

So as an example， we're going to be using the Baltimore fixed camera data so these are speed cameras that are set up around Baltimore which have unfortunately caught your instructor more than once speeding and sent him a ticket and so you might want to be able to download these data and figure out are where they are So if you go over here under the export button on this website you actually get a bunch of different kinds of files and so for example you might go down to CSV which is one of these types of files that you would see over here on the right hand side and if you right click you can copy the link address so now that's the link address just to the CSV file that we might want to download with these camera positions。

And so then what we do is we take that link that we copied and we put it right here when we save it into a variable called fileile URL just like this。



![](img/c4e14fee2b58ea66518883ae0dbc7bb7_63.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_64.png)

And then we passed a download file， that file URL that we collected off the website。

 and we say we'd like to put it in this data directory and we'd like to call it cameras。csv。

 we're using。csv because that's the extension that's used for comma separated files。



![](img/c4e14fee2b58ea66518883ae0dbc7bb7_66.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_67.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_68.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_69.png)

And the method that we're going to use is curl， this is necessary because this website is an HTTPS secure website and so if you're doing this from a Mac you need to specify the method as curl in order for it to work if you're working from Windows I don't think that you need to set the method to be curl the default method will work all right for you。



![](img/c4e14fee2b58ea66518883ae0dbc7bb7_71.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_72.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_73.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_74.png)

So then if you list the files in this data directory。

 so this is sort of like the LS command that we saw on the command line interface。

 you see that we now have one file in that directory and it's the cameras。csv file。



![](img/c4e14fee2b58ea66518883ae0dbc7bb7_76.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_77.png)

An important component of downloading files from the internet is that those files might change so for example。

 if they update the cameras there might be a new set of cameras and the data that we're analyzing might be different。

 so you want to keep track of the date that you've downloaded the data and you can do that with the date function so you just assign to date downloaded the command date and that will give you the date that those data were downloaded so with those data having been downloaded and knowing the date you can go back and see if you can find the right version of the file if you have trouble later on。



![](img/c4e14fee2b58ea66518883ae0dbc7bb7_79.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_80.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_81.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_82.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_83.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_84.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_85.png)

So if the URL starts with HTTP， you should be okay， even if the URL starts with HTTPS on Windows。

 you should be okay on a Mac， you need to set the method equal to curl if you have HTTPS。



![](img/c4e14fee2b58ea66518883ae0dbc7bb7_87.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_88.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_89.png)

One thing to keep in mind is that this is actually going out downloading a file from the internet and so depending on the size of the file and your internet connection。

 this could end up taking a while so sometimes what you may want to do is have the instruction list but when you actually run new versions of the processing software you don't rerun the file download every single time if it's a really big file and remember to record when the file was downloaded so that you can go back and check the version of the file later when you're trying to figure things out。



![](img/c4e14fee2b58ea66518883ae0dbc7bb7_91.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_92.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_93.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_94.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_95.png)

So that's how you download a file from the internet inR。


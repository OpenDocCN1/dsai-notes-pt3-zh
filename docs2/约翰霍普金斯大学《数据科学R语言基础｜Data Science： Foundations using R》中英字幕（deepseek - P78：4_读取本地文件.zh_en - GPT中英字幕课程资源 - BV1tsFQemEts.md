# 约翰霍普金斯大学《数据科学R语言基础｜Data Science： Foundations using R》中英字幕（deepseek - P78：4_读取本地文件.zh_en - GPT中英字幕课程资源 - BV1tsFQemEts

This next lecture is about reading local what are called flat files。

 These are common examples are text files， add the limited text files。

 comma the limited text files and so forth。 If you've actually already taken the R programming class。

 you may be able to skip this lecture because you've already seen how to load data into R。



![](img/bc9ca33ee5139c562c0e8e91211edac0_1.png)

So again， we're gonna to go back to the Baltimore fixed camera data and so I'm again going to download the data I'm going to check to see if the data directory exists and if it doesn't I'm going to create it。

 then I'm going to download the data with download file So now the data have been downloaded from the website and actually is sitting on my computer It's local data to my computer So the first thing that you might want to use to load the data and the most common way that they're loaded is with the read dot table function and so read dot table is the most common function because it's the most robust and it allows you the most flexibility in some ways in R it does require a few more parameters then you would pass to some of the other functions and it can be a little bit slow so there's actually faster ways if you need to scan through files to find specific elements and we might talk about those later。



![](img/bc9ca33ee5139c562c0e8e91211edac0_3.png)

It reads the data into RA， so it reads the data into memory and this can so if you have a really。

 really big data set， it can cause problems unless you read it in chunks。

Read dot tableable is also probably not the best way to read large data sets in general into R。

So the important parameters here are what file you want to read， whether it has a header。

 what's the separation between elements， whether it has row names。

 and how many rows you want to read。The files related functions， read。

t CSP and readt CSP2 will also be briefly discussed。



![](img/bc9ca33ee5139c562c0e8e91211edac0_5.png)

So if we want to read the camera data， we could try just sending it to read do table just like this。

 we say camera data is going to be the variable we're going to assign and we're going to use the read dot table command and we're going to read the file on cameras。

csB So the problem that you'll get back immediately is an error it says line 1 did not have 13 elements and the reason why is because there's commas separating cameras。

csB。But the default for readdot table is to look for a tab delimit file。

 so if you actually try to look at this variable camera data。

 it doesn't exist because R wasn't able to read it in。



![](img/bc9ca33ee5139c562c0e8e91211edac0_7.png)

So what we can do instead is reddot table with setting the SE command， so this is the separation。

 we're going to set it equal to quotes comma， and so what that does is it says look through the file and assume that all the different values will be separated by commas。

We're also going to tell it header equals true because the variable names are included at the top of each column in the file。

So if we do that and assign the results to the camera data variable and then use the head command。

 this will look at the top few rows of that file and so for example。

 on the first row now we see we have data on the first camera。

 it wraps around because of the way that the slide looks here。

 but each row is now been read into one row of the camera data variable。

You can also use readdot CSsv in the case that you have a CSV file。

 it automatically sets set equal to the quote comma and it automatically sets header equals to true and so if you have a CSV file which is one of the most common flat formats that you'll see for data。

 you can use the read dot CSV command。So more important parameters that you can pass， for example。

 to read dot table is you can tell it quotes， so for example。

 you can say whether there are quoted values， if you say quote equals quote quote like that。

 you get no quotes in the file NA dot strings R what the character is that represents a missing value。

 so the most typical character that you'll see in R data sets is NA but that character might also be minus1 or 999。

99 or something else， number N rows tells you how many rows of the file to read， so for example。

 if you only want to read the first 10 lines of the file you can use N rows equal to 10 as one of the arguments to the read dot table function。



![](img/bc9ca33ee5139c562c0e8e91211edac0_9.png)

![](img/bc9ca33ee5139c562c0e8e91211edac0_10.png)

Sip will also tell you how many lines to skip before you read so for example。

 suppose you want to read the third through the 13th line。

 you would set skip equal to2 and M rows equal to 10。



![](img/bc9ca33ee5139c562c0e8e91211edac0_12.png)

So my experience suggests that the biggest common problem that I see in a lot of files is that you see one of these quotation marks placed in the data values somewhere。

 so when that happens R gets confused because it's not looking for those quotes and so if you set quote equal to quote this often resolves those issues and then you won't have to deal with them so it's just a helpful tip。

 whenever you see sort of data sets that aren't getting read in or getting read in is a very long vectors。

Setting this quote variable in that way can be one way to address it。



![](img/bc9ca33ee5139c562c0e8e91211edac0_14.png)
# 密歇根大学《给所有人的Python课》课程4：《使用数据库进行Python编程》｜python-databases｜ - P23：23_03_05_实战示例：tracks.py程序.zh_en - GPT中英字幕课程资源 - BV1PP411W7H1

Hello everybody and welcome to yet another walkthrough of Python for everybody。

 this is a walkthrough of the tracks CSV application。



![](img/328a55af607248a550615fd51e572b82_1.png)

And you go to wwwpd 4。com/code 3， and you will find a file named tracks。 zipip。



![](img/328a55af607248a550615fd51e572b82_3.png)

![](img/328a55af607248a550615fd51e572b82_4.png)

Tracks zip download this and extract it， and you will have all the code that I am working with。

 So here I am in that file。 let's take a look at the。



![](img/328a55af607248a550615fd51e572b82_6.png)

Let's take a look at the files that are in here， so there's an old folder for the old XML version of this application if you want to try that one it's still sitting there the autograder doesn't actually care whether use the CSV1 or the or the XML1 the XML1 is interesting if you have to learn XML。

 but basically what we're going to do is we're going to take a CSV file。



![](img/328a55af607248a550615fd51e572b82_8.png)

![](img/328a55af607248a550615fd51e572b82_9.png)

![](img/328a55af607248a550615fd51e572b82_10.png)

Tracks。Dot cv compass separated values。 And this is just a whole bunch of data from my own。



![](img/328a55af607248a550615fd51e572b82_12.png)

![](img/328a55af607248a550615fd51e572b82_13.png)

My own export of my iTunes data then converted to CSV from XMl。 So it's got， you know。

 the title of it， the the artist， etc cetera。 And so we're going to read this one line at a time and then insert it in a database and the key thing to this database is we're going to make it in normal form。

 meaning that we're only going to put the artist in once。 we're going to have a primary key。



![](img/328a55af607248a550615fd51e572b82_15.png)

![](img/328a55af607248a550615fd51e572b82_16.png)

![](img/328a55af607248a550615fd51e572b82_17.png)

![](img/328a55af607248a550615fd51e572b82_18.png)

They're going to have a unique name， so the word queen is going to only appear once in that table。



![](img/328a55af607248a550615fd51e572b82_20.png)

And so we're going to link everything together through foreign keys like artist ID and album I D。

 And if we skip this thing started， we sort of starter up， we go to trackdbeat SqLite。

 and I want to be able to run this over and over again So the first thing I do is drop all three tables and then I recreate them both in case I want to change my schema or if I just make a mistake and I want to start over because as if you write this or you're modifying this code。

 you make little mistakes and just want to start over every time you run the code you want to start fresh。



![](img/328a55af607248a550615fd51e572b82_22.png)

![](img/328a55af607248a550615fd51e572b82_23.png)

![](img/328a55af607248a550615fd51e572b82_24.png)

![](img/328a55af607248a550615fd51e572b82_25.png)

![](img/328a55af607248a550615fd51e572b82_26.png)

![](img/328a55af607248a550615fd51e572b82_27.png)

So let's take a look at the code that's going to run， we're going open that tracks。

 CSsv file this one right here and then it's not a super formatted CSv this is kind of a really simple CSV that's just comm separated versus a true CSV is actually a format and there's code inside Python that parses the rich CSV format。

 but I'm just going to read through and split it by comms。



![](img/328a55af607248a550615fd51e572b82_29.png)

![](img/328a55af607248a550615fd51e572b82_30.png)

![](img/328a55af607248a550615fd51e572b82_31.png)

![](img/328a55af607248a550615fd51e572b82_32.png)

And in case there's like some weird piece of code in there and there's not what I want。

 If there's less than six pieces， I'm just going skip it。 So I put a continuum in here。

 And then I parse out the pieces， the the name of the track， the artist， the album。

 The count arrayating in the length。 And so we're most interested in an artist and album doing a money to one relationship into that。

 So I just immediately print those things out because I want， you know， when I。

 when I build something like this， I would build these lines first。 And， yes。

 it looks like my parsing is working correctly。

![](img/328a55af607248a550615fd51e572b82_34.png)

![](img/328a55af607248a550615fd51e572b82_35.png)

![](img/328a55af607248a550615fd51e572b82_36.png)

![](img/328a55af607248a550615fd51e572b82_37.png)

![](img/328a55af607248a550615fd51e572b82_38.png)

![](img/328a55af607248a550615fd51e572b82_39.png)

Then we're going to do the many to one。 And so we work from kind of the leaves of the tree inward。

 So we're going to do an insert or ignore into the artist by name。

And so whatever that is queen or whatever。 Now that's the first time it's going to actually insert it and assign a primary key。



![](img/328a55af607248a550615fd51e572b82_41.png)

The second time this I is going to work because art the name on the artist's table is defined as。



![](img/328a55af607248a550615fd51e572b82_43.png)

Unique， and so you can't insert that more than once。



![](img/328a55af607248a550615fd51e572b82_45.png)

So this will work the first time we see a particular artist。

 but it it will ignore it the rest of that point， but then we got to figure out what the generated ID is the primary key。

 So we're going to select that。 So you notice there's an I in there。

 That means autogenerate this if I don't give it to you。

 and so we're going to grab the I from artist where name equals and then look that same artist up by the by the name of them and then grab the artist ID。

 this is going to be fetch1， get one record and then the0 with I。

 which is there's only one column and there's going to only be one row and artist ID is what we get same thing is true except now we're going to use artist ID as a foreign key into the album and so we're going to insert album album by title and artist ID is a foreign key in there and then we're going to do the same trick。

 we're going to look up the ID the primary key of that particular album。

 we're recording the artist ID。

![](img/328a55af607248a550615fd51e572b82_47.png)

![](img/328a55af607248a550615fd51e572b82_48.png)

![](img/328a55af607248a550615fd51e572b82_49.png)

![](img/328a55af607248a550615fd51e572b82_50.png)

![](img/328a55af607248a550615fd51e572b82_51.png)

![](img/328a55af607248a550615fd51e572b82_52.png)

![](img/328a55af607248a550615fd51e572b82_53.png)

![](img/328a55af607248a550615fd51e572b82_54.png)

![](img/328a55af607248a550615fd51e572b82_55.png)

![](img/328a55af607248a550615fd51e572b82_56.png)

![](img/328a55af607248a550615fd51e572b82_57.png)

![](img/328a55af607248a550615fd51e572b82_58.png)

If。If we're inserting it， we want to record it， but now we're going to get the primary key of the album and we'll have that。



![](img/328a55af607248a550615fd51e572b82_60.png)

![](img/328a55af607248a550615fd51e572b82_61.png)

And then let's get all that figured out。 we're kind of working from outward in。

 so we're doing artist then we're doing album， and then we're do track。 That's kind of outward in。

 and then we're going to insert the foreign key album might D title length rating account into the table and then we commit it so that we write it all to the database。

 So let's go ahead and run this code。

![](img/328a55af607248a550615fd51e572b82_63.png)

![](img/328a55af607248a550615fd51e572b82_64.png)

![](img/328a55af607248a550615fd51e572b82_65.png)

Python。

![](img/328a55af607248a550615fd51e572b82_67.png)

Track。pyy。It opens the file， loops through everything。 and then away you go。 So if you look at。



![](img/328a55af607248a550615fd51e572b82_69.png)

![](img/328a55af607248a550615fd51e572b82_70.png)

Like the last file in its microchiip， Jason Farnham。And then that is the last record that came out。

 So now at this point， let's take a look at the database。



![](img/328a55af607248a550615fd51e572b82_72.png)

![](img/328a55af607248a550615fd51e572b82_73.png)

![](img/328a55af607248a550615fd51e572b82_74.png)

And trackdv。sqolite， that's the file， and I can say in this。

 I've got the SQLite browser installed in the command line。



![](img/328a55af607248a550615fd51e572b82_76.png)

You may have it in your oze。嗯。I can't even type it。And then track Db。Okay， so I can say。

 what tables do I have in here？

![](img/328a55af607248a550615fd51e572b82_78.png)

And I see they got the album artist in track， and I can say select star from artist。



![](img/328a55af607248a550615fd51e572b82_80.png)

![](img/328a55af607248a550615fd51e572b82_81.png)

Limit 10。

![](img/328a55af607248a550615fd51e572b82_83.png)

。So you see that queens are the first one， lead Zeeppeelin， these are the primary keys。

 there is only one record。

![](img/328a55af607248a550615fd51e572b82_85.png)

Named Queen， so I could even say this。 Select Fro Arphraaris where。



![](img/328a55af607248a550615fd51e572b82_87.png)

![](img/328a55af607248a550615fd51e572b82_88.png)

Name equals queen。So you'll see that there is only one record。 and if we say select。



![](img/328a55af607248a550615fd51e572b82_90.png)

![](img/328a55af607248a550615fd51e572b82_91.png)

Star from track。Limit 10。

![](img/328a55af607248a550615fd51e572b82_93.png)

We see they're all connected together and we got the primary key for the track and then the album ID is this third parameter here and you see you know that's album7 and there's a lot of reuse there in the in the data so so let's get out of this。



![](img/328a55af607248a550615fd51e572b82_95.png)

![](img/328a55af607248a550615fd51e572b82_96.png)

So I'm going to open the SQLI browser。

![](img/328a55af607248a550615fd51e572b82_98.png)

And we're going to open trackDB。sqlite。

![](img/328a55af607248a550615fd51e572b82_100.png)

So we see that those are the tables that got created， we can take a look at the data。

 we can go look at， for example， the artist data， we see again one same kind of data there。

 see all of them now， and then we can kind of work our way into album。

 the album has a foreign key of artist ID and each album has its own ID。And then if we go to track。

 we see them all。🎼Together where we have Al I D and this other data。

 which is not really foreign keys， but we see the Al I D foreign key。

 So that gives you hopefully a quick run through of the CSV version of the tracks and the one to many mapping into a database。


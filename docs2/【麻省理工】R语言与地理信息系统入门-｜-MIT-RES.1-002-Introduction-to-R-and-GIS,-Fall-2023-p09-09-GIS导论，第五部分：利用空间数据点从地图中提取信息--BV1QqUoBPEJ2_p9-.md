# 【麻省理工】R语言与地理信息系统入门-｜-MIT-RES.1-002-Introduction-to-R-and-GIS,-Fall-2023-p09-09-GIS导论，第五部分：利用空间数据点从地图中提取信息--BV1QqUoBPEJ2_p9-

![](img/aab4c4e0d6458370ed34dea38b1c5250_0.png)

In this part of the code， I'm going to guide you through the gap filling process based on maps。

So this is a process that I use quite a lot in my research， which is when I'm facing a new database。

 sometimes comes with some empty slots， some NAAs in the data。

 and I want to fill them based on field data。Obviously。

Data coming from maps is not as accurate as data coming from field experiments。

 but this is a good proxy we have to maximize the data we have and use them all in our models。

So what I'm going to be doing here is to use the latitude and longitude of the coordinates that comes into the databases。

 transform them into special explicit data points and use these data points to extract。

The data crop coming from a map。So let's just go ahead。

 I'm going to download real data that I created， that it's in my GitHub account。

 you can download it freely here。It's a database that calculates nitrogen uptake。

 global scale based on field data。But I encountered that some of the drivers。

 temperature and precipitation， soil information has not always been collected or maybe wasn't reported in the original papers。

 so that's why there are some data gaps。So well， you can see that is a big。Database。

 it includes a lot of columns， some of them are complete， some of them have Ns。U。

So I'm just going to see how are they called？These are all the names of the columns。

And we are going to be particularly interested in the latitude and longitude。

 which is the third and fourth column right here。嗯嗯。😊。

I'm going to make sure that we don't have an A there， so I'm just going to subset。

The data that doesn't include NAs。 So it say is NA so that doesn't include NA in the latitude and it doesn't include Ns in longitude。

 This is one of the several ways we have to make sure that we。Exclude Ns in this particular。Columns。

Okay， now that we have this sort out， there are two ways of transforming this data points。

 so this latitude and longitude in data explicit points。

 one is using spatial points here and the other one is using spatial points data frame。

In both of them， I need to specify where latitude and longitude are located。

What's the database that I'm using and in the first case I need to specify also the resolution。

 I want the data to be I personally like this more。

 but with this one right here it's going to also work for our purposes right now。

We see that the outcome we get。<|OTHER|>He's a slightly different one。Special points， data frame。

 and the other one is special points。But if we plot them， they look。Very similar。T。And。

We can plot them。With the shape of the earth， you don't have a good understanding of。

What is this plotting？Here， I add it。This map that we already used in another。

In other parts of the videos， so here we can have a good understanding of where this data is coming from。

And it also certifies that we have built our map appropriately。

 Sometimes if you miss much latitude and longitude， you're going to have。I could twist it back so。

Try it for fun。Let's see how it looks like。You see， now it's totally。Change 90 degrees。

But just the heads up to put latitude and longitude in the appropriate。Location。Okay。

So going back to the process， I'm going to use as the base， this map that we've been using。

Recurrently， which is this temperature map， and I want to extract the information using these points。

 so I only need to use the function extract the map where I want to take the information from and the points I want to use to extract the data。

So I use this and I see that the result。Is this right here Oh， sorry。Here。

 and we see that we have a new value here， a new vector that is 159。Data points long。

 which is exactly the same number of columns of rows， sorry we have in our data frame。And。

If instead of having one map here， we would have had a stack or a break。

 we would have had a column per map so。In this case， we only have one because we have one map。

 but the more maps we have， the more columns it would add in our result。

Now I'm going to guide you through an exercise that hopefully is going to be a good summary of all the functions and all the concepts we've been working with in this GIS session。

 I'm going to guide you through it so initially there's nothing done here so I'm going to type while doing it live。

And first of all， I would ask you to download this 10 meter resolution average temperature maps from WorldC。

This is the link， but in case you don't have it handy， this is how the web page looks like。

 I would ask you to go to this average temperature and download this one。😊。

Feel free to download other resolutions as well， but I just went to the course one to make the explanation more fluid and the calculations easier to calculate。

So it's download these， a story's somewhere in your computer that you know they're out of。

And also I'm going to ask you to load all these maps in your R session and calculate the average of all the maps so to obtain the yearly average temperature。

Okay， to do that， I'm going to use code that we've already used， I'm just going to jump。Around。

I think I have this coat here， yes。😔，I'm going to use this。

So I'm going to charge everything at once instead of going one by one， I'm going to do it faster。

This。And this， I don't really。One this code here。😔，I'm going to create a stack of these。

Now we want to calculate the mean of all these maps。So to do that， it's going to be called。

I'm going to use these object here。And calculate the mean。This is what we got。

To see that information。Looks good。 The value， minimum， the maximum。They look feasible。

 so it seems that everything worked out pretty well。

I'm just going to apply it to see how it looks like。So yeah， it seems reasonable。

 so I think we've successfully completed the first step。Second step。

I want you to download the Unitedtrogen opttake data from this page， which is my GitHub page。

 this is the database we've used in the previous exercise so you might have it already。

And I'm going to ask you to create a new data frame by subting the columns number。3，4， and 18。

 which are the latitude longitude and mean annual temperature。

 which is what we just calculated in our maps。U。So to do that。Just going to load the data。

That she would have here。This is the thetum。I'm gonna to upset。I said the column。Number three。

 number four and number 18。Now we have this object that has exactly the same length。

 so the same rows， but the only these three variables that I asked you for， latitude， longitude。

 and mean animal temperature。I chose this variable because we have some Ns as I mentioned。

You see some empty values that we would like to fill。In further steps。嗯。

Kay let's move on to the step three。I want to create spatial points by using that coordinates in the subd data frame。

And I also want to extract the main an temperature of the data points you just created from the map。

And include them in a new vector to the data frame resulting in a four column。Data frame。嗯。

We'm going to go through the coat that we just。Used， oops。Sorry， sorry， sorry。嗯。😊，Find them here。

This one。I'm going to use this one that's shorter。Okay， we created that。

 And now we want to extract this information。 So it's going to be called。

MATT stands for mean An temperature。And I want to extract from。This variable that we created。

 that's the mean temperature。And the PMT。Okay， we created this vector here and now I want to add this vector to our initial data frame。

So our data frame was created。Was called。F。It's gonna be called。Coming from World clean。嗯。

This is one way to do it。 There are other ways。 So if you find。

An easier way that works better for you to do it， feel free。

So now we had this initial database that had only three columns， now it has four columns。

And we just added this new column here。With a new variable， we could even see how this too match。

 so this comes from。Ground measurement， so it's based on field data and this is the map we could even see how these too match。

 we could， for example， plot these two informations or create a linear model that' just going to go with a model。

It's going to be cold。Model one is' going to be a linear model。Where。I have these。Based on。

We claim this data。Is gonna be。These one。Let's see， well， it's almost the same data so。

They agree in a 94%。H。Yes， almost one， the perfect regression， so this is a good proxy。

 we could also plot them。嗯。In a linear inner regression plot。Just。It's like this。And we see how。

The data mostly agrees。Okay， and now finally， I want to combine these two columns so create a new column in your data frame where you got feel the mean annual temperature variable with the map data you just extract it so what I want to do here。

Is to use， so。Mainly use these field experimental data。But use the map to get field。

These empty spaces that I have here。To do so， I'm going to use code that I already have， which uses。

A for loop。So it's faster。Okay， what I'm doing is to this state I'm going。Change。The code， using。

These two。So what initially was General Db now is going to be cold and。In the section。

 which is what I selected。And replace them all。Yes， for occurrences。Okay， and now the data。

So what I'm going to be doing is I'm asking R to generate this for loop that goes from 1 to 159。

 which is the number of rows that I have and I'm saying if，This is NA， so it's an empty space。A。

 but boom。If this variable is an empty space。Go to。The same variable。And feel this space。Wuiz。

What you will find here。And if that's not then an A。Just leave it like is。You could。

Even erase this part。We could not need this else part because it's basically leaving the thing as they are。

 so you could decide to erase these and things would work either way。So I'm going to make this run。

 maybe it gives us some error， it assume that it went smooth。啊。Okay。

Now we see that this variable here doesn't have。NAs because we filled this information with information coming here。

In this case I have destroyed the initial variable。

 meaning that now we no longer have the variable with these spaces。

 I could have created a new variable， which is what I'm going to do now just for you to see and to compare things better。

 so I'm going to rerun the whole code。In a very easy way。

Like this is are the advantages of R that you。Can rerun things。Pretty easy。 And now， instead of。

Rearranging things on top of the variable that are already existed。

 I'm going to create a new one that's going to be called new。Newu。



![](img/aab4c4e0d6458370ed34dea38b1c5250_2.png)

'm goinging to redo the process。Now， we have this new。Code this new column here and。

So when we have an NA， it's always the same as MAT， but in the ones that we have NA。

 we've used this one instead， and this is a very efficient way that we have to gap field data coming from。

From map data。

![](img/aab4c4e0d6458370ed34dea38b1c5250_4.png)
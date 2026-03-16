# 【精译】蒂宾根大学《神经数据科学》-p13-13-神经科学中的数据管理--BV1DEYozGEMW_p13-

🎼。🎼。

![](img/b1f215368247cdcd19ab292ad34266b2_1.png)

Welcome to the final lecture of neuroda science。Today。

 I would like to talk to you about data management and neuroscience。

We've talked a lot about different machine learning algorithms and how you apply them to data。

But an important component of using。Data in a lab setting and also beyond the standard of data management。

How do you keep all your data nice and tidy， How do you make it accessible。

 How do you keep track of your results so that they are reproducible and so on and so forth。

So as we have seen during the course in a modern lab environment， we record lots of information。So。

 for example， during a given experiment。

![](img/b1f215368247cdcd19ab292ad34266b2_3.png)

In， in the lab， we could monitor the running of the mouse on a treadmill。

 We have a visual stimulus that has shown。 We perform calcium imaging。

 We monitor the eye movement of the animal， the whiskers。

 and we could even simultaneously record the membrane and potential of individual neurons or the local field potential with electrodes。

 And in addition， We have lots of May met data， like which animal it was。

 which transgenic line it belongs to。

![](img/b1f215368247cdcd19ab292ad34266b2_5.png)

What stimulus was used and so on and so forth。So this can become arbitrarily complex。

 especially if we want to try out different settings of our pre processingces parameters。

Or of our inference methods， later on。So one crucial question that as soon as you work with data that goes beyond just a few simple examples。

Is how do you keep all of this nice and tidy。 What I would like you to show you to what I would like to show you today is a tool to do just that。

So， conventionally。After the experiments， you put your raw files。On the lap storage， sova。

Then you write down lots of the metada。In your lab notebook。

 if everything goes well or you just remember them， or sometimes you also forget to write on things。

 of course， not on purpose， but things can happen。Then you do some post processing of the data with the parameter settings that are usually used in your lab。

It's either done manually， or by applying a function。But often， it's a function。

 that's A PhD student， let's say， wrote that already has left the lab All the modificationifications thereof that has occurred since。

When you do analysis， you run some scripts on post process data， you save intermediate results。

 either locally or on your storage server， and then you rerun analysis each time you need to generate a figure。

 or if it's too much for that， you just save it and rerun if you found a bug。

 If you found all the saved files that were generated with the scripts that had the bug。

And the data is compiled for the paper in the end， manually for all the data that you can find at that time。

Of course， that is a bit of a mean sketch of usual lab work。

 And I know that almost all colleagues in experimental and also in computational lab are super careful about keeping track of data。

 It's just a complex process to work with real data。 And in the end， lots of information is lost。

 even if you try hard。 if you do everything manually。

So problems that occur with such a conventional workflow could be。

Which version of the code did I use again to compute the receptor fields， I'm not sure。

If it's a lot of cells and you need to compute all of them again with a current。

 with a current version of the code， this can take a long time。

I'm not sure whether I deleted the reive field file where I saved the data。For neurons 1 to 42。

 when I found that back。 So again， you need to recompute everything from scratch。

 which can take a prohibitively long time。 if you're tight on time， for example。

 when you try to publish before a conference deadline or you need to have the data ready for a presentation。

So often you hear them quotes like， this will take a week。

 I have to recompute all the receptive fields。 I didn't save them。Or I saved the wrong ones。

 Or I'm not sure which ones I saved。Then sometimes you might wonder。

 are these labels that I have in addition to the cells that say the ones that tell you which of the cells was tacked by the transgenic line and which one were not。

 Are they really in the right order， And does the order match that of the receptive fields。

If you have not keep， if you didn't keep track of that， that can be very difficult。

Or things like this。 you try to find out where exactly in the brain or where on the cortex or where on the retina or。

 you know， some coordinates that youre interested in， and you say， let me check my lab book。

 And you find， I don't have the information ready。 or you try to find out which temperature was it。

 that the animal had when we did that particular recording because temperature can， of course。

 affect also neural activity。 but you know， the standard setting。

 but you don't didn't write down the measurement you took by the thermometer that day。

 you just checked that it was roughly in the fine range。

And then you want to do some postdoc analysis because here。

 some review tells you and you don't have the information。

Or you need to go through your lap book and manually write it down every time。



![](img/b1f215368247cdcd19ab292ad34266b2_7.png)

So what can one do about that？One way to deal with that is actually a data management system。

 and one of these systems that is very， very useful for a neuroscience lab。

 but also beyond can be also used， for example， to train models in deep learning or for simulating models when you do biophysical modelling or pretty much for any other kind of experimental data。

Is a so called data joint。In data joined， a data scientist such as itself。

Interacts or writes a data pipeline that specifies how data is processed。There's a client。

That manages in either par Matlab or Python the interaction with a back end architecture。

 which can be either for large files， a bike object storage or a My SKL server for smaller data。



![](img/b1f215368247cdcd19ab292ad34266b2_9.png)

What is important about that data management system is that it preserves dependencies between primary and metadata once they are in the system。

It interfaces naturally in manta and Python and has a very simple and efficient query language。

You can easily， in a straightforward way， perform distributed computations。



![](img/b1f215368247cdcd19ab292ad34266b2_11.png)

So how does that work。Data joint builds on the so called relational data model。 If you。

 an expert in databases， then all of that is no news for you。

So the relational data model needs a few terms to work with。 so called Tple is a set of attributes。

Name value pass。So for example， here， mouse， I D measure date and rate。

 And then a tuple is this entry 1001 and so on and so forth。

A relation is a set of tus that have the same attribute names。

And each tu in a relation needs to be unique。 You can think of a relation as a table。

So this table here is a relation。 It has the fields， mouse， I D measure date and weight。

 and all of the entries are unique and distinct from each other。

A schema is a set of logically related relations。And the primary key is a subset of attributes that are used to uniquely identify a triple。



![](img/b1f215368247cdcd19ab292ad34266b2_13.png)

So， for example， here in this in this relation， mouse idea and measure date could be the primary keys because they can be used to uniquely identify all the individual entries。

And weight is then。Another variable that is just measured for each of these entries that is identified with the two other F fields。



![](img/b1f215368247cdcd19ab292ad34266b2_15.png)

A foreign key。These are subsets of attributes inherited from another relation。

So let's make this concrete。 So let's say we have a relation or a table that is called mouse dot info with a primary key mouse I D。



![](img/b1f215368247cdcd19ab292ad34266b2_17.png)

![](img/b1f215368247cdcd19ab292ad34266b2_18.png)

And then in addition， it has information about the sex of the mouse。



![](img/b1f215368247cdcd19ab292ad34266b2_20.png)

Then we have a second relation here that is mouse outt weight。

And mouse dot weight inherits the key mouse I D。

![](img/b1f215368247cdcd19ab292ad34266b2_22.png)

From mouse info。 So for every mouse in mouset info。



![](img/b1f215368247cdcd19ab292ad34266b2_24.png)

Most that weight has an entry。That contains additional information about the weight。

 which was measured at a certain date。

![](img/b1f215368247cdcd19ab292ad34266b2_26.png)

Why are these foreign key important， For keys ensure that theres no triple in the derived relation。

 So in this white table here， that does not have a corresponding entry in the base relation。

So if you don't have a mouse in your database。

![](img/b1f215368247cdcd19ab292ad34266b2_28.png)

You also cannot enter it。Into your measure。Into your， into your weight table。

 So if you want to enter a mouse here， you have to first enter its ID D and it sucks here。



![](img/b1f215368247cdcd19ab292ad34266b2_30.png)

![](img/b1f215368247cdcd19ab292ad34266b2_31.png)

This forces you to have the metadata for the sex of the mouse。

Always entered into your primary table here。 This cannot be forgotten。



![](img/b1f215368247cdcd19ab292ad34266b2_33.png)

![](img/b1f215368247cdcd19ab292ad34266b2_34.png)

It also makes sure。That， there's referential integrity。



![](img/b1f215368247cdcd19ab292ad34266b2_36.png)

So if you delete a mouse。From your， from your base table here。Because I don't know。

 something came up why the mouse has to be deleted。



![](img/b1f215368247cdcd19ab292ad34266b2_38.png)

Then it will make sure the system will make sure that the corresponding entry is also deleted here。



![](img/b1f215368247cdcd19ab292ad34266b2_40.png)

So this， for example， is not possible。If you did eat this。

Then the corresponding entry here is also deleted。So what is this good for。

 Let's say we have a schema。 So this would be a schema。 It's a set of logically related relations。

Such as this， where you have mouseed info， then you have the height and the weight they are measured at certain dates。

 And then you compute the body mass index of the mouse。Now。

 you find out at some point that you confused inches and centimetersime and BM I is defined as centimet。

 as in units of centimet squared。Now， you delete the table mouse at height because this is where the error occurred。

Then what your system will do。 So this is the referential integrity。

 It will automatically delete all the entries in mouse dot BMI。

 because these will have to be recomputed。Because something in your base relation changed。

If you map that bank to the example of the receptive fields。

If something in the pre processings of your data changed because you've found a bug during the spike sorting process。

Then you will also delete all the receptorive field。

 and the system will automatically make sure this is done。

So it cant can't happen to you that you have some version of your receptive fields floating around where you don't know whether it was computed with the back free code。

This is what we refer to as referential integrity。Such a system also allows for easy data filtering by defining a few。

Key operators that， that map to。Database operations。 So we can， for example。

 easily find two matching two pills or two pills。Mach if they are identically named attributes contain equal values。

 So kind of a clear definition。 So mouse I D， this mouse I D table here with a sex and the mouse I D table with a weight。

They match if the I is the same。We can also do a restriction。

Where we select twos that match certain contentence。 So this is kind of filtering the table。



![](img/b1f215368247cdcd19ab292ad34266b2_42.png)

So if we just simply say， I want all the mice that where the weight was measured on the 10th October 2010。



![](img/b1f215368247cdcd19ab292ad34266b2_44.png)

![](img/b1f215368247cdcd19ab292ad34266b2_45.png)

Then， we can specify that。As such。

![](img/b1f215368247cdcd19ab292ad34266b2_47.png)

We can also restrict by another relation。 So why is that good， Well， this can give us。All the。

All the entries。 So， for example， if we want the sex of all the entries for which we have also measured the weight。

Then， we can simply restrict。This mouse I D table。By the relation here by the mouse weight table and obtain this these three entries for which measurements are or for which entries are present in both tables。



![](img/b1f215368247cdcd19ab292ad34266b2_49.png)

If use the minus sign instead， then we get simply the remaining F entries。

Then we can also join two relations。 And this contains all fields for all matching tus。 So。

 for example， So this illustrated down here， if we compute the join between two these two。

 we get a new relation that has all matching tus。 So just the first three entries。

 and it has the information。

![](img/b1f215368247cdcd19ab292ad34266b2_51.png)

嗯。Of the sex。 and the weight。From both the original tables。 So we。

 we can manipulate these kind of data tables very easily。



![](img/b1f215368247cdcd19ab292ad34266b2_53.png)

![](img/b1f215368247cdcd19ab292ad34266b2_54.png)

This also makes it very easy to implement automatic computations so we can specify some relations as manual relations where you have to enter the data either manually or whether。

 where the data is automatically entered by your， by your experimental system。 Let's say these top 3。

And then you can say the bottom one here， the BMI。 This is just a simple function。

Of the information in these other things。 So I don't have to do anything manually just specify in the BMI table what from the other fields or from the other relations needs to be combined。

To compute the information that I want。 And then you call a simple function called populate。



![](img/b1f215368247cdcd19ab292ad34266b2_56.png)

This goes to this table。

![](img/b1f215368247cdcd19ab292ad34266b2_58.png)

Looks， what is the computation that needs to be done to fill in its entries。

 and it will do so for all unique entries in this。A combination of these two tables。



![](img/b1f215368247cdcd19ab292ad34266b2_60.png)

Whereas the data then actually stored。 So each relation is mapped to a table in a Myosq database。

Each table in the database is associated with a Matnap or Python object。

 where users manipulate data by invoking these Python or matlaub glance that encapsulate the corresponding tables。

Ma， the mat， the Matlab or Python object does not by itself contain the data。

 It's just fetched from the database if necessary。 So you。

 you bring that into your Python or Matlab workspace by， by calling a command like like this。

 This will go to the data， Ex the data and transfer it into your workspace so that you can work with it。

嗯。In principle， you can also use R or any other software that you would want。

To access your My SQL T tables。 but the。The language that my SKL uses is。Is a bit peculiar。

They are much less intuitive to standard my SK I queries and have a a very。So a lot。

 a lot needs to be learned。 And also a lot in the databases can be damaged by wrong queries。That。

Is encapsulated in this case by data joint。 And thus the user is more protected。So if we want。

 for example， to filter all the BMI values where the value is larger than 28。

This is very simple in data joined。But。For if you go to my SQL code。

 then you would need to write something like this， which is already much harder to， to learn。

Also parallel processing is easy because basically populating one line in a。

 in a certain relation or in a certain tuple，1 entry in a certain tuple can be done on one core。

 so one can simply use a compute cluster。To in parallelel， compute all the entries for a certain tuu。

And also， plotting relations or two builds is possible so you can give these objects plotting functions that allow you to easily browse your data with standardized plots。

So this is an example from one of our projects we had a well bank ago。 So here。

 a data set consisted of multiple quadrants stimuli was shown。

 there was some additional info for each quadrant。For each of these two photon imaging experiments。

 there were regions of interest that were defined for each of these regions of interest。



![](img/b1f215368247cdcd19ab292ad34266b2_62.png)

For a combination of stimuli， we extracted traces。 and then for a subset of these traces。

 namely traces where we used an noise stimulus， we then computed receptive fields based on the calcium info。

 And for the stimulus， for example， you also have an information table with metadata。



![](img/b1f215368247cdcd19ab292ad34266b2_64.png)

This is just the subset of the entire schema that we worked with。 Of course， these things， also。

 in the end， become quite complicated。But still， if you keep the data in such a nice and tidy format。

 you can always use it and go back。 You have the referential integrity assured。

 and just your entire workflow is much less prone to processing mistakes。You enter， you， the。

 the system also forces you to enter data into the database at the start of the experiments。

 It's fully configurable。 By the way， you need to write these classess for your for yourself or for the lab that you work with。

 It's not like they are provided， just the interface is provided。Then you can configure it such that。

 for example， post processing is carried out automatically once all manually defined component are present。

 So， for example， if you define ros manually， then the extracting of the traces occurs once the ros have been defined。

And then all the analysis， once they're in production mode。I implemented as data joint relations。

 and you get all the added benefits， Refential integrity， easy filtering。

 standardized access for everybody in the lab on top。



![](img/b1f215368247cdcd19ab292ad34266b2_66.png)

If you want to get started with this， there's an excellent tutorial website。

 tutorials dot datajoin dot a， O。It's a system that is open source so you can download it and use it without any cost。



![](img/b1f215368247cdcd19ab292ad34266b2_68.png)

With that， this is the has been the， the final lecture of the neural data science course。

 I thank you for your attention over the past few weeks。

And for all the efforts that you put into our coding exercises。

 I hope that the course has fulfilled your expectations that you have learned about various kinds of data in neuroscience that we now。

 now process as a data science lab and that you are as excited now about the prospects of using machine learning for neuroscience or for science in general and want to do more into that direction。

Thanks a lot for your attention。And stay healthy。

![](img/b1f215368247cdcd19ab292ad34266b2_70.png)

![](img/b1f215368247cdcd19ab292ad34266b2_71.png)
# 【香港科技大学】基于Spark的大数据计算--Big-Data-Computing-with-Spark-p10-05-02-03-数据框--BV1V8FmzuEHf_p10-

Okay， so another stage is set for us to move on to spark Sel， essentially。

 how spark was has been incorporated to。Also， handle。Also handle a sequQel， right。

 because people find that。Still， you know， RDD is an improvement over mat reduce。

 but still for many operations， for many program， people want to write。

 writing things in using RDD is not very convenient。 People still want to use Sqel。

 which is has been know there for over half a century。

 And people are very comfortable with writing SqL。 And so that's why people are built spark Sqel on top of Spark。

 Okay，So actually， in parallel， when people was developing Sq from other components， Sp streaming。

 know M L， M L Li the machine learning library and graph X for graph processing。

 they have also been being developed in parallel。 Okay， in parallel with Spq。 But then later on。

 we will see next time that Sq is now becoming another horizontal layer so that other components are my being migrated from。

😊，RDD to spark SqL。 Okay， but still， this process is not done yet。 Still， still work in progress。

 But then I think the trend will be moving to a sparkql based system。

 So spark Sq is actually very important to be able to master these other components。Okay。

 so for RDD if you only use RDD， then the entry point to RDD based spark processing is this thing called S。

 a spark context。 So if you use Jupyter or the shell， then S C is created already for you。

 if you use a standard application， and then you have to create a spark context yourself。

 similarly here， for sparkql， the entry points is this thing called Spk and again。

 so if you use the shell or Jupiter notebook。 then this spark session， its created already。

 you can just use it directly。 However， if you use a self can if you create create a selfcon application。

 then you have to create this spark session yourself。Okay。Okay， so the。

The counterpart of a table in spark SqL is this thing called a data frame。 And actually。

 this term is borrow from pandas。 Okay， and， and， and also are。 But then， of course。

 the underlying implementation is can be different。 And spark data frames is implemented。

On top of RDD， right， So although R RDD is is， is not being used directly by users。 not I mean is。

 is becoming less。Used directly by my users。 But however。

 RD still is a central component under underq。 Okayq is on top RDD。 So more precisely。

 a data frame is nothing but a RDD of row objects。 So it's a special objects。

 RDD can be R can be RD consist of any objects。 data frame is just a special RDD that consists of row objects。

 So what is a row objects。 Well， a row object so conceptually the same as almost the same as a in Python namely it can consists of any number of components。

 Okay the difference between a row and python tuple is that here the role the different components in a row have names so。

 so therefore they they serve as they correspond to a role in。Relationational table。

 so here is one example。So this row has two columns or two members， one is called name。

 the other one is called age okay and then the value of the name is Alice and then the value of age is 11 okay。

 I should say the row is very similar to a Python dictionary Okay they have they are cable pairs okay。

When you assemble many rows into a RDD， then into data frame。

 all these rows must have the same set of column names。 say the same keys。 So namely。

 if you have an RDD have data frame of of this kind of rows。

 Then every row must have both name and age。 Okay，So you can access the members， the components。

 the components of row in the4 in two ways。 Okay， this is actually the Python syntax。

 you can either use， you know， bracket， square bracket。

 and then you use this as you include the name of the the name of the component as a string。

 The other one is you don't use that don't use that as a string， you just use this dot。 Okay However。

 although the second one looks nicer。 and it's actually is more concise。 However。

 there is one technical subtle， you have to pay attention。

 namely if this name of row conflicts with its own row this own attribute。

 then it will you will run into problems。 and we actually see see a concrete example。Yeah， okay。

 let's go to this an example here again， this Python。This Jupyter notebook can be downloaded。



![](img/4cf1705586b6b4cb22ef251bfc1cfceb_1.png)

嗯。Okay， so so now let's see some examples on data frame operations。 So first one row so here。😊。

We have created row objects。Okay， so we print the row and this is just the content row converted as a string。

And then you can access the members of the row。Using either one of these two methods。

 and both work fine。However。If we add another， if we add another。If we add another member。

 which is called count。Then。Using this way， using this dot operator， this will no longer work。

I here like I want。 I'm trying to print the value of this count。 I was I'm expecting a one。 However。

 it returns something like this。And the reason is that count is actually a internal is a built internal method of this row row objects。

 Okay， so it is a method iss not a， is not an attribute。 Okay， so， so that's why it's returns this。

 this method。 If you really want to access this field。 You can only use the first method。

 which is use a square bracket。 and then use the include encloed the name of the member in a。

Single or double quotes as a string。 So this， this method always works。 Okay。

 so this is also always recommended way of accessing the members in the row objects。Okay。So， yeah。

 okay， let's go through the examples before coming back to the to the theory。

 So there are spark provides。 spark6 provides a variety of ways for you to load for you to construct a a data frame。

 So one method I'm gonna use here is to use the CB method。 So actually， the in the in this read。

Object class has。 It has a variety of method for you to allow。

 which allow you to read from a variety of file types。 So here we are reading a CV file。

 And there's some optional。Prirameterters， header tells that this C SV has a header so that you can actually infer the column names from the header field from the header of the C SE file。

 And then it also tells spark to infer the schema。 Okay So let's see example。 Well。

 this C SE file is just a。Just the standard CS file， which is actually a text file。Looks like this。

 right， simply it's separated by commerce and by commerceas。And the first lines is is is a header。

 Okay， and then if we read it the in。 And for little frame， we don't have collect frame。

 we don't have show。 And but because collect is bad anyway。 So the the show is always safe。

 show the show method will always， we only show the 20， the top the first， the top 20。

 the first 20 roles。 Okay， so even if little frame is huge， it is still safe to use show。 Okay。

 so this is also an action。 So recall that。😊，We said the data frame is just the RDD of row objects。

 RDD of row objects。 Thats， that's underlying implementation。

 which also means that the data frames are operations under frames are also classified into transformations and actions。

 transformations are still lazy。 only actions will trigger them。 So， so therefore， this。

 this read does CV。 This is actually a transformation。

 This transformations says file into into a data frame。 And this show is an action。 Okay。

 this ones action。 run it。😊，Okay， run， okay， and this show is the action。

 This will actually this will will actually trigger the computation and read the file， okay。

So what do mean by infer schema， because the C me file。

This C S file doesn't really have the type information。 It only has the column names。1。

2 this five columns。But the data frame requires similar to a relational table。

 It requires a type of each columns to be specified。 Okay， so。

 so what happens if you say in first schema is true。

 then this will spark will actually read the CSV files twice。

The first time the first time it scan the file， it will try to determine the best or the most specific type that is appropriate to to to every color。

 Okay， by most specific， we mean that okay， for example， here。

 a string is always appropriate because any any data type can be at the string。 However。

 this is not very appropriate for let's say building I D and building I。

 you can see that they are all integers。 so if you， if you treat them as a string。

 then certain operations that is only available for over integers will not be available。 so， so。

So after the first scan， Spark decides that okay， integer is a more specific type。

 It's a narrower type。 so it will assign the most specific type to each column。😊，For the second one。

 then， you know， it's just you cannot do， you cannot say anything more specific than string。

 So if you string。 And the third one is integer， the last one string and string。 right。

 So after this is what we mean by we， we mean by infer schema。 Okay， and this， this。

 you can actually print how a schema by using print schema of data frame okay。😊。

And there is also another condition called knowledgeable。 Okay， And so if you use infr schema。

 they are all true。 that that which means you it is allowed。

 You are allowed to put now as a value of a。Of a column。

So this is the one way of creating a data frame from a file。 In fact， in addition to CV。

 they also have text file， except a text file， you can only return a data file。

 a data frame with one column because a a text file is just。Every line is string， right。

 so the text file will only return data frame with one column。

 C SV can return a data frame with multiple columns， and there are other。

Ws to create the data things。嗯。You can also create a data frame from an RD。Okay。

 but the constraint is that the condition is that is RDD must be RDD rows。 Okay， so earlier， we have。

Oh， no， this is the other way around。 But yeah， we will see how to create frame from RD later。

 So here is create RD from data frame。 So this one is easier because data frame is an RD of rows。

 and this can be accessed through this RD member， okay。😊，In the of the data frame。 So the data frame。

 D F， the same data frame we we created earlier is RDD member will returnEssential will give us a reference to the underlying RDD。

 which is RD of rows。On this RDD， you can do whatever operation you want on RD。For example。

 you can do take， this will return the first three。Three members， so which are all role objects。O。

Okay， so now， of course， when if you， if you just do operations on the RD。

 then you will not use any feature S。 so， so， so that's so this， although this is available。

 this is not used a lot。 In fact， recommendation is to use data frame API directly as much as possible。

 okay。😊，Let's see some of the data frame API and data frame API are designed in a way to completely accomplish what SQL can give you。

 right， so all the standard SQL operations have been implemented as data in data frame API。😊。

Let's see some examples。 The first one is projection。 Okay， so this caused one to select。

 so this is called this。 So you can just do say select， okay。So when you， when。

 when when we first look at Sq， it give the feeling that this is not a declarative language。

 This is a procedure， it tells you。It tells you the sequence of operations。

 sequence of transformation that you want to do。 However， later on。

 we will see that it's actually declarative due to the internal。Cattalylist。All optimizer。 Okay。

 but for now， let's still， we can， we can。 we can take a procedural view of data frame API。

 This is just one operation， one transformation， which is a。Projection， okay， projection。

 although it's called select is actually doing a projection。 Okay， on two projection on two columns。

same thing happened here。 No duplicates are removed are if there are any， okay。

 this is same sematics as SQL。😊，Okay， so this example where we have a selection and projection。

 selection is accomplished by the square。 Okay， so it says that， okay。

 I'm not going do two transformations。😊，The first transformation is a selection。 Okay。

 is namely is aware。 So we only we only keep those roles where。

 where the country is smaller than USA。 So this comparisons between two strings。

 So so this is a lexographical comparison。 And then， but we only project on buildings。 Okay。

They buildings。So let's ignore this for now， okay。O， okay， anyway， let's看 delete that O。O。

So this will keep all the building ideas where the country is smaller than USA okay。

So know that this where function in Sp SqL takes a string as input parameter input argument。

 And this string correspond to the same condition as expressed in SQL。So this namely。

 this is really a sequel operation， comparing a column。to a。Stam to a constant stringO。So in fact。

 you can actually put any standard operators or even functions in SQqL inside this where condition。

 because this this is gonna be pared by spark SqL and translate that into corresponding operations in spark。

 But then the interface is still following the SQL standard， okay。Okay， so this。Literal。

This one allow this is actually a sparse sql function。 This。

 the its effect is to create a new column。 Okay， so this。

 so in general projection only select sub column， but you can also use select to create a new column。

 Okay， when you create a new column， there's two ways to create a new new column。

 one way is to perform some computation。 and the other one， which well see later。

 second one is to just to put a constant。 So constant literal。 So this lit I I T stands for literal。

 literal essentially means a constant。 So this is the same， same value across all rows。😊，So， yeah。

 because so now let's see that's essentially we'll go through the examples we did in the first half of a lecture。

 rewriting those SQLquiries using data frame API just to get some exercise on on this set of。Methods。

O。Allright。So we are using the same set of examples， same set of tables， namely the four tables。

 customer product， sales order details， sales order header， same as the before。

 I actually convert convert them into CSV files so that you can download and then play with them。

Okay， so let's see this SQel query。 Select product I D name。

 list price from product where color is black。 How do we translate that to sports SQel okay。So it's。

SQL is declarative。 And for now， at least Sp SQL looks looks procedural。

 but let's bear with that for the moment。Okay， namely， we just specify the list of transformations。

 the sequence of transformations that we want to perform。The first transformation is the selection。

 Okay， we only， we are only interested in black。 okay， in black product。 Okay， so that's the。

 the first transformation。 So this will only keep the。😊，Rose where color equals to black。

So no doubt this is a single equal sign。Why。Or because this is the equal in S Q L。

 in S Q L equality is a single equal sign。 So， so this is this。

 everything in this everything in the double quotes。It's sequqel， not Python。Okay。

 second step is projection we project on these three columns。And， and then we invoke an action。

 So this will return the result， okay。啊。Okay， so this is another example showing how you can。

 how you can create new columns。 So earlier， we create new column with the same value。

 What if you want to。Create new， create new column with which is the result of some arithmetic operation。

 Okay， so this is one example。So we first still， we only， we are only interested in black products。

 Okay， so here I'm also showing a different way of writing this condition。 Okay， by the way。

 where and filter they are the same thing。 They are aliases to each other。

 so you can you can use either。So in this example， we are using a SQL。

Expression to specify the condition。Here I'm， I'm using a Python condition。 Okay Python expression。

 Okay， so now this is not in double quote。 So this will be interpreted as a Python expression。 Okay。

 in a Python expression， we， you cannot refer to a column by using a string。

 you have to you have to retrieve that column。 so so this can be done by data frame dot column name。

 column name。 Okay。Again， there are two ways to， to do that。 You can also write。

 you can also use this form。I think this also works。 Yeah， this also works。 Okay。

 there are two ways to to do that。 Actually， this is always safer because if the column name happens to conflict with an interin member of if it data frame。

Maybe can't。 then this won't work but color is okay。A select is， this is the projection。 Okay。

 so the earlier example， again， everything in a string is interpreted as sqel sql。 So we can。

 you can just specify the column names。Alternatively， you can also use。

 you retrieve that column directly。 Okay， so without using double， without using the quotes。Two ways。

 when I'm showing two ways。 Both are fine。 dot S format or this square bracket。 Okay。

 this is the product I D column。 This is name column。

 So you can see that both are serving the same purpose。Okay。Alright。

 so now suppose we want to compute a new column， which is。The original price doubled， Okay。

 original price double doubled。 So know that you cannot simply write。Let's say， list。Price。

This won't work。 Okay， this won't work。 Why， Because whenever you write a string inside select。

 this will be interpreted as a column name， okay。However， this column doesn't exist。

 list price star 2。 This is not a column name。 So that's why it return an error。 So therefore。

 you have to use a。Use the Python way。 So namely， this is retrieving a column from from the data frame。

 Okay for this way， you can you can， again， you can use dot。

 Also that also works can also use a square bracket。 and then multi multiplied that by two。

 So what really happens is this spark has overloaded。 This has red defined the star。

 This is overloaded so that it can be applied between。A column， and a constant。

It has it it it actually has another overload， which is between two columns。

 You can also use this to multiply two columns。 Okay， so this will will return a new column called。

Caught list price times 2。 Okay， Of course， this is， this， the last part is optional。

 This is to make the results looks look better。 Okay， so if we we， if we don't have that。

 then the name of the column will be。The name would call will the expression。

 the expression because the name， which doesn't look very nice in particular when you want to use the result。

For some other transformations。So we give it a new name called double price。

 and this way we can create a new column， okay。Okay， any questions， okay， good。This is。This is， okay。

 so this is。Okay， similar to the this example， except that we are also doing。Yeah。

 so we are also doing a。A selection。Where we use a more complicated。

A more expression as the selection condition。 Okay。

 where we want to check about this is greater than something okay。I think for the wearer。

 it's okay to write this in。In a string as a。S a。Yeah， so this works。 Okay， so anyway。

 they they also could， you know。😊，Interpret this as S SQL， but it doesn't。 they， they didn't care。

 They didn't really care to do that。 So by anyway， so to for easy。For easy reference。

 just remember for where a filter then this whole thing， this whole expression can be sequL。

If you write a string， okay， however， for select for projection。When you， when you write a string。

 it has to be a column name。 Okay， It has to be a column name。嗯。Well。

 the other one doesn't work work either， right， So let's say this doesn't work， okay。Yeah。

 this doesn't work。 So because this will be interpreted as a string multiply by two。 Okay。

 and this doesn't correspond to any column name， okay。So this works。Okay， so next example。

 if this is a order by。 Okay， another order by says this is。Is in SQL。

 you just have a second another clause here。 We do another ordering。

 sorting after we have done the selection and projection。

Okay orderder by by default is asc sendingending order。 If you are， you， if you want dising order。

 there is a second optional argument， which you can use。Okay， so now let's go to some joins， okay。So。

Okay， this， this， these two queries are equivalent。 Okay。

 except that second one uses the join keywords explicitly。 The first one uses the implicit join。

 namely， we write the join condition inside the warehouse class。 Okay。

 this is a join between two tables， the order detail table and the product table。

We have one joint condition， one selection condition， okay。So this is equality drawing。 right。

 and this equality says that the product column in this table must match the product I D column in the other table。

 Okay， so this is。Called it natural drawing。 As I mentioned earlier， this is very。

Natural because it naturally appears in many scenarios。 The nice。

s not nice thing about Sp is that it supports natural joints。😊，Naturally， okay， so the the the。

 the syntax is very is very easy。 It's much easier than SQqL。 actually， So the format， the， the。

 the syntax is the following。 So this is the first table， and this is the second table。

 We perform join。 We we perform natural drawing on this。😊，Column。

 you only need to write a column once if the column appears in both tables and you want equality between them。

So this you don't in SQL， you have to write this twice and because。

This column appears in both tables。 You have to dis disambiguate them。

By adding the table name prefix。 So this makes the correct pretty long。

 So this is actually redundant。 Okay， it's nice that S remove this redundancy。 Okay， so when。

 when when， whenever a column。😊，When then the same column name appears in both tables。

 then you just need to specify this column once， okay。InThe international中O啊。So also。

 you have to specify this because even if two columns， two tables have the same column。

You may not want to join on it。 So， so， so that's why if you want to a drawing on this。

 you have to specify the column， the drawing column， Okay。

 but you don't have to specify it twice as in SQL。So this is a join。

 So this will return all the pairs of topples that can join that match on this column。

 and then after that we do a。呃。We do a。嗯。Okay， okay， my， my intention is to do this first。 Okay。

 so this is， this is more natural。 right， So this is okay， refer to a join， and then we filter。

 we filter out all the。Ts all the results where color is not black。

 We only keep those that our color is black。 And then we project on these require the columns。Okay。

So now where， where things start to happen。 Okay， I'm actually， I。我哋 game up the诶。

I I already spoiled it。 But anyway， So if we move the filter to of the select。This still works。

This looks weird because， you know， at so at first sight， it doesn't really。 it should not work。

 right， because。You know， this is a join。 Okay， of course， this join has no problem。

 And then the selection is okay， but then after selection。Color is no longer a column。 In the result。

 right coloror is not one of the five。Projection attribute。

 So we would expect an error because after this selection not after this projection of select。

No column is called color。 so you cannot do a filter on color。However， it is still， it works fine。

 It doesn't really change anything。 Okay， so what is going on。So let's try break this。

Down even further。 Okay， so we're gonna do the following。 We're gonna break。 So。

 so here we are using chainning to chair everything together。 So we， so。

 so here we even separate them out。 Okay， we well let's say we first do a drawing。

 they do the do the selection。 And then print out。 I'm gonna check whether the results indeed has no color。

 And this is verified。😊，In the printout， so in the D1， D1 is the result of join plus projection。

These five columns， indeed， no color。Now， I do D1 dot filter color X to black。And then I do D2 show。

Still， no problem。No error。 right， It doesn't have to。 So that let's maybe its， is's。

 maybe one guess is maybe if the color， if color doesn't exist， it will ignore the condition。 right。

 that's one possible explanation。 So let's do something else。Okay， so it's not really。

 it's not really ignoring。 It's really doing this selection。 Okay， with the true。

 with the original color column， okay。You cannot simply， you cannot simply make something up here。

 okay？That would result in an error。Okay。So this is， again。

 where a Sql board from SQL right So we we mentioned that in any relation database。

 the language is declarative and optimizer will be responsible for finding a good query plan Okay and in any relation database。

 there is a command called explain， which allows the user to look into the query plan。

 So because sometimes we may be interested， especially for Dbas Dbas are D Dbas wants to know how my query myqueries is actually executed so that I can optimize my performance。

 So similar something similar here is happening。 S SqL has this explain method。

 which tells you how this query is executed。And if we do that TD2 type plane。

We see something that is。Barely ir readable。But anyway。😊，We can still。

Pick up the keyword from this from this whole mess。 Okay， so anyway， this is trying to use to。

 to tell you the structure of the plan。 So namely each one of them is actually a node in the expression tree in the in the the plan is generally a tree。

 operator tree， right， So it's like like an expression tree。

 You want to do multiplication first and do addition next， you know。

 this is how we learn from primary school way the order of operation。

 something similar happening here， this this， this represents a tree。 the deeper it is。😊，earlier。

 it is。Executed。Okay， remember I that that D2 is the following。 D2 is computed as follows。

 We first do a drawing。Then do a select a filter。I know。

 join and then do a projection and do a filter。 Okay， so this is， this is at least this is our。

 this is how we told spark to perform the sequence of operations， our transformations。😊。

But if you look at the actual plan or called physical plan。 Okay， something。

 sometimes this is called a logical plan。 Okay， logically， I want the to do something like this。

 which doesn't make sense because color doesn't exist after the after the projection， however。

If you look at the physical plan。On the leaf level， of course。

 there is a there is some scan and then theres a filter。

 they often insert some not iss not not condition， but you can just ignore that。啊。

Then then this is for the， for the sales。 Okay， so for the。Sales order。Okay。A sales order。 Okay。

 which table for detail and product。 Okay， detail and product， see。嗯。Okay， so this is。

 I can these CE files。 Okay， so this is the sales order detail table and the other scan。Is the。

These columns。 So this must be， yeah。 okay， this must be the product。 Okay。

 well I have the CV file name。 So here the CV file name is okay， sales order。

 So this tree has two branches。 like one branch is reading one file。 The other branch is reading the。

 the other file。Okay， and then going upward。It。Perform this。 Okay， so yeah， importantly， this filter。

Okay on this branch， this branch raised the product table。 this， that's the the product table。

On the prior table， instead of performing a join。😡，It actually performs the filter first。

 And here we already have this color equals to black condition there。

So this means that SpQqL is really doing something smart here。So because when we write this。You know。

 if you are you are。诶。If you're sharp enough， you already know that this order of operation is actually not。

 is not optimal because， you know。Even even the first way， the first program we we， we wrote on here。

 Okay， so even the first program is， is that the code we wrote on is here。

 Even this way of writing program is not optional because we are only interested， you know。

 in a small number of products whose color is black。 And yet we did this drawing first。So actually。

 we also saw this kind of example in in the first lecture， right， because we， we are。

 we were we perform both a drawing and and a selection。😊。

And we know that we should do the selection first。 That can potentially reduce the problem size a lot because the joinin is very expensive。

 Join requires a shuffle。 and it is always a good idea to reduce the data size needed in a join。

 So the best way if we were to write， really implement the query is actually to do the filter on product first。

 namely， we should write something like like this。 filter。😊，Color equals to。Black， okay。

 we should do something like this。 This is just。Way better way。啊。O呀，你的。Okay， yeah。

 we should have done this。 this is much matter。 Okay， we， we， we， we， we， we， we remove as many。

A non black products first， and then we do a drawing， and then we do the protection。

 This is the best way， okay。But luckily。It doesn't matter。 Okay， so even though we wrote。Actually。

 even even though we wrote this in two stage， we actually we。

 we use D1 to point to the intermediate result。The say is physical plan for completing D2。

Is completely discarding our instruction， right so。

Sparco has is completely almost rewritten our query。 So it performed this。Selection first。

 and then it did also did a projection。 Okay， and before doing this， you know， broadcast hash join。

 whatever that means。 we will talk about what this means later。 Okay， anyway。

 the point here I'm trying to make is that it did something quite smart here。

 It first did this filter this selection。 And then it also did a projection。Earlier。

 as earlier as possible。 Okay， so here this projection is we only keep product I D and name for the product table for this 1。

 I only keep this5。attributes。Well， ignoring the rest。 And then we do a drawing。

 and then we do another projection。 Okay， so this is。Can be quite useful。In practice。

 because in practice， all tables， for example， product may have many columns， may may have some。

 let's say address may have remarks， Ph number。 All these are not needed。 Okay。

 so it will perform the will perform the projection as early as possible。

 remove removing the removing the unnecessary columns as early as possible。Okay。

 so this explains why it's not returning error。So this also means that， you know， it's， it'。

 it's still declarative in a sense that， you know， the spark will not strictly follow， okay， your。

Instruction to build the linear graph。Okay， so this is actually the key difference between RDD and sparkrsq and data frame。

 So RDD Spk will strictly follow the linear graph that you have ordered a spark to to construct。

 Okay， however， this is not the case in Sp okay。So， so finally， this will cause an error。 Okay。

 so here， what we did is I first do the drawing and then do the selection。

 And then I physically write。😊，The intermediate result into。Disc as a C SV file。 Okay， I write that。

 and then I load them， I load the back， and then I do a filter。

 So this will finally cause report error， because I'm so。😊。

So stubborn in in in in insisting that you need to give me the intermediate result。

The intermediatemedia results， indeed， if we follow this plan， the intermediatemedia result。

 which is D1， doesn't have color color。 Okay， so this， of course。Or if you are so strict。

 then Spark will have no way to get around and this will report this will result in an error。Okay。

So this is the example of a distinct。 Okay， so this。Requests really requires nothing to specify。

So this these essentially can be applied on any data frame。 Okay。

 so this is also give the procedure a flavor， namely if you want to。

Remove duplicates for a certain column。 You first need to do a projection and then do a distinct on it data frame。

Okay。Oh in this way， this distinct， in this sense， this thing is similar to RDDs distinct。

It is applied on the whole RD， how whole data。Okay。So this is a distinct count in Mexicoco。 we do a。

Selection first and thendist and then counter。Okay， so it's it， it's actually。

TheEx the opposite compare with Sqel。 So Sqel， we do count first and then distinct and then color。

 Okay， but anyway， I think I would think this is more readable right。

 So this because this is more natural。 And we we， we first are one color。

 And they I only one unique color。 And they I want to count。 So this is。😊。

I think this is actually more logical compared with standard SQL。Okay。

 this one is a group by example we。Fine， we want to find the total price of each order。 Okay。

 and return the order I D and total price。And column name should be total price。 Okay。

 so this is the sQel statement， and this is the corresponding corresponding。ASrs sqL program。

 So I first compute this aggregation。 This group by aggregation， Okay， so。

So this is how this is how we do that in Sp SqL， we first you select to create this column。

So this is one example where I I think SQqL is more， is more concise。 But anyway， so in Sp SqL。

 we need to create this column， this new column first。 Okay。

 so this can be done by using select okay。Yeah， anyway， this we use I use star here。

 it doesn't really matter because we can ignore them anyway。

 So the point that we are creating this new column following this expression okay。😊。

This is a column name times another column name， multiplly by  one minus column name。 Okay。

 And then I give a new name to this column。So here it's important to give it a new name because otherwise。

 there will be no way to refer to it。ok。And then I do a group by， okay？And then I do some net price。

 So this net price refers to this new column that I have just created。ok。Finally。

 I rename that column。 I rename this to total price。 Okay， total price。 Okay。

 so this method with column rename and alias。 they they serve different， they serve the same purpose。

 right they are， they can be， they both of them are used are used to rename of column。 However。

 the scenario in which they are used is are slightly different。 So with column name。

 This is a essentially a transformation。 it transform one data frame into into another data frame by renaming a column。

Into a new one with a new name。This alias is actually a function。 It's not a transformation。 It's a。

 it's a， it's a， its a function defining pro。 is， it can only be used inside is。

 is a is a function of a column。 So this whole expression will return a column。😊。

And then you you rename， rename that column。So essentially alias， this method。

 this function can only be used inside select。Cha I select。 Okay。

 although they essentially save the same same， they serve the same purpose， okay。Okay， so the。

 the alias is useful when this， you already have this whole column and you don't。

 So in the first situation， it's actually difficult to use with column renamed because this for to use with column renamed。

 you need to have a name for the old column。And this one has a very long name， which is hostpress。

 So it's actually easier to use alias。And in the second scenario， you cannot use use alias because。

Oh yeah。 okay， because some price， this will， this group buy will。This scroll by。 there's no select。

ItSo so。In fact， these are。This example is a good one in the sense that they are。

 they are used in exactly the sation。That they are designed for。Okay， let。

What happens if we remove with column green？ Yeah， okay。

 nothing happens except that is the result is not as beautiful。嗯。Yeah， so in this case， the。

 the column name will be this expression。ok。This simply did a final touch to the column name of the output。

Okay。Alright， so this example is showing the effect of having。 Okay， but as。

 but there's actually no counterpart of having in Sprsq。 Thiss no having。 But anyway。

 this is not a problem because as I mentioned earlier， having is really the same as where。

 if you rewrite that query using sub queryry。 And this is exactly what is being done in SprsqL。

We use where。 Okay， we simply use where。 because after this group by。

 this is nothing but another data frame。 and you can apply whatever you can apply whatever that is available on a data frame。

 including a filter where， which is which has the same effect as having。Okay， in fact。

 after renaming this as total price， then you can， you can use you can use total price here。ok。Okay。

 so this is one complicated example with join and group by and having。 Okay， so the the， the。

 the the query finds total price on black products of each order where the total price is greater than 10000。

 Okay， so it involves a join between two tables and group by and having and。😊，It's。

Spar in in Spq is written as follows， okay。Yeah， okay， so。So again， as we have seen earlier。

 this multiple ways of writing this。 So here we are trying to be nice to spark。

 We are already telling them。 We are， we are we are telling Spk the best way to do this， namely。

 we do this filter first， okay。And then we do， and then we okay， N yes， and then we do the。

When do this filter and do this， do No， do this projection and do this filter and then join the two together and then do the group by and then do the having。

 but it's。It's also fine if we did， it would also be fine if we did this。Later， okay。O。ok 本脑。

啊 ok 你先啊。Okay， this is same， okay。嗯。Again， although this looks more inefficient， but actually。

 it doesn't really matter。 So in terms of both net effect， and even the performance。

 they are the same because they will result in same query plan。

 and the spark will move this condition earlier okay。Alright。

 so the last example is the most complicated one where that we saw in the first half of lecture where we did a。

2 joins，2 inner joins， plus one out join。 plus goodbye and order by。 Okay， so so this is the sequel。

 Okay， this is the sequel。 And name we did。WeWe joined the three tables first by inner joints。

 and they are all natural joints。And there is also a filter condition here。

 And then we did a outer join， a left outer join。 And then we did a group by the and。

 and then a order by。 The reason we needed a outer join is that we want to repair。 we want to return。

 we want to return we want to。Retain。Customers， even if they haven't bought anything。 Okay。

 so that's the reason why why。 And we need an outer drawing， okay。So this is this is。In SQL。

 it needs a sub queryry。 So here， similar in first SqL， we need to。

 It's hard to write everything in one big in one line。 So we're gonna decompose is into two parts。

 And the first one is the join。 and second one is the outer join plus plus group by and everything else。

 So for the join and。呃。For the drawing and grow by， okay。Okay， so let's see。Okay， so。Okay， yeah。

 So yeah。 So the observation is that the outer joins， the group and outer join， they。😊。

The order in which they are done doesn't matter。 You can do the outer drawing first and then do do group by。

 or you do the group by and then do the outer join。 They have the same effect， because， okay。

 if we did the， if we do the outer drawing first。And then do the group by。 and。

 and and because the only the， the， the out join only join the customer table。

 join the customer customer table with with the， with the other tables。 Okay， so in fact。

 it's more efficient to do the group by first。 because and but， of course。

 this group by will not include any customer。That hasn't bought anything。 Okay， but， however。

 but as long as the last join is out of join， we can still keep all customers。

 even if they don't appear in the other tables。Okay， hopefully that is clear。 essentially。

 we first compute the total total sales for each customer。

 And then we use the actual join to find its first name， Last name。 The actual join is only needed。

 Its only used to find the。😊，The name of the customer。 So it is not used for anything else。

 so we can do the groupai first。Okay， so we first do the join。

 the two inner joins plus the group by together with the filter condition。

 And the last one is the out drawing is a left outer join Okay for outer join。😊。

You have to tell Spq explicitly。 So by specifying the third optional argument。As left outer。

I think a left also works。Yeah， left also refers to left out doing， okay， similar to sparsqle。Okay。

 and then I， then we do a order by。 and then we。Ascending is false。

 So we do descending order sorting。 Okay， so now you can see that， even if a customer。

Hasn't bought anything。 It will appear here as a now， Okay， as a now。嗯。So if we， let's try we。

 if we replace this， if we delete this，ly if the last join is also an annual join。What would happen？

Yeah， we， we will lose those customers。ok 嗯。When optimization in Pro Sql interacts with with the caching mechanism。

 something weird appears to be happening。 So let me try to reproduce。

The the phenomenon that has been observed。 Okay， so let's。

 so this is the same example we saw last time。 We first did a a drawing and then and did a projection。

 So drawing is the drawing is natural drawing between two， the data frames。 one is all the details。

 The other one is a product。 And it's a natural drawing。 and they will， we project on these5。 Yeah，1。

1 to ，5 columns。😊，Okay， indeed， we can check the result， the intermediate， this join result。 Indeed。

 it only consists of this five columns。 Okay， so now suppose I。Cash or persist the result。 Okay。

 so this table is actually cached in memory。 Okay， so let me go ahead and execute it。O okay。

 of course， I need to first load data。呃。Yeah， okay。You to first load data。And then， I will。Do this。

Okay， now I can run this drawing， and then I。Print out the。Ps out。So this time I cache this。

 this table。 Okay， this table is caching memory。 Okay， now suppose I I go I do the same thing。 Okay。

 then I add a filter。 Okay， so as we we saw last time because okay。

 this color is not actually one of the five five columns。 So we would expect an error。

 but actually the error didn't appear because because SqL was smart in deciding that all this all this selection should be pushed down this if you look at the when we look at the physical plan Spq chose to run this filter first。

 And then they they then they do the join。 Okay， and this actually also explains why the caching did not seem to work。

 Okay， let's verify this thing okay。Okay， so now， let's say we run this， okay。啊。Okay， so let's。

 for example， let's take one row and modify the result。



![](img/4cf1705586b6b4cb22ef251bfc1cfceb_3.png)

Moify the source file。So I will go ahead and。Okay， so let's say we。



![](img/4cf1705586b6b4cb22ef251bfc1cfceb_5.png)

There is a sales order， I D。

![](img/4cf1705586b6b4cb22ef251bfc1cfceb_7.png)

This one let's go ahead and modify its， let's say， mod unit price。The all the data can be downloaded。

 You you can actually try this on yourself。

![](img/4cf1705586b6b4cb22ef251bfc1cfceb_9.png)

啊。This should be the。

![](img/4cf1705586b6b4cb22ef251bfc1cfceb_11.png)

All the detail， yeah。Detail， okay。玩玩。诶。Okay， so let's say I modified that。Price to 29， okay。



![](img/4cf1705586b6b4cb22ef251bfc1cfceb_13.png)

Okay， whole hearing， See that this is updated， okay。

So means that means the caching didn't seem to work。Because if we。Read from this file。

 which is already in memory， then this。The， then the， this。

 the change I just made here should not be reflected because。



![](img/4cf1705586b6b4cb22ef251bfc1cfceb_15.png)

I， I execute。

![](img/4cf1705586b6b4cb22ef251bfc1cfceb_17.png)

And cache actively join and cache result。 Okay， and then the next time I run the same inquiry。😊。

Which is， I run D2。 D2 is defined on D2 is a is is a transfer is is a result by transforming by by doing a future on D1。

 And D1 is actually in memory。 So so however， the caching didn't seem to work， okay。诶。Okay。

 but let me try something else。Okay， so啊。Okay， so the only thing I did is to change the filter condition。

 Okay， is， is it' still a filter。 So if you look at the linear graph， it should be the same。

 except that filter conditions it is is is different。 So now let's try again。 Okay， of course。

 I start from the beginning。😊，嗯。Okay， okay run this and cache the results out， okay。呃。Okay， this。

 this is a different。 Okay because this is a different odd detail，1，1，0。



![](img/4cf1705586b6b4cb22ef251bfc1cfceb_19.png)

玩玩。呢个 seven nine。4， okay。

![](img/4cf1705586b6b4cb22ef251bfc1cfceb_21.png)

Okay， the the unit price is 20 something。 Okay， so I know this。



![](img/4cf1705586b6b4cb22ef251bfc1cfceb_23.png)

I changed this to 29。

![](img/4cf1705586b6b4cb22ef251bfc1cfceb_25.png)

Save it。Right it again。O， this time， the caching。

![](img/4cf1705586b6b4cb22ef251bfc1cfceb_27.png)

Worked， I changed the source file。

![](img/4cf1705586b6b4cb22ef251bfc1cfceb_29.png)

For this particular role，1，1，0，7，9，1，1，0，7，9，4。 And then the， the ugly result is not reflected。

In the query result。So， this time。It seems that this has worked。 Well， indeed， if I I'm persisted。

 can I run again and then。

![](img/4cf1705586b6b4cb22ef251bfc1cfceb_31.png)

Now it's reflected。So let me trend to the back。

![](img/4cf1705586b6b4cb22ef251bfc1cfceb_33.png)

Okay， well this also reflect because it its not， it's not cached。Okay。

 so this seems to be a bit weird because， you know。

 the linear graph is supposed to be same because the same set transformations is only the only difference。

Is this future condition the previous example in the previous trial， the filter was on color。

 a color equal to black。The second one is an orderer quantity greater than something。 Okay。

 so it seem that this small change has， has affected the query plan。

 especially on the caching behavior。Okay， yes。What if were you where set up。Okay， let's try。

 This shouldn't make any difference because be are。Which do you want to try as persist？ok。Okay。

 this is 20。

![](img/4cf1705586b6b4cb22ef251bfc1cfceb_35.png)

Let's change that。

![](img/4cf1705586b6b4cb22ef251bfc1cfceb_37.png)

It's still 20。 The caching is still， is still working。诶。And this shoes。Okay okay， of course。

 this is different。 This is different， this is a new one。 Okay， but now。Let's try。 Okay。

 this is still persist。Let's try again，20。诶。

![](img/4cf1705586b6b4cb22ef251bfc1cfceb_39.png)

Okay， or you， that's a different tu， Right，1，1，3。 I have to go 1，1，3。Okay， change it back to。20。



![](img/4cf1705586b6b4cb22ef251bfc1cfceb_41.png)

Okay， yeah， still， whenever the future is on its color equal to black， then the caching doesn't work。

When whenever the future condition is is the second one quantity order quantity。

 then the caching works。Okay， still。Oh okay， you want to change this to where。



![](img/4cf1705586b6b4cb22ef251bfc1cfceb_43.png)

2y。Okay， of course， I need to。

![](img/4cf1705586b6b4cb22ef251bfc1cfceb_45.png)

嗯。好。Yeah， still。 yeah， the caching doesn't work。And actually， the wear and filter they are。

 they are aliases to each other。 It doesn't matter。 Okay， so filter and where they are。

 they are the same thing。 So still they they， they， they the。啲。The key is this condition。 Okay。

 so think that this condition has changed the query plan。

 which is indeed the case when we when we really look into this， the the， the， the the physical plan。

 So that's why this explain can be very， can be very helpful。 Okay， can be very helpful。😊，Okay。

 so now let's。So yeah， so then so we know the query is essentially the same， have the same structure。

The only the only difference condition。 So， so whats。

What's so what's so special about these two conditions。O， know that the first condition is on color。

Which is not a column。Of the drawing result， of the cached data frame。 This is。

 this doesn't have color。On other hand。The second condition is an order quantity。

This one is a column in the drawing result。Okay， so that means okay， smart is really smart in in。

 in deciding when to use a cache result or not， whenever the cache result is useful。It will use it。😡。

Otherwise， it will just ignore that。 So it's so that's why the caching doesn't seem to be working。

 And indeed， this can be verified by examining the query plan。 So let's look at the， okay。

 let's look at the first， the plan for the first query where the condition is color。

 And we saw last time that when， when， when this is the case。 if there's no， let's， okay， still。

 let's， let's don't。Do any caching， okay？啊。Okay， we don't。 we don't do any caching。

 We know that this does not result in an error， even though color is not a column in the joint result。

 because this condition color。嗯。Is pushed down。 right the color this filter is pushed all the way down to the bottom level where。

 where this is just where this use。Immedialy， immediately after scanning the CSV file。

 So when the file is red， fetched from disk。As as early as that point， Sp tried to filter out this。

 try to apply filter condition， okay。And this。Plan is not affected。

Even if the inter Intermedia result is cached。Okay， so you can see that this is the same plan。

 Of course， it's hard。 It hard to hard hard hard to tell。 But trust me， this is the same plan。 Okay。

 whether the intermediate result is cash or not。This is this is the same plan， okay， exactly same。

However， now let's try the second one。O， so now I change the condition on from color to order quantity。

Again， we will first do this thing。 So we， we， we don't。We don't persist the intermediate result。

 Okay， this as expected， the same same as before。 Okay， namely， this condition。

 filter condition is also pushed all the way down to the leaf level。Immediately after files scan CV。

However， if this is。If the intermediate radar is cached。This time。Now， the plan looks different。

 Okay， so now let's try to find where the condition is。Okay， here， okay。So it's not。

 it's not push down anymore。 right， So if the intermediate result previously was。

 when the intermediate result was not cache， this case， this condition was all the way down here。

 right after the files scan C SV。 Now it's， iss actually after the join。 Okay， join is below。

And this is because spark sees that the drawing results cache is already in memory。

 It would would be。 it would be stupid not to use it。

 And if you look at the actual physical operator， this is a， you know， is this is in memory relation。

 And this is a in memory table scan。 Okay， so even the physical operator has changed from， you know。

By making use of the cached result。 Okay， so essentially。

 sparkql will try to use cache result whenever possible。 Okay。

 this is illustrated by changing this condition。 Okay， in when the condition is color。

 the inter is not useful anyway。 So caching it doesn't help。 Okay， when the second one。

 this is in this case， the intermediate result is useful。 In that case， sparkq will try to use it。

 do this。Okay， so yeah。 so this is the last example in the SQL review。 This is a complicated。

4 way join， right， we have two inner joins plus one outer drawing。 Okay， in SQL。

 we use this this present parentesis to signify the join order。

 We want to do this to inner two joins first。 And then we do this outer join。

 And the reason why we needed out joins is that we want to preserve。All tys on the left hand side。

 even if they don't join。 Okay， inner drawing only produce matchingtys。 if some。

 if some typo doesn't match anything on the other side， it will be omitted from the join result。

 okay in some in some applications， scenarios， this is not desired。 So we use outer drawing。

 So out drawing is remember it asymmetric。 there's left outer drawing right after drawing。

 then there' is also full after drawing。 in full outer drawing either side。

 Tpo from either side will be preserved。 even if they don't join okay。😊，So in sports sqL。

 we don't have prees。 But instead when it's actually more flexible， we can use。

 we don't have to then we can write in in two lines。

 we don't you cannot chain them together in one line。

 So that's that's difficult So instead we can we use a we use a we use two lines。 Okay。

 so D1 will den the two join results。 plus a group by。

 the group I can also be done after the second after after join。 It doesn't matter。 Okay。

 so the first is two joins， and then we do a group by on customer I。And then we do outer drawing。

 So by default， the drawing in Spqco is inner drawing。 Okay， so if it's outer drawing。

 then you need to specify， you need to tell Spo you want you， you， you want to do a outer join。

 So if you oit that， that would result in inner drawing。 Okay， so this is still a natural drawing。

 Okay，😊，so啊。By natural doing， we we mean that， you know。

 the two tables must have both tables must have this column and then the values on these columns on this column must match。

Okay， and then we do a projection， and then we do another order by。 Okay， we do order by。

 and then we show the results。 Okay， so this is。The last example from the sQL， from， from the SQL。

Okay， so know that this， although we are writing this in two lines is actually building one bigque because the first one。

Doesn't have a any action。 So this only builds part of the linear graph。And then this boost this。

The remaining part， Okay， the two lines together builds the whole query plan。 Okay。

 a two whole logical plan。 And then the only action here is show。 Okay， so this is still just。

 we write it in two lines because we want to specify the order。 Okay。

 Spec order in which the joins should be carried out， okay。Well， ultimately。

 you can also write it in one line by， you know， So， yeah， so you well。

 that that that can be a bit ugly。 You can write。 You， you just you just copy the whole thing。

And you replace D1 by that。 So this also work。 Okay， but that makes the code bit ugly。

 So this is more readable， okay。U。Okay， so because this， you know， the。

 the compatibility between Sprsq and standard SqL and SprsqQ actually also allows you to just directly embed S QL queries into。

 into Sprs code。 And they did this。Because， you know， many legacy code may be written in SQL， right。

 You know， it's if code is already is SQL query is already there， it will be nice to， you know。

 to support them as well。 Okay， so here is one example。Okay。

 we first to register data frame as a temporary view。 Okay。

 a view is nothing but a table as a a temporal table。 Okay。

 or you can so you can call it a logical table。 It doesn't necessarily exist physically。

 It's a logical table。Okay， so this means that， okay， data frame Df。😊。

I is registered as a SPOL table called this name， okay？And then。Os， okay， yeah， not define。Right。

 I need to read。The file here。O。Okay， so， so， so now they， so now you can call this spark dot S Q L。

AS do SQ。 So know that this is this is not a data frame。 This is a function directly under Spk。 Okay。

 so this allows you to execute any standard SqL statement。 Okay， of course， you here。

 you cannot refer to data frames in the SQL， you can only refer to table names。

 So that's why we need to register the data frame as a SQL table before in before calling any SQL query directly。

 Okay， and then this what is inside this spark do SQL function can be any standardq SqL statement。So。

 for example， this is selection and the selection select from where SQL。

 What is even more cool is that you can mix data frame API with SQL。 Okay， so here's one example。😊。

So I first suppose I want I first， each each， it's actually the same query。

 but we want to use data frame API to do this selection。And then， I。

Register the resulting data frame as a table called old buildings。

 because this are after this field condition， building H， greater are than equal to 10。Now this。

 the result of this filter has become a registered SQL table and then I can do any standard SQL on this table。

 for example， I do a group by account。All right。Okay， so now that this again。

 this is registering a logical table。 It doesn't actually exist。 Okay。

 so what is really happening is， is the entire entire。The two lines together define the entire plan。

 Okay， so namely， I， you， you tell， yeah， I want to first do a selection。 and then I do a。

 a group by， a group by account。 Okay this。Neither where or create or register temporary review is in action。

 They are both just transformations。 They just tell you， they just tell your intention to startq。

 Okay， the only in actions here， then which is only one that triggers execution of the whole plan and the benefit of design is。

 of course， now， you don't really have to worry about， you know。

 whether you are writing the right query， because you know， so of course。

 this one is the right one you do the selections condition first and then you do this go。

 but even if you do things in other in wrong order， it doesn't matter。

 The optimizer will automatically be able to rewrite the whole query。

 even though part of query may be written in SQL part of the query is written in data frame API。Okay。

So。Yeah， this is， yeah。 this is not an example where we， we， we， we first， we first use。

 we first use a SQL。 Okay， we do the selection。 And then for the group by account part。

 we use data frame API。 Okay， so this is actually equivalent to this one。They only。Appear。

 they only have different appearances， but logically， they achieve the same result。

So another useful construct in SQ L is this thing called UDF or user defined function。 Okay。

 user defined function。 This is useful whenever the standard SQ functions are not sufficient。

 You can do same。 You can do the same thing here in Sp。 Actually， this is even。More flexible。 Okay。

 because in in SQL， when you define a UDF， you have to use standard SqL language。

 So which is pretty restricted for example， you cannot do a loop in inside UDF here you can do anything because you can define a Python function as a UDF。

 So that gives you full power of Python。Essential， you can do anything with UDF。 Of course。

 here we we just illustrate by， by a very simple example。 Okay。Alright， suppose here。

 I want to define a， you know， just some， some some just as a， as an example。

 I suppose I want to compute this weird function called S language is really the。

 the which is really the the， the length of the string plus 2。 Okay。

 I just want to create this nonsense function just to illustrate how to define how to use UDF。Okay。

 so this function， of course， doesn't exist in standard SQL。

 but then you can what you can do is you can defend UDF by by， of course。

 by importing this method and then you defend you create your UDF by simply essentially passing any Python function Okay into in in when creating this UDF。

The only requirement is that this。You need to specify the return type。

 Okay and the return type has to be a sqL standard type， Sql standard standard type。

 So it's not a python type。 Okay， so not a python inteter Here it's a。

Interter type is defined in Sp SqL's SQ L library because the data types in SQL are not exactly same as those in Python。

 For example， in SQL， they have even have data。 They have money， for example。

 since types that are useful in when creating relational data。 Okay， but anyway。

 all the Python types are supported， but there there are something more。For this example。

 since a simple example， I just say that the return type is integer， well。

 actually even for integer in SQL， there are different integer types with different precision and this is Python doesn't distinguish that if you know that Python actually。

😊，Integer can be can have arbitrary precision。 Okay， in SQL， different integers may have a different。

 Digital typess may have different。Precisions or range。Okay， anyway。

 so any person function can be defined can be can be used as a UDF。

 And then after this UDF is defined created， then you can use it in your data frame API。

 Okay example then。 Then you can use as learn here。

 So know that this returns a this UDF function returns a UDF inq。

 So so that's why you can only use it inside select inside select。

 and the the argument to this UDF must be a column。 must be a column。

 So that's why we use this this D is data frame。 So D F country is a country column。

 you cannot use cannot say S learn just you can you cannot say just country。 Okay。

 so this is a string。 this is not a column。😊，The input to a UDF or any standard SQ spql function has to be a column when use inside select。

By anyway， so。Yeah， this gives the intended result。

 The S length is the length of the country name plus 2。 Okay。

 if you want to use your user your UDF inside embedded SQL statement。

 you will have to register it first， similar we use S do UDF dot register。 Okay。

 then this string gives the the name of the UDF in in SQL。 okay。啊。Okay， yes， yeah。 So here， yeah。

 So we register as then as as a UDF in SQL， and then I can write any standard SQL statement inside SQL。

 the SQL method using your your UDF。Okay。All right。Okay， so we have three question examples。

 and an RDD can actually be used to achieve the same functionality。 Of course， in fact。

 all data frame。Programs。You will be translated intoRDD。

You will be translated into RDD programs anyway。 So in terms of functionality。

 data frame API doesn't really give you anything extra。 So the question is。

 what are the benefits of using Sprsq。 So we already see the outsider and there's some other other benefits the first one readability。

 Okay， because you know， in RDD， you don't have column。

 you don't you still have columns because you can define an RDD as RD oftys。

 then every typo can have a number of fields。 However。

 the difference that in RDD you you as a programmer have to remember know which was what each column represents There's no names for the columns in data frame。

 every column has a name Every column has a type。 So that makes the whole thing more readable。

bil well talk about that later。 columnar story。 This is actually another important optimization。

 So all original databases， actually， at least the traditional ones。 they use row based storage。

 namely if you store the table inside memory on on on disk is store row by row。

 namely you you you first store all the all the fields of the first row。

 And then you store the second row and and and third and etctera。 Okay， So this storage。

 this story format is。Good for updates。 for example， if you want to update a certain role。

 you can just go there and update the different fields of that role。 However。

 this kind of storage is inefficient for analytical queries。 namely。

 we want to perform some bad computation。Because， you know。

 although this is not in the original design。In in in practice， when people use relation databases。

 the number of columns can grow very large。 initiallynitially， maybe there are only 5 or six columns。

 but after some time， people realize， okay， I oh， okay， I also need to add， I don't know。

 Maybe the birthday or and then some some some time later。

 people realize I need to add a phone number。 so the columns people keep adding columns。

 So the tables can get very wide。 actually if you。If you talk to the practitioners and people。

 the DbaA， the database administrators， they often see columns they often see tables with hundreds of columns due to you know due to many column being added after the initial design so when you perform analytical queries on these wide tables。

 this row based storage can be very inefficient because for analytical queries typically we are only interested in a few columns although in examples we often see select star in practice don don't people don't do do that。

 only select only projection only do projection on a few columns that they are interested in so this columnar storage can be much more efficient and namely namely internally when a data frame is stored they first stored the first column for all。

Rrows and then followed by all rows of a second column。 Okay， so this can be much。

 much more efficient。 You know， when the query only touches a few columns。However。

 this is inefficient for updates because if you want to update row， you need to go to many places。

 you need to update all the columns which are not stored conceptually in memory or disk。

But that's a tradeoff you have to make， because spark SqL is designed for the little queries。

 We don't do updates。 actually， Sp Sql doesn't allow you to do do updates。

 So that's why it's very natural for them to adopt column storage。Okay。

So we we already saw many examples of optimization。 by anyway。

 this is the whole pipeline for the optimizer。 So， in fact， they follow the same。

 same pipeline as in a standard relational database engine。 Okay， and they they actually they。

 they try to reproduce the same thing， although it's still working progress。

 It's not completely done finish yet。 Okay， so in the very。😊，So in the you the advert。你开下。So。

 so at very beginning， we see that the whole pipeline accepts both SQL and data frame API。

 So that means although you can use the user is allowed to use both SQL data frame API to specify their intention to specify their query the the only difference is only initial stage。

 Okay after that， you know， they merge。 so no matter whether you write a query using SQL or either frame。

 they will go through the same pipeline。 Okay， so namely in the very first step。

 the pass will already know， generate the plan no matter which which。😊，Form you are using。

So this is the initial one is called unresolved logical plan。

 And then they will they will go through this whole stage。

 which will I will not go into details because this is really same as the relation database But anyway。

 we will show you some of the organizations that they。

 they are doing so that you can understand certain things or you you can be less careful。 Okay。

 when writing your query。So the first one is a very simple transformation。 by the way。

 all these the majority of the organizations are called rule based。O， namely。

 they will apply these rules iteratively until no more rules can be applied。 And all of them。

 these are， in some sense， static， static in the sense that， you know。

 the the the optimization are done without looking at data。 they only look at the occurring。Okay。

So this is a simple one。 Okay， so this is a this is， this is called a constant folding。 Okay。

 constant folding。 What it means is that it will try to compute these expressions involving only constant。

 Okay， so this is actually one example， saying that a constant， a constant。At another constant。

You can rewrite that by computing this first。 So this， whenever this rule is applied， this。

 this rule is only applied at compilation time， namely before the query is actually executed。 Okay。

 so namely， they compute this one plus to only once。They don't have to do it for every role， right。

 So if you this often appears in select。 So if we don't do this。

 you would have to compute this whole equation on every row。

 because X here represents a attribute or a column。 So this is clearly very wasteful。

 So this constant unfolding can be is a very easy but very effective rule。 Okay， this is just one。

 one rule one constant folding rule you can imagine there are other others like subtraction。

 modification， All other operators。 So all the rules are there in Sp equalql。Okay。

 so the second one is。So， this is。Another one。 Okay， so this is okay， this are more complex example。

 The first one is okay， this one we already saw namely literal literal means a constant。

 literal plus literal is is not literal Okay， so namely three plus three3。

3 plus three can be can be simplifies to6。 The other one is a left so namely anything。Plus，0 is left。

 So namely x plus 0 can be simplified to x。 Okay， of course， there is， there is， is another one。

 So this one is not used。 Okay， so the， they will try to apply this transformation rules。Iteratively。

 until， until reaching a fixed point， namely reaching， no more ruless can be applied。Okay。

So S Sq is designed in a way that because Sq is open source。 the host spark is open source。

 So people can contribute new rules。 So that's why Sq continues to improve over。

 over the years and every time there is update， you know， the there。

 there's often some new rules being added。去。Okay， so this is a another example。 Okay。

 so this is slightly more， more complicated。 But anyway， this illustrate on the the。Data types。

 different data types use in SQL in Python， we don't we only have one integer， but in SQqL。

 there can be different integer types。 Okay， so， for example， they have this。They this。

 this is a long integer， the number of digits and。So， let's see。So the intention here is， is。

 is okay。Okay， so yeah in， in smart， this data type， there is a data type called decimal。 Okay。

 so this decimal type can support arbitrary。Precision， okay。

 where the precision is the parameter that a user can control。 right if this is。

 if you want a very long integer consisting maybe more than maybe 20 digits， you can specify。

 you can specify， specify that that。 But， of course。

 the downside is that is's more expensive to to carry out consultation over this high high precision integers。

 Okay， so this rule is saying that okay， if it realize， if it realize that the。The actual precision。

 the actual precision is not too high。 Okay， it's not iss less than 18 digits。

 Then the rule converts all these integers into logs into a standard long integer。 Okay。

 and then compute sum using logs and then convert result back to the original decimal type as required by the user。

So， in fact， in standard database like Oracle， they also have similar rules。 So namely。

 even if you define a very data column with very high precision。

 you don't have to worry about the high computational cost。

 you know because at at at the urban adviser will decide the appropriate level of precision to conduct to hurry out the precision。

Okay。😊，Okay， so this one is this example illustrate two other important optimization rules。

 The first one we already saw that。We already saw that in action， this is called predicate pushdown。

Also called a selection pushdown。 So namely the idea is for any selection edition。

 you should push that down， push that as close to source as possible。

 Okay so if you look at this query， this is so this is the original user query。

 which that a join first join between events and users， these two tables。

 and this is a natural join on user ID。 and then we do a filter on events on the city column in the events table。

 So that's a filter。 and then I do then this query does a projection on these two columns events that timest and users form so this is original logical plan this logical plan is following the user' code directly and then Sp SQl tries to optimize that because the first rule is the first first。

ize that this is a selection condition that can be evaluated。啊。Immediately。

 after the event table is read， is fetched。 So they push down this predicate， okay。

To below the drawing， Okay， because drawing is very expensive。

 we want to reduce the amount of data the drawing has to process。

 So this filter is is is pushed down。Okay， so of course， there are certain rules in in。

 in this operation。 For example， if this filter condition involves columns from both tables。

 For example， if this filter is， I don't know， maybe events dot city equals to users。

 users dot city or users do current location， for example， then this filter cannot be pushed down。

 because it involves both tables。 So only when this filter can be evaluated on a single table。

Can this rule be applied？Okay。The second room， which is also very useful， is column pruning。

 and this is also this is particular， this is particular useful。Together with column not storage。

 because， you know， in smart， they store column by column。 So so if you can prune a column。

As early as possible， then， then the。Those those unnecessary columns will not be fetched at all。

 okay。So again， if you look at this example， there are actually two opportunities to do this projection。

 So in the original in the original plan。There's only one projection， which is at the end。

 because the user did the projection in the end。 However， that's not the best way。 because， you know。

 suppose both tables have many columns， many， maybe hundred columns。

 most of most of which are not needed by for this query， so they can do column pruning very early。

 So namely they do a projection actually even before the filter， So because you know。

 because the table is stored column by column。 So if you do the if you do do the。Future first。

 then you will， you will still have to scan all columns。 But then if we do the projection first。

 then only these， in this case， three columns are needed。 Okay。

 so know that sportsq is smart or the in general， any database optimizer should not only look at the final columns the user want。

 In this case， the final columns， only two column are needed。 time stampamp and user phone。 however。

City and user I D are also needed。 Okay， why。Well， city is needed by the is needed for the filter。

 The filter is a condition on city。 So city， although city is not needed in the end result。

 it is needed by by the filter。 the other one， user I D user I is not needed by the user by in the final result。

 However， user I is needed by the join。 So if you don't have user I。

 there's no way for you to do for you to do the join。

 So similar similar similar happening here for on this branch， user I and phone。

 phone is needed in the end anyway， right， So we have to we have to keep it。

 user I is needed for the join。 So in general。The the columns that are should be preserved should include both columns needed in the final result by the user。

 but by the by the query。As well as any attribute needed to evaluate any of the relation operators。

 Okay， for example， here， we are filter。 we have drawing。 you can。

 there are other cases like group by， right if you do a group by on on some column。

 that column must also be preserved。 Okay， but the other columns can be pruned。Okay。ok 诶。Right。

 so so in fact， so a major missing piece currently in the in the first up is cost based Op or CBO in for。

 for short。 This is actually a very important component in other relational。DaabaseO第。

So what is cost base optimization， So the rule based organizations。Is our systems。

 in some sense easy， because of the rule based organization。 So， for example， these rules， they are。

 they only rely on they they can be done by only looking at the query okay。Maybe if they are。

Independent of data。 So no matter how the data looks like。

 these rules will always be applied because they are always useful。

 no matter what how the data looks like。However， you know， for some problems， for some operations。

 for example， join this。呃， whichch。How the query is executed will depend on the actual data size or some data characterizations。

 Okay， Spq so far have only done one cost based optimization。

 which is in choosing the join algorithm， okay， so we mentioned this briefly earlier Okay。

 so because for example， if we are talking about the join。 Okay， so between two tables。

 one is called R and the other ones S。 suppose each is partitioned into P partitions。 Okay。

 P partitions。 Okay， partitions。For a drawing， there are two algorithms。

 One is called a shuffle join。 Okay， namely， we will namely。

 we will apply a hash function on all typos and then shuffle， this is like a the shuffle in reduce。

 then we shuffle all typos with the same key to the same to the same machine。 Okay， anyway。

 we will talk about that in more detail。 when we talk about algorithm design。 But anyway。

 the cost of the shuffle join is simply everything。 So namely the size of our plus the size of S。

 So that's the amount of data that needs to be shuffled。Okay。On the other hand， the other。

 the other choice is to do a broadcast join。 Okay， so we actually did something similar when we talk about broadcast variables。

 so we can do a join by simply broadcasting the smaller table to all workers。

 and the larger table remain put stay。 They don't move。 Okay。

 So let's suppose that R is smaller than S。 So the cost of the the cost of the broadcast join will be P times R。

Okay， namely， only smaller one will be communicated， will be broadcasted to all players。

 to all to all machines。 Every worker should have a copy of R， and every worker has a。

Part has one piece of S。So which one of this is smaller， clear depends on R SNP。This， this is a very。

 this is actually simplest example of a call of a CBO， A cost space Op。

 namely the option plan depends on the data characteristicsization。 characteristics。

 Okay in this case， it's simple， only depends on the size。

So this is currently implemented in SpartqL。 SpartL will at run time check the size of the two tables and decide which join operation to use。

However， there are many other more complicated CBs for five example。 If this join is done， Okay。

 yeah， let's still look at this example。 If this， in this example， this join is done after a filter。

 after a filter。 So in this case。The size of a table on the left hand side。Is unknown。

 Spq simply uses the original table size， which is not may not be accurate。

 If the filter is highly selective， then the actual size of this table may be much smaller。 However。

 S doesn't know。 Okay， However， for many other， more， more。More mature databases like Oracle。

 They use statistics。 So what what what， what they do is they first collect some statistics on the table。

 For example， they may build a histogram on this column called city。Of course。

 this is more again more like an art。 this the DBA will have to decide on which column。😊。

Stat statisticsistic should be collected。 So if， if the DBA expects a lot of queries on with conditions on on on this column city。

 then he will instruct the database to collect。For example， a historyogram on city。

 namely the most frequent。Values， for example， maybe Hong Kong very frequent or Beijing is all very very。

 that may be the top K most frequent。Values。 And then if he has a hisscribe information。

 then the database will be able to estimate， okay， to estimate the size of the table after this future condition。

 Okay， then they can make a more informed decision in choosing the drawing operator here here。 Okay。

 so in general， this is actually very complicated process。Different statistics can be built。

 This is actually also a very active research area。 Okay。

 so namely how to build statistics statistics so that the cost of different operators can be estimate more accurately。

😊，However， this is not done yet in Sprsico。Yeah， okay。 yeah， the other benefit， actually。

 a major benefit is the flexible flexible data model。

This is where SrsqL is even better than a traditional relation database。

 a traditional relation database。😊，Only supports a flat table or it kind highly structured in sports circle。

 they actually support。In， in some sense， the sign structured data， namely。

 the data can have a hierarchy， specifically， they allow。They， they， they support Json file。 Okay。

 so namely， you can have a Json file to store to store your data。

 and then you can read your Json file into S Sql as a data frame。 Okay， so here is one example。

 the actual file can be。Dload it。Here， yes。Okay， so this is， this is a J Json file。

 which is actually nothing but a text file， but it has a。two ra core。With different， you know。

 column names and values。So this is， okay， for example， these are standard key pairs， ID name， price。

 and this text， this is a order list。A square bracket is a list。 It's actually your order list。

 And so this can also be a nested， namely dimension this column。The value of this column。

Attribute is another design file。 Okay， which has three fields，3， sub，3 sub attributes。Yeah。

 where how location this is another nested case。 Okay， so this。Data like this can be fetched。

 can be loaded into Sprssele directly by using sparkk do read dot JU。And schema can be inferred Okay。

 by Sp Sql automatically。 So you can see that this nested structure，And for each， yeah。

 this is extract is a double and long， so the type can also be inferred。Okay， again， what。

 what is happening is that data smart will read the file twice。

 The first time it will infer the schema together with the type。

 And the second time it will actually load the data。Okay。诶。You can， yeah， you can。 You can。 You can。

 can still use the F show， which prints out the contents of the table in a nice format。

 although for the sub fieldss like dimensions， it only prints out the value， but not the column name。

 because there's no space to print it。 Okay， However， you can still access them。By using this。

 by using this dot operator。 Okay， so name this is actually pretty intuitive。

 This dimension dot height retrieves a sub， a sub field， a sub attribute。Okay。

 so here is another example。Yes， the the syntax slightly different。

 This is just essential because select can accept both columns。 So this is a column。

A select can also accept a string， which represents a column name。Okay。However。

 if you want to perform any other operation， then you have to use the first one。 Okay， for example。

 you want to。Do height times 2。 Then you can， you can only use the first one， the the first four。

 the first form。So this is an example where you can do a filter。 Okay， on the subfus。 Okay。

 so tag 0 refers to。Yeah， okay。 yeah。 So tax。 So so， so tax is like different。 Okay， tax。 So this。

 as mentioned， this is order the list。 Okay， this is all， all called array in， in， in Json， okay。

So then you can use numbers， indices to access this different field。 Okay， so this is a nested field。

Nested。Attribute。Okay， you can take a closer look into the RDD underlying the underlying the data frame。

 So essentially， every design file is a row object， except that the row。

 the row objects can be nested。 So， for example， here， it's the first row is this whole thing。 Yeah。

 this whole thing。 And then this row objects contains another row objects as is one of its members。

Okay， of course， this nesting can be arbitrary。 You can have three or four levels of levels of nesting。

Okay。Okay， so now we're going to look at some examples of converting between RDD and data frame。

 because we mentioned earlier that for social operations iss more convenient to use RDD。

 but for others， it's more convenient to use data frame。 so you may need to convert between the two。

So this， the first example shows how to build a data frame from RDD。

 Okay you build a data frame from RD。 so you can simply build a data frame from a RDD of tus。 Okay。

 so here we are reading us。 this is standard RDD program， which reads。

 which reads a raise data from text file and parse that。Split them into two columns， Okay， two。

 so this is this RDD is just a RDD of tops， okay。And then you can just then create a data frame out of the RD by using create data frame。

Because RDD doesn't have column names， so the data frame doesn't have name either。

So they use this placeholder， underscore one， underscore two for the as the column names。

But the data type name the schema can still be inferred。 The first one string second one is long。

Okay， so this， if you want to give names to the columns。

 you can add this optional argument when you create the data frame。

 So this will tell data spark that the name of columns are name and age respectively。Okay。

You can also create an data frame from a row from RDD of rows。 Okay。

 because data frame is nothing but RDD of rows。 So this is actually more straightforward。 So here。

 what we are doing is we， yeah， this RDD is the same as before。 this RDD of this。

 this RDD of topples。We first convert that to RD rows by using map。 Okay。

 so this lambda function converts every tuple in the RD in this RD into a row object。 Okay。

 where the row object has two fields， one's name， one's age。

 and then you can create data frame from the RD of rows to。嗯。So， so here the。So the。

 if because they frame in in in in data frame， all the values in the same color must have must have the same type。

 But this is not in force in R， right， So in RD， the tops。Or even RDD rows， these tops。

 they don't have to have the same types。 Here we do。 In this example。

 the first one is always a string。 second one is the second one is integer。 However。

 is not necessarily the case for RDD， RDD doesn't enforce， doesn't do type checking。 However。

 example， you can actually construct RDD of rows where the first one the first one is always string。

 but the second one。 the first row is a integer， but second one is actually a string 1，2。 Okay。

Then when you， when you convert this RD into a little frame， then so obviously。

That smart doesn't like this。 doesn't allow this to happen。 So what is happening is that it will。

First， decide type， we create the frame of first decide type。 In this case， it will， it will。

See the first row。 The first row has an integer here。

 So the type of H will be set to be an integer and any other remaining rows with incompatible type will be turned into nos。

 So this， this string 1，2 will be ignored。So this， I can this illustrated key difference between RDD and data frame。

 So RDD allows different types， okay。So this one returns the content as RD of rows。 Yeah， yeah。

 because， yeah， this is converting data frame back to an RD。 Okay。

 after converting that to back to an RD， then you can use any standard RD operation on that。Okay。

 yeah， some notes。 So little frames are stored using column column or storage with actually with compression。

 I didn't mention this。 This is another author。 So the idea is that when you are。

 when data is store column by column， there is more opportunity to do compression。

 because because all data in the same column， they have the same type。😊， so and。

 and what's happening in practice is that very often adjacent rows have very similar values on the same column。

 for example。If this column is the primary key。 is I D I Ds are likely increasing。

 then what they can do， they they can use the run lens compression scheme。

 they only store a difference。 They don't， for example， I D is maybe A D long。

 but they they only differ in the in the in the in the last dig by one。

 Then they only need to store a difference。 So which can save a lot of space。

 So this is a very common compression technique。嗯。On the other hand。

 RDD are RDD are start using row storage without compression。 Okay。

 so that's why data frames can be more efficient for the same task。嗯。

Even assuming the RDD programs have been。All opt manually for RDD linear the linear graph in RDD。

 you know， spark will just follow strictly your linear graph， your plan without any。

Attempt to rewrite it。So， yeah， so lastly， so we we talk about yeah， caching the caching behavior。

 So similarly， a closure also exists in data frame because data frame is just you can't consider as the optimized RDD。

ok。However， something where is happening again。 So let's， let's see this this， these examples。Okay。

 so first I create a data frame with these two columns they have they actually have identical values。

Just for the purpose of illustration。Okay。So in in fact， you cannot， you cannot even do this。

 You cannot even do this。This will create， this will result in error。 Okay， yeah。

 the reason is that created a frame expects a list oftys。 You cannot just give them a。

 give it a list。 It has to be a list oftys。If you want to create a data frame with one column。

What do you do。You must create a list of taps where every table has one component。 So that's， yeah。

 you can， you can， you can do that in in in。Okay。So until now let's see。 now， let's see。 Let's。

 let's try to re reproduce the same results we did earlier with RDD with the closure behavior。

 We remember that。 So earlier， we did the same thing on this RDD where we make。

We where we made a transformation where where the condition is a smaller than。 Okay。

 smaller smaller than x， where x is a global variable。嗯。

If you should remember when we did this for RDD， the second time。When we examine。

 when we invoke connection on the RTD， the new value of x。Is applied， because。You know。

 X is a global variable。 So X will be packaged into the closure sent to all workers。

Every time an action is in in is invoked。 Okay， so the first time this is invoked。Value 5。

We will replace this X。The second time it is invoked， value 3 will replace x okay。However。

When we do this on a data frame。This is not happening， okay？Namely， the second one。The second one。

Is still using the same， so same result。 So as if the D F one has been cacheed， Okay。

 although it's actually although it's actually not。 So even if we do persist。

Although partyy fought his em。Anyway， right， so this is actually redundant。 Okay， but anyway。

 even if we do and persist， we can see that it's， it's still the old value of x。 Okay。

 the old value of x， okay。😊，嗯。Okay， so why？Okay， so chlor behavior doesn't seem to exist。

 which doesn't make sense， right， because we know that data frame is still implemented as the RD。

 So what is happening。Again， if you have trouble explaining phenomenon。

You ask Sp circle to explain for you by using explain。Okay。

 so the physical plane in this case is rather short。

 it rather simple because it's just one transformation filter， okay。

So now if you examine the physical plan， you see that。There's no x。 It's actually5。It's actually5。

 So this is actually the effect of this optimization shoe called constant folding remember。

 So what is happening is that the first time you invo action， the whole plan will be optimized。

 will will be compiled and optimized and Spark sees that hey， you are using a global variable。

 whose value is known So so why don't we just replace that by a constant so which is why that which is why the5 is written。

 is written there。And they do that for a reason， because。You know。

 what if you are using very some very complicated expression。

 So here I'm creating a another made up example， which says I'm going do I know select times 2 and plus even a function here and plus  one plus  one and in function I'm。

😊，I'm return x over to where x is a global variable。 just anyway。

 just maybe you are doing some crazy computation。However。

 we know Spk knows that anything that you do here。Is independent of the column。 So namely。

 if you are doing the same， it's essential， you are doing the same thing on every row。

 which is a lot of redundancy。 So， so smart is is will try to optimize it by essentially unfolding by precomp everything。

By by precomputing as much as it can know that this part cannot be simplified because this depends on the actual value of the column of the role in that column in this column the the other part is independent and this can be precomputd more。

 more， more precisely know， it will first evaluate this function F， which returns x over2。

 which is 2。5。 and then its plus one plus one right and and。And so， and so， so this is。

What is the this is。I think they should also actually compute convert that into 4。5。嗯。Okay。

I don't know why。 Okay， I think in the early version， the。Have 4。5。开 try。

Maybe they change this explain，4 times5。Maybe you， maybe there's maybe there's a new bug introduce。

 So it seems that they they。😊，They messed up with the。With the asciivity。

The association rule somehow has been messed， but I think we should。

Or maybe you guys can file a bug report to spread Sq。 So if I do， if I apprenticice。

 can see that this is 4。5。 So they should do that。 even if without preice。

They could have realized that this。This plus is associative。 It does order doesnt matter。

 And this should be simplified to4 to4。5。 Okay， that can save a lot of redundant computation。

But anyway， the point is that， you know this is the reason why the closure behavior doesn't seem to be happening for the data frame。

Because of the catalystist。Oizer optimizeizer， the catalyst is just a name of this optimizeizer of this project。

Allright， okay， yeah。 okay， so。Yeah， so this is just。啊。Yeah。

 just we' we do the same thing on RDD we can check indeed， closure is working， is working。Yeah。

 this is the same example we saw last time。Okay， all right， so yeah。

 I think the message is that when you write program in data frame。

 remember the optimizevisor to keep that in mind so that you can explain certain weird phenomenon in case they happen。

So here I prepare another example。 we are rewriting the PMI example。 We earlier use RDD。To do。

 to compute PMI。 So here I'm using SpqL。So let's just walk through this example quickly together。

 it's actually， you can see the readability is better compared with RDD。😊，So we first read this data。

 which is a list of additive non pairs。This will read data into。A data frame with only one column。

 because this is a text file。 Okay， so there's only one column and using a default column name called value。

So now we're gonna split this one column into two columns。 right， so we're gonna。

 we're not gonna we gonna do that using two steps。 The first one is yeah， we， yes， remember。

 data is dirty。 We need to。Future them out。We only we only keep those lines with two words。So， yeah。

 so this is what we did using R TD。 So now we are using Sp sql。 Okay， so in RDD， we use L do split。

 This split is Python split。On the string。Here we are。 So essentially。

 a spark Sql has migrated all the standard Python functions SQL functions。

 So this split is from spark sqs function library。 So it splits a， it splits a column。

 so this line line 0 is the only column right lines only has one column。

 So this is lines only column， and this split is spark ss split using space。

 And then give it a new name W。 and then we do a filter and the condition size of W is equal to 2。

 this size again is。😊，Oh， no， okay， this size is， is Python's size。I know。

 This price is spae equal size。 So it it's， it's essentially here。 This W is the。Is the column okay。

Okay， then the resulting table looks like it this。Okay。

 and then when you split that into two columns， we can do that by using also select。 So words。

Is this table。 Okay， W is its only column。Is the first column。the first component give it a name。

 AD DJ additive and second component。Give it name， which is now。Okay， so after that。

 we have a data frame with two columns Editive and none。 So now data preparation is done。

 You can see that now we have a data frame with meaningful column names。 So earlier in RDD。

 we have remembered which， which ones additive， which ones now。😊，Okay， this just。Yeah。

 the same thing， Okay， count。Okay， now we need to compute the frequency right。Remember。

 we need to compute three frequencies， the pair frequency。The additive frequency and non frequency。

 And each one is very similar。 For example， the first one。This is just a group by both columns。Okay。

 the groupai can have more than multiple columns and can。 and then we feel it。

 we only keep pairs that are frequent enough。 So after that， we have this thing。And similar， we do。

Addditive count and non count。 we rename the。The count column。One is called AD， ADD count。

 One is called non count。 Okay， essentially same thing。 You can see this is。

So you can hopefully you can agree that this， this S program is much more readable than the RDD program。

 okay。😊，So finally， this is the best part， okay。😊，In the artist example， we use broadcast variables。

 Okay， we have to retrieve them as a Python dictionary and a broadcast and。E cetera。

 and this is inefficient and not as readable okay in Spo， this is just a threeway join。

 you just join the three tables together okay because you want to match the same editingitive you want to match the same man So this is just the two natural joins after the join then the three frequencies are brought together then you can compute you can compute the PI according to the formula directly I'm also saying this is more efficient because you don't have to worry about which join algorithm is used earlier you have to decide that on your own here you know Sco can decide that。

Cleverly， depending on， depending on the sizes of the three relations。 if one。

 if one or two are very small， much smaller than the other。

 then they can they will use a broadcast join。Otherwise。

 they use suff join so they can make this decision。optimalptim on your behalf。 Okay， so this。

 I hopefully this illustrates both that illustrate the fact that S SqL programs are both more readable and more。



![](img/4cf1705586b6b4cb22ef251bfc1cfceb_47.png)
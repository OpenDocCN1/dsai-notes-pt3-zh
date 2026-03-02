# 苏黎世联邦理工《工程师的大数据｜Big Data for Engineers - ETH Zurich - 2024》中英字幕 p10 5 - Syntax (1_2) - .zh_en -BV17FAmeFE9K_p10-

Wecome back， everybody。 So let's move on to the next lecture on syntax。😊，So here's an intro。

You remember these fundamental data shapes， right we have trees， we have graphs， we have cubes。

 we have tables and we have unstructured data right And now I'm also I'm going to share with you I'm considering adding a sixth one because now it's becoming too much of a buzzwe to we ignore。

 but I need to see if the hype comes down。 that would be vectors， collections of vectors。

 vector database。But anyway， for the purpose of the lecture we brushed up on tables at the beginning of the semester and for lots of this lecture this course we are going to focus on trees right。

 but I want to tell you a bit more about why trees。

 why are trees so interesting in the context of big data。



![](img/2c75a3909261bc406bb31ac6f1006ef5_1.png)

So this is where we are。 This is the technology stack。 We are done with storage。 Now， you。

 we know where to store data that is large。 We can store it on Amazon S 3 on Google Cloud St on Amazon Blob storage。

 Asia Bb storage story。😊，嗯。But we we need to know what to store in there， right， Because for now。

 we just know we can store objects or files that are just beats， right， So what。

 what does these beats then look like， So today， we are going to go on a higher level and talk about encoding and syntax encoding very briefly and then syntax a bit more。

😊，So syntax is about how to turn data into a text representation， just characters， letters。

So theres many， many different syntaxes。 I'm pretty sure everybody knows about CSV。

 who knows about CSsV。😊，Okay， you go to any websites like I don't know the the federal Office of statisticsistic。

 and you can download pretty much anything in CSV。 This is one of those。

 And then you probably also heard of X statement and Jason， which are alternates in Texas。😊。

And RDF would be for graphs。 Doctor also for graphs X B R and for cubes。

 this will be less the focus of the lecture， right， Who heard of X and Jason。Oh， this is fantastic。

 Okay， so you know a little bit about that。 So we just dig a bit deeper。😊。



![](img/2c75a3909261bc406bb31ac6f1006ef5_3.png)

Now， something important is that。On the level of S3 or Azure Blob storage or HDFS， we store bits。

 ones and zeros。Now， you can store a lot of things as bits。 And I told you， for example， videos。

 pictures and so on。😊，But for data， we love to exchange it as text in a text format。

 actual letters of the alphabet and symbols。One of the reasons is that a human can look at it and understand right we'll see later in the lecture that it doesn't have to be text there actually you can also store data in a binary form and we will see that it has advantages but well focus on data in a text form or for today。

😊，嗯。😊，Now， if we want to start text， we need to encode it into zeros and one。 So how is that done。

 I'm assuming a lot of you are familiar， but I just want to make sure that everybody's on the same page。



![](img/2c75a3909261bc406bb31ac6f1006ef5_5.png)

So the characters are letters like ABC D， parque， lower Arques， the diggiits， the dot， the dash。

 the ccoone and so on。 How do you turn that into zeros and ones Well in the very early days of the computers。

 the first way to do that was called ASI， whohar of ASci。Okay。

 so ASI has the IDs that you have a catalog of symbols in that case， 128 for ASI。😊。

And every one of these characters gets some number。 you like you counts them。 This is the first。

 This is the second。 This is the first。 and you have a number between 0 and 127。

 without starting to count with a0 in computer science。And what we got was a table like this。

 this is actually on purpose taken。 looks like archaeology， right。

 but there are documents where you can see it goes like this like this is 0，0，0，1，2，3，4，5。

 all the way to 1670，33 and so on and so on。 It goes like this all the way to 127。😊。



![](img/2c75a3909261bc406bb31ac6f1006ef5_7.png)

![](img/2c75a3909261bc406bb31ac6f1006ef5_8.png)

RightNow how do you encode numbers in zeros and ones。

 where it's only a matter of convention because you know since primary school we count in base 10。

 we have 10 fingers so we have 10 digits。😊。

![](img/2c75a3909261bc406bb31ac6f1006ef5_10.png)

But you know that base 10 is completely arbitrary， right， We could also have had base 12， actually。

 base 12 was popular， right， when you counts eggs， for example， in in dozens。

Well one of the base we could take is base 2， so we can also express numbers in base 2 just with zeros and ones。

 And this is what you get in here。😊，Where you have every number between0 and 127 can be expressed with  seven bits。



![](img/2c75a3909261bc406bb31ac6f1006ef5_12.png)

![](img/2c75a3909261bc406bb31ac6f1006ef5_13.png)

So these are the first three。 and these are the last four。 And whenever， for example。

 these four here would be 0，1，1 followed by 0，1，0， right， So 0，1，1，0，1，0，0。



![](img/2c75a3909261bc406bb31ac6f1006ef5_15.png)

Encodes 4。 So now you have a mapping。 Every character here can just be encoded into0 and ones in that way。

 It goes in both direction。 You can write or you can read。 So that's solve the problem。 right。

 Now we we can have text。 And we know how to store it as zeros and ones and to read it back to letters。

 Now theres a few more that arrived later， why， because SQ was specific to English。

 And you know that in English， we don't have accents or any complicated characters。

 There used to be some， but somehow they disappeared in the 19th century。😊，嗯。

But we do have special character in Sch， for example， a lot of them。

 especially if you use the the spellings that use also these acutes and and so on， all the accents。

 The problem is that there are so many languages in the world and so many different accents you can have。

😊，That everybody developed their own encoding。 So Iol  in one， Latin1， also known as Io 88，59。

1 is for Western Europe。But there was yet another one for， I don't know， Eastern Europe， China。

 India and Suanzo。And at some point， we needed to unify all of these because that。

 that just couldn't be that we have all of these separate。Ways of encoding。 And there came Uniiccode。

 Uniode is an absolutely gigantic catalog of symbols that all assign Every symbol gets a number。

 basically。😊，And an encoding of Unicode is UTF 8 and UTF 16 right these are possible ways of putting that into zeros and ones。

😊，嗯。😊，Unicode now is pretty much done in the sense that almost all the languages in the world have the symbols encoded in there so that now the。

 the working group is mostly focusing on emojis。 like every every time Uniode is updated。

 you get new emojis。 and that's actually very useful。

 But what I want to say is that for the alphabets， that's kind of taken care of。Alright。😊，嗯。

And this is just an example， you don't really have to worry for the purpose of the lecture。

 this is just to show you that unlike S key where it's always going to be seven bits。

 plus maybe a zero in friend to make it eight。But in the case of UTF 8， it's elastic。 It's magic。

 if it's a character like。😊，From English， then it's going to fit on 8 bits。

If it's a slightly more complicated character， like I don't know Greek letters in math that fits on 16 bits。

 always a multiple of 8。 And if it's a more recent symbol， like the euro symbol。

 which which is just few decades old， then you will need in that case，24 bits， right。

 So it's elastic automatically， right。😊，You don't need to understand the details。

 This is just that there is a way based on the number that it has in the Uniode catalog。

 you can automatically map it to the zeros and ones。

 So all you need to know is that you can map it and you can read back the symbol。Alright， by the way。

 who already experienced that you try to open a file that contains the o La Om Laud O Las and you try。

 I don't know to import the CSV in Excel or fees And then you notice that instead of the Um La you get weird symbols like square root and so on。

 who saw that Okay that's because of the encoding right here basically means that it's encoded maybe in UTF8 and you try to open it with isolating in one So the decoding with the zeros and ones is basically incorrect This is where it's from Now you know。

That this is the reason。Okay。So now we solve the problem。

 we know how to store letters and digits and symbols as zeros and one。

 so now we can forget about the zeros and ones and reason one level higher with characters and letters and symbols。

Okay。So。CV you already know， I'm going to start from there。

 CSV is basically a text representation of tables right Coma separated every comma basically separated the cells on the first line。

 typically you have the headers which are the name of the columns and then on every line you have one row。

 one record， one business objects， if you remember， So in that case there are two business objects。

 one and two that I put in there Okay， three columns， two rows。I hope this is clear to everybody。

 right， the mapping between CSV and the table。So you see that here。

 the idea is that we have something that is technically logical as part of a data model with Rose and Collins。

 You know， you could almost treat it mathematically。



![](img/2c75a3909261bc406bb31ac6f1006ef5_17.png)

But we represent itta's text， ID commma， LST space， and this is text， right。

 but this is a textual representation of the table。😊。



![](img/2c75a3909261bc406bb31ac6f1006ef5_19.png)

Now， as a word of warninging， if I just show you this， it looks like CSV is extremely simple。

 be careful， CSV is extraordinarily complicated and the reason it is complicated is that there are so many different conventions in how to write CSV that every time you want to open a CSV file you need to first tell how to open it for example。

 you could use commas， but some people use tabs or semicollons as separators or spaces then there is the question of what do you do if you have a coa that is inside an actual string like for example。

 general special relativity here there is a comma but I don't want that comma to be interpreted as the separation of a cell it's actually part of the part of the text So what you do you put quotes around it and the quotes tell you okay that coa is special the comma inside the quotes is not a separator it's really a real comma。

😊，But then what happens if you have quotes inside like on the row2， now you have quotes。

 So what do you do Because the quotes should not be recognized as quotes of CZ。

 but actual quotes that go in there。 So what do you do， you triple the quotes。 So。

 you double the quotes。 So you have an opening quote in there。

 a double quote that means it's an actual quotes， an incomplete nest and a double quote。

 meaning it's an actual quotes in and so on。 So you see it's complex。

 And there are so many conventions， There are other ways than the double quotes。

 Some people prefer to use backtes and so on。So there is an RF equaled RF request for comments，48，80。

 It's one of the places where you have a lot of standardout RF。

The problem is that in practice everybody does a little bit what they want and so it requires a bit of effort to basically open the CSV files who's already been through that trying to open a CSV file and having to deal with all of that so you have a bit of experience with that okay。

So。Now。CSV for East Fork paperss。Now， in the first week of the course。

 I told you about these normal forms， right， some of you already knew because you attended information。

 some systems were engineers， some others us got scared probably like what are normal forms and why suddenly am I throwing at you all these normal forms in the first week。

Basically， a normal form is the ID is simple。😊，The idea is that first you don't want tables in tables in tables in tables you want everything to be flat it's the first normal form and for the higher normal form you basically want to have a lot of tables that each do one thing rather than a gigantic table that tries to do everything right for example you want to have a separate table for students a separate table for course。

 a separate table for rooms and so on and so on then you can say you're in high normal form right if you're in low normal form imagine that at TH the database were stored in a single giant relational table that has everything the lectures。

 the students and so on that would be very very hard to manage and to modify every day。

So there are many normal forms。 and one of them is called boy Sc。 There is， there is the second。

 the third， the fourth and so on。 So there's many of them。

 but I have good news because as I told you in the first week， we're going to throw them away。

 it means that for the purpose of these costs。😊，We don't really care about what having many different tables and each table does each thing。

 we will not even care having flat tables， we will even accept tables in tables in tables in tables that's going to be fine with us so the first second and third normal forms and the voice got normal form they all go right there for the purpose of that lecture。

Why， of course I need to tell you why， right， there is a reason for that。嗯。

It's because in this lecture for big data， we want to analyze data。So typically。

 when you analyze data， you connect to the Internet。

 you log into a website and you download a data set， and then you analyze that data set。

You don't actually want to modify the data sets or to update anything。

 You just take it as it is and then you analyze it。 This is very different。

From having a relational database behind a web where the people are shopping and they updates their。

 their shopping carts。And they place orders and so on。 So here the data keeps changing。

 but not in big data here， we just download the data set and don't touch it。And the idea is that。

The reason we want the normal forms in a web， for example。



![](img/2c75a3909261bc406bb31ac6f1006ef5_21.png)

Is because we write a lot。 And when you write a lot to the data。

 you really want to spread it across plenty of tables that are flat。

 So if it's right intensive to avoid these ugly things called a data nomadies onconsistencies and so on。

 But it's in our case， all we want to do is download the data and analyze it。

 maybe in Jupyter notebooks。 It's really intensive。 So in that case。

 we don't even need to care about normal forms we can denormalize。

 We can have single big table instead of smaller one。

 we can have tables in tables And the reason is we have a joins because again。

 if everything isn't the same table， then I don't need to join anymore。

 it's already joined it's already joined into a single table who sees who has the intuition of that。



![](img/2c75a3909261bc406bb31ac6f1006ef5_23.png)

![](img/2c75a3909261bc406bb31ac6f1006ef5_24.png)

Okay， so normal forms go to the trash can， and we are going to have a lot of single data sets like this。

 Vily， it looks like this。 This is a beautiful relational database， all flats。😊。

Divided on in multiple table。 So this is a high normal form， right。

 you have a table for products table for sales table because customers high normal form。

 If we deormalize， it means we do that。 we just merge it back into a single table。😊。

Because we just want to analyze the data。What you do is actually join。

 you get that by joining these two into a single table。

 but what's new in big data is that this is what we're actually going to store on S3 or IDGFS。

 we will install that and not that that we throw away， we only store that。😊，So this is a table。

 it turns out to be flat， but as you will see， it will not always be flat。😮。

A table you can see as a collection of rows， right， if you have a collection of people。

 one person on on every rose。 So a table is a collection of rows。

 an anate terminology is collection of Tuppers， right， every every record on in my table is a Tupper。

😊，Now， if I take one to one row， I marked it is in green in here， phone 800 John1。😡。

What is that mathematically， Well， mathematically， it's a function， partial function。

 a mapping that maps product to phone price to 800 customer to join in quantity1， right。

 It's just the header。 the product is a phone。 The price is 00 and so on。 So mathematically。

 you could represent it with this symbol That is for the functions， right。

 This is a product is mapped to phone。 Price is map to 800。😊。



![](img/2c75a3909261bc406bb31ac6f1006ef5_26.png)

![](img/2c75a3909261bc406bb31ac6f1006ef5_27.png)

As I use， it's my convention for the set of strings。

 So this is all the possible attributes that you can have here for columns。

 And these is a set of values。 That's also my convention。 It's not universal。 So we map。😊。

The headers right here in purple， two values right here in green。 And， of course。

 if I change the the row and I consider the other rules， that will be the same。 But here。

 the values will be difference with with me。

![](img/2c75a3909261bc406bb31ac6f1006ef5_29.png)

![](img/2c75a3909261bc406bb31ac6f1006ef5_30.png)

So every row in here is a tuel that looks like this。

 so that's how the mathematicians would represent this。😊，But we are computer scientists。

 and we prefer to look at it this way。 Do you see it's the same thing。

 It' exactly the same thing It's just written in a different form。 In fact， it's even text。😊。

It's a text form。And now you see that I have the quotes around them， but the product is full。

 The price is 800。 The customer isjo the quantity as well。😊，This text is called， you know， right。

 It's called。Jason， I heard it。 So this is indeed the Jason syntax。

 right we might have seen it before。 So the J syntax is just a textual representation for toppers right so instead of looking at it with the mathematical or scary notations like this。

 we just represent it as a text document that looks like this。 That's Jason。Now， just so you know。



![](img/2c75a3909261bc406bb31ac6f1006ef5_32.png)

If you look at that text， you will see that I did a lot of nice things in there。 For example。

 I put one on every line， and then I have a small indentation in there to make it look nice。

 Why did I do it just because I'm a human being， your're human beings。

 and it's easier for human beings to have it nicely formatted like that。

 It's like when you write write a formal letter。 and you just make sure that the paragraphs are aligned and so on。

 But this is really just for us as human， It's just to make it beautiful In practice。

 you don't have to I could also have it all on the same line like this without new lines。

 without indent， and that's just fine。 It's the same thing。😊。



![](img/2c75a3909261bc406bb31ac6f1006ef5_34.png)

![](img/2c75a3909261bc406bb31ac6f1006ef5_35.png)

![](img/2c75a3909261bc406bb31ac6f1006ef5_36.png)

And in fact， typically， if you want to create one search that's called an object， right。

 one for that record， one other for that record， one other for that record。 So six of them。



![](img/2c75a3909261bc406bb31ac6f1006ef5_38.png)

![](img/2c75a3909261bc406bb31ac6f1006ef5_39.png)

You can basically just line them up like this。 So here I put the source 5。 I don't know why I could。

 I might as well have put the 6，1， but for some reason， I put three do。 But anyway。

 you see every one of these objects corresponds to a different row in there。

 Who see that it's the same data。

![](img/2c75a3909261bc406bb31ac6f1006ef5_41.png)

![](img/2c75a3909261bc406bb31ac6f1006ef5_42.png)

![](img/2c75a3909261bc406bb31ac6f1006ef5_43.png)

Okay， but in one case I have a table， I could also have stored it as CSV。

 but instead of storing it as CSV， I store it as J CSV， but just like CSV， it's in fact text。😊。



![](img/2c75a3909261bc406bb31ac6f1006ef5_45.png)

嗯。Okay。No。Even though it's not in the high normal form， this table still fulfills my three criteria。

 domain integrity， relational integrity and atomic integrity， atomic integrity。

 because there is no table in the table， it's all flat Do integrity。

 because if you look at the columns， they all look nice。😊。

In the first columns you have strings in the second columns you have numbers and so on and so on right so this is domain integrity and relational integrity because it's a table right it doesn't have missing cells or extra cells。

 So you see that in that case I check all the boxes I am in the beautiful and marvelous world of SQL which we studied in information systems for engineers but as I told you we are going to now venture out of that territory and stop dropping all of these and that's called no SQL for not only SQL。

😊。

![](img/2c75a3909261bc406bb31ac6f1006ef5_47.png)

![](img/2c75a3909261bc406bb31ac6f1006ef5_48.png)

![](img/2c75a3909261bc406bb31ac6f1006ef5_49.png)

And what's going to happen is that we are going to now break the rules and throw away the normal forms。

 So， you know， the first normal form says it has to be flat。

 I cannot have a table in the table in the table。 Let's throw that away and allow for tables to be in tables。

 That's going to be fine with us now。

![](img/2c75a3909261bc406bb31ac6f1006ef5_51.png)

RightSo this goes there。 So now this is what I get。 If I put tables in tables。

 I might get something like that。😊。

![](img/2c75a3909261bc406bb31ac6f1006ef5_53.png)

Right， so if you do that， did that in a bachelor's lecture of databases。

 people would scream at you like， no， no， no， no， no， you can't do that。

 This is not in the first normal form。 Here we can， right， It's big data。

 So we are allowed to do that。 So I can put a table in a table in a table。 This is called nestedness。

So that's the first thing that we can do。In big data now。How do I represent this in Jason， Well。

 what I can tell you is that in CSV you got in CSV， it will not work that in Jason you can。



![](img/2c75a3909261bc406bb31ac6f1006ef5_55.png)

And in fact， the way you do it， let's take this is how many records are there， There is one record。

 a second record and a third record right and you have tables instead inside， but it's still one，2。

 three records。 Let's take the first record， just the first one。😊。



![](img/2c75a3909261bc406bb31ac6f1006ef5_57.png)

![](img/2c75a3909261bc406bb31ac6f1006ef5_58.png)

What does it look like in Jason， Well， you probably guess right， this is the EPA product phone。

Price 800。 or there， What do we do， It's a nest table。 No problem。 In Jason。

 we have this angle brackets here that says it's a list。 So called an array， a list。



![](img/2c75a3909261bc406bb31ac6f1006ef5_60.png)

![](img/2c75a3909261bc406bb31ac6f1006ef5_61.png)

And inside， if I map this to Jason that we know how to do customer John quantity one here it is customer Peter quantity2 here it is customer Mary quantity one here it is。

 we put commands to nicely separate them and put them inside inside so you see that in Jason I can have a table。

😊。

![](img/2c75a3909261bc406bb31ac6f1006ef5_63.png)

![](img/2c75a3909261bc406bb31ac6f1006ef5_64.png)

Inner table。Who sees that。

![](img/2c75a3909261bc406bb31ac6f1006ef5_66.png)

If it's magic， I can do it in CSV， but in Jason， I can do that。😊，Now。

 here are some other rules we can break relational integrity， how do we break it。

 maybe by removing cells， right？And here I removed one。 Did you see the one I removed。

I removed that cell right there， it went away。We don't have relational integrity in there。

 That's no longer a table。 It's something thing that。Looks like a table。

 but it's missing a set in there， right， And that's fine In big data， It's fine。

 This is called heterogeneity。 How do you see it in Jason， when it's simple in that case。

 you have custom Mary。 And for quantity， you just have no， you just don't have anything。😊，In CSV。

 you could not do it Well you could kind of leave it empty between two commands， but it's less nice。

 right， So you see that。With Jason， I can account for nested nest。 I can have a table in a table。

 and I can also allow for hydrogengeneity if I have a missing value， then I just leave it out。😊。



![](img/2c75a3909261bc406bb31ac6f1006ef5_68.png)

In this syntax。诶。😊，So what we call data deormalization is pretty much that it's breaking rules and throwing away the normal forms。

 So it means that we go from these。

![](img/2c75a3909261bc406bb31ac6f1006ef5_70.png)

1970s way of doing relational databases。 It's flat。 It's homogeneous， relational integrity。

 domain integrity。呃 atomic integrity。

![](img/2c75a3909261bc406bb31ac6f1006ef5_72.png)

And if we throw these rules， then a lot of things can happen， we can have tables in tables in tables。

 we can have extra values that come out of nowhere， we can have missing values。

 we could have invalid values， maybe we have integers everywhere in a string in here and not honesty table in there it's nested and heterogeneous right SQL。

 no SQL who's with me。😊。

![](img/2c75a3909261bc406bb31ac6f1006ef5_74.png)

Okay。Goods。😡，So。

![](img/2c75a3909261bc406bb31ac6f1006ef5_76.png)

Now this is an example of a table， I can have some nerves in there。

 but it's still kind of considered the table。😊。

![](img/2c75a3909261bc406bb31ac6f1006ef5_78.png)

嗯。And now I have this other collection that breaks the rules。 I have tables in a table。

 I have missing values and so on here and here it's missing。 And if you look at here and here。

This is the J representation of this。And this is the Jason representation of this， Who agrees。

Right it's intuitive。 It's exactly the same idea as before。 When you want to nest the table。

 you need these， it's called angle brackets。 These are called curly brackets。

 and these are called sorry， not angle。 what am I saying square brackets。

 the square brackets and the curly brackets。😊，All right。

 so you see that we are moving away from tables as homogeneous collections of flat items。

 flat records， and we move away to heterogeneous collections of arborerescent items aorerescent if you don't speak a Latin language it means like a tree like a ministry okay。

 and this is called semistructured data on the left you have relational data on the right you have semistructured data。

😊。

![](img/2c75a3909261bc406bb31ac6f1006ef5_80.png)

And this is a whole spectrum you basically have on the left the fully structured data that fits in tables that strictly respect the normal forms。

On the right， you have data with no structure at all。 And here you。

 you really can imagine chat GT analyzing text from Wikipedia， right， So that's totally unstructured。

 And somewhere in the middle， you have this semistructure data。

It's kind of unstructure because it's just text。But if you look closer， it's not text like English。

 it actually does have some structure， this is why it's called semi structures。😊，Okay。No。

A second aspect of the syntax that we are looking at today is that it is standardized。

It is standardized by W3C for XML， that's the same standardization body that also standardizes HTP。

 H and so on and Ecma standardizes Jason right and it's the same that also standardized JavaScripts Ecma。

Okay。Soue。Now let's start diving into it， right what I give you until now was the motivation。

 like why do we have syntax and why do we need something S than CSV。

 it's in order to account for data that is denormalized。So what is syntax？

Well when you have a syntax like Xml alterization， you're basically asking a yes， no question。😊。

So I'm giving to you some text documents， you can download it from somewhere。 and the yes。

 no question I can ask you is， is that text Jason？More precisely， I will ask。

 is that text welld Jason？And then there are two answers， it's either yes or no。

I can ask the same question with X。Is the text that I give you well formeded XML。

 The answer is either yes or no。 And I want to give you today the intuition of that that with your eyes。

 you can see if it's well formeded or not。 Of course， in practice， it's fully automated。

 You can just fit it into some program that we answer。😊。

This is what computer scientists call a language， a language is just a set of text documents or a set of strings that is considered valid for the language。

 but I'm not going to be using the word valid， I'm using the word wellform。

 you will understand why in a few weeks。So， yes， no。

Now I'm throwing at you an example of XM documents who already saw when before。😊。

You actually so when in the previous hour at the very end of HDGFS。

 I show you configuration files of HGFS that were actually also exc。😊。

So this is one of the two syntaxes。 and the other one is Jason。

 Now this should be more familiar to you because I showed you the example on the deommalized data who was already familiar with Jason before。

😊，Okay， several of you， but I'm going to now go into the details and TgDs to you right， Okay。

 Xml Jason， Xml， Jason。

![](img/2c75a3909261bc406bb31ac6f1006ef5_82.png)

So I start with the easy one， I mean， Jason has the reputation of being easier than XMl。😊，In general。

 you really need to try to not have any bias towards the one or the other because really there are two different syntaxes。

 they all have strengths and weaknesses in practice it's good to know both because both are used。

In practice， so let's start with Jason again because this one is easier to learn。



![](img/2c75a3909261bc406bb31ac6f1006ef5_84.png)

So what do we have in Jason， the way I'm going to show you the language is is that it's like a Lego game I'm going to give you the building blocks like in the Lego game。

 you might have the red brick of one by four and so on and so on right so I'm going to give you the building blocks。

So Jason。There are six building blocks， six， exactly six， this is the first one。

So the first building block。Is a string。A string I assume all of you most of you are familiar with that it's just a sequence of characters。

 a sequence of symbols and computer scientists put double quotes on both sides to daily meets them so the first string is who with FO0 and then you see what happens with the second string it looks a bit weird disease because there are these backslash here and whenever you have a backslash followed by an end that actually is a new line it's just an escaping sequence for a new line and here this is an escaping symbol。

😊。

![](img/2c75a3909261bc406bb31ac6f1006ef5_86.png)

![](img/2c75a3909261bc406bb31ac6f1006ef5_87.png)

![](img/2c75a3909261bc406bb31ac6f1006ef5_88.png)

Back slash you for a special character。 Guss what you put in there。 It's the uncode number。

 I told you about uncode， right， this huge catalog of letters and symbols and emojis。

 You can even put emojis in in Jason。 You just need to know in Ba 16 the the the number of the character you want to put。

 So this is extremely powerful because you can put any symbol， any emoji。

 Any character can be Arabic Japanese， the and so on and so on。 Any symbol you want。😊，In them。

 with a unique character。So this is the street， that's the first building block。Double quotes。

On both sides， the second billion blocks is numbers。It's a bunch of digits。

Possibly followed by a decimal period， possibly followed by more digits and then possibly followed by E which is times to 10 to the power of right the scientific notation and then plus or minus and then again digits right so e plus5 really means times 10 to the power of5 it's a scientific notation。

And this is it so in Jason you can have numbers like this what's really nice is that there is absolutely no limitation if you want to put1 thousand digits you can you can go ahead and go ahead and technically it' it's also well from Jason。

😊，So you can have integers， you can have any decimal number， right。

 any decimal number can be expressed。In this way。Okay， so this is called numbers。

 That's the second building block。 Then we have Boyards。 that is easy。

 There's only two There's through and then force。 That's basically the the lotion of logic， right。

 a statement can be true or it can be false。We also call them flags in some configuration files。

 true and， there is no quotes around true enforce， just true just force without quotes。

And there is a fuck。When that's null。 It's a bit like the SQL null。乐乐。

Can appear explicitly in adjacent documents。 And it just means that you don't know the value or you don't want to tell the value or for various reasons。

 right， It's just an nu。 You can also think it's kind of the same thing as anerd in Java in C plus plus。

 So you'll probably be familiar。So we already have four building blocks。

 these four building blocks have in common that they're atomic。Right。

They are just what you could have them technically in the cell of the table these four。

In addition to these four， there are two additional building blocks but these are not atic。

 these are called structures。The first one。意思。It's on the strike， a bit lower today。

And need to click again， there you go。So the first one is neoray。It's just a list of values。

How do you recognize an array because of the square brackets you see the on the top and the bottom。

 it's just the square brackets。

![](img/2c75a3909261bc406bb31ac6f1006ef5_90.png)

It is an opening sb bracket。 This is a closing s brackett。

 and then you could put any values you want here。 there's a number。 There's a bulletan。

 there's a string。 there's a nu。 there's an object。 It's on the next slide， coma separated。😊。



![](img/2c75a3909261bc406bb31ac6f1006ef5_92.png)

This is an array。 The order is important in India。 There is an order in the array。

 in all the ob list。And finally the objects。The objects。

 you can really consider them just like the tupperers in a table， right。

 Every row in a table associates an attribute with a value。 That's exactly what objects do。

 So fo bar STR would be the attributes。 And then on the right， you have the values。

 So you see F is the number。 Bar is a Boolean。 SR is a string object in an object。😊，N Q is none。

 And you see the difference with a race。

![](img/2c75a3909261bc406bb31ac6f1006ef5_94.png)

Because you have cur braces。It's called a curly brace。



![](img/2c75a3909261bc406bb31ac6f1006ef5_96.png)

Opening and closing。 And you also need the coas to separate them。

 And here you see the columns that separate。

![](img/2c75a3909261bc406bb31ac6f1006ef5_98.png)

What is called here or key and what is called a value right remember how I told you you can say block chunks plea part sh and so on is the same thing here there are people who call these keys some other people call them fields some other people call them properties you know just be aware that there's many ways you can call them typically and Jason it's called their key and a value。



![](img/2c75a3909261bc406bb31ac6f1006ef5_100.png)

![](img/2c75a3909261bc406bb31ac6f1006ef5_101.png)

![](img/2c75a3909261bc406bb31ac6f1006ef5_102.png)

![](img/2c75a3909261bc406bb31ac6f1006ef5_103.png)

对。So thats six strings， numbers， bulloleans learn erase objects。And that's it。 Thats sort of Jason。

So now just a few more considerations in order to say if yes or no， a document is Jason。

 there are a couple of things you cannot do， for example。The key must be a string in an object。



![](img/2c75a3909261bc406bb31ac6f1006ef5_105.png)

So what you see here is an object， but the key is not a streaming quotes。 That's not okay。

 That is not correct。 Jason， that's wrong。 Can do that Here， you're missing the quotes。

 That's also wrong。 This is fine。

![](img/2c75a3909261bc406bb31ac6f1006ef5_107.png)

Next。😊，This year。Let me put it that way for the purpose of the cross， it's not okay。

 You cannot have twice the same key。 Why when imagine a table with two columns the same right。

 If you have a relational table， every color name must be different。

 So if you have twice the same key， the same object that's not okay right you're kind of you have a collision between the two。



![](img/2c75a3909261bc406bb31ac6f1006ef5_109.png)

![](img/2c75a3909261bc406bb31ac6f1006ef5_110.png)

This is fine because the keys are different in the same objects。



![](img/2c75a3909261bc406bb31ac6f1006ef5_112.png)

Now， those who know Jason and the purist might say yes， yes， yes。 But actually。

 if you look at the the， the spec technically， the RF， the original one。

It doesn't say that it's forbidden。 It just says you should not be doing it。

 There is something that computer scientists like to do is that whenever you should not do something。

 then you treat it as you must not do something。 It's called also treating a warninging as an error。

 It's just safer， right， You know that everybody will be able to read it So technically。

Jason would not strictly forbid repeating a key。But if you do that。

 you should expect that maybe 90% or more of the software that can consume Jason will refuse it。

 That's basically what happens。 So for the purpose of the course。

 because it's used for data sets and it's mapped to relational table。

We treat this warning as an error， and we are not allowed to repeat the same name of the key in the same object。

 we cannot have to raise the same key。Alright。😊，Okay now I told you that we can use Jason to to store data I gave you the example with the table。

 this is a real life example that's called the Great language game it was played I think now it's quite quite old maybe 10 years ago whoever heard of that。

😊，It was a website。That you could connect to， you did not even need an account。

 you just connected to it。And it would just play audio， somebody speaking and then it would tell you。

 okay， that's person speaking， did they speak Chinese， German。

 Italian or English and you have to pick an answer and then it's right or it's wrong and then you accumulate a score。

And basically， when they did that， so they put it online and half people played it was actually quite fun。

 We even played it at the at the Pu menza。 I remember with our laptops a few years ago。😊。

And they recorded what people were doing。 So they basically every time somebody played the game。

 they created a Jason object that basically says that the audio played was Italian and that's the code of the sample。

 just like a block I a block I in a GFS， the choice given to the player were Chinese German Italian English and the player guessed German they were wrong right it was Italian So they guess German and the answer was wrong。

 that game was played in 2018 on November 7 by somebody in Switzerland。😊，And we have a data set。

 We actually have it for the lecture。 You can download it。

 I think it has 16 million objects like that，16 million。 it's a few gigabytes。😊。

And we love to use it for the purpose of the course。 It's relatively simple。 You can understand it。

 It's just 16 million times something that looks like that。

 And you can query it and aggregate statistics on it， right。

 So that's called the great language game。😊，This is the example I showed you earlier that any table technique can be converted like this and what is typically done is that every record of the table gives you an object and we like to put one object power our line。

 this is called JON lines this format where every line of your text file contains one JON object。😊。

Now again， I'm repeating here I've already showed that to you。

 so if you have a table in a table all you need to do。

 now I can use the words of the terminologylogy because now that I have explained Jason I can say it。

 this is an array that contains three objects。

![](img/2c75a3909261bc406bb31ac6f1006ef5_114.png)

![](img/2c75a3909261bc406bb31ac6f1006ef5_115.png)

RightAnd an array of objects is typically what you use to have a table in the table， right。

 the nest table is basically an array of objects。Okay， who's with me？



![](img/2c75a3909261bc406bb31ac6f1006ef5_117.png)

Okay。So this is Jason。It's relatively simple。And I'm going to move on to the other one， XmL。😊。

It's a bit complicated， more complicated， and in fact that's the reason why I'm not going to show you the whole of XM just as subset said yes。



![](img/2c75a3909261bc406bb31ac6f1006ef5_119.png)

Yes， absolutely。 Yeah， you can have you just have a square bracket with nothing inside。

 you open and close and that's fine。 That's an empty array。 That's absolutely a load。

 and then you have an empty table。😊。

![](img/2c75a3909261bc406bb31ac6f1006ef5_121.png)

嗯。😊，ok。So， excellent。X， M L is extremely complex。 If you， I put a link to the specification of X M L。

 but I think I stamp it as insanely optional because I don't want to scare you。 I mean。

 you can try to open it。 but at your odd risks。I'm only going to give you a subset of that's the one that is actually useful for our data and that it will allow you to understand。



![](img/2c75a3909261bc406bb31ac6f1006ef5_123.png)

Daタ。Okay， the first thing I want to say because。You might have thought， okay， XM is old。

 the X is complex， Who cares about XML， The research of XML has been done。

 It's now in the now it's the past。 This is just not true。It might be done in academia， in academia。

 you will not find many people still working on XL。😊。

But if you go to companies or if you go to governments， XML is all over the place。

 a lot of governments stand out use XML， an example of that and that's one of many examples is that the banks can issue tax statement to file with the tax authority and a couple of years ago they introduced the notion of an electronic tax statement right an a to houseook。

😊，It's a backwardcodes。 You basically have a Pf at the end， there's backwards。 and at the end。

The backward， in fact， contains guess what X M L。 It has X M L inside。

 and that is a sample of that's taken from an official government website in Switzerland that shows an example of using X ML for for reporting data。

 As you can see， they have a very good sense of humor。

 if you actually look at what's written in there。😊，All right， or you can do golines。So。

What does XmL look like when just like Jason I'm going to give you building blocks right。

 Jason has building blocks and so does XmL。The first building block is called an element。An element。

Is basically a zone demeter。 You basically have a start and just like when you arrive in a city。

 you get a shield that tells you this is the start of the city。 And when you leave it。

 you have another shield that tells you this is the end of the city。

 So it is called an opening tag and a closing tag。 And here you don't you don't have square brackets or cur brackets。

 you have angle brackets。 the third kind of brackets angle brackets。

 that's called an opening tag and the closing tag is the same but you have this extra slash right Now。

 just like the array could be empty， as you mentioned， that could be empty。 That's fine。

 you just put whatever inside could be empty。 But if it's empty computer scientists are so lazy。

 we love to actually save space。 So if this is actually empty。

 we don't want to have the opening and the closing tag。

 we like to be lazy and to just use that empty tag with the slash at the end。

 It's just really a shortcut。 that would have been fine too， right But since we are lazy。

 We love to actually shorten it to this。😊。

![](img/2c75a3909261bc406bb31ac6f1006ef5_125.png)

![](img/2c75a3909261bc406bb31ac6f1006ef5_126.png)

![](img/2c75a3909261bc406bb31ac6f1006ef5_127.png)

![](img/2c75a3909261bc406bb31ac6f1006ef5_128.png)

![](img/2c75a3909261bc406bb31ac6f1006ef5_129.png)

![](img/2c75a3909261bc406bb31ac6f1006ef5_130.png)

![](img/2c75a3909261bc406bb31ac6f1006ef5_131.png)

Okay， so this is an element next week I will give you the other building blocks attributes。

 text mainly and I'll show you more examined。😊。

![](img/2c75a3909261bc406bb31ac6f1006ef5_133.png)

So this is it for this week thank you very much for your attention I hope you enjoyed learning all of this you will have the exercises this week on HFS also the the the quizzes released for the exercises on the queries by the way you can check again if you didn't pass maybe now you pass because we allowed a few more answers for example if you just Omit Adida space or you have quotes and so on we also count see details as correct so you can you can check again。

😊。

![](img/2c75a3909261bc406bb31ac6f1006ef5_135.png)

Thank you very much， enjoy the rest of your day， thank you Shag for the meration and I see you next week at 8 a。

 thank you very much。😊。

![](img/2c75a3909261bc406bb31ac6f1006ef5_137.png)
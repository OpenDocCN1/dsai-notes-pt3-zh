# 吴恩达《数据工程（数据建模、转换和服务）第4课，完结｜DeepLearning.AI Data Engineering》 - P41：40_与Ben Rogojan的对话.zh_en - GPT中英字幕课程资源 - BV13mtpe7ESt

I'm here today with Ben Rugehan also known as Seattle Data Gu So it's good to see Ben are you doing Hey good see you again Joe I'm doing great doing great really excited to talk to about data engineering but for the learners who don't know who you are do you want to give a quick intro Yeah so since we' talking about data engineering I've been working I think about almost a deck at this point in the data world originally I think like most people who came around in the 20122015 kind of era I was like data science is what I'm going do I like switched a lot of my courses even in college to being like a lot more bioinformatics or statistics space just for that reason then I came out。

 started doing some data science work and I think I just eventually realized I like more of like the software the programming side of things and I accidentally found data engineering honestly when I was looking for a new job。

 I was just typing in the skills that I had know SQL Python automation like data warehouse。

Sa different things and got my first like official role as a data engineer。

I'm in a healthcare analytics startup。 And then from there just kind of kept growing my skill set。

 I eventually got a job at Facebook after a few years at the startup and then worked there for a few more years before at this point now。

 I just do kind of consulting in the data engineering， data infrastructure space。

 and you make awesome content about data engineering。 Yes， yes， I try。 I try。

 it's always it's always challenging Keep up with all the stuff that changes that you're always likes so hard isn't it Yeah。

 I have a intro to databricks like video that's done really well。

 And now I'm like I need to redo it all at this point。 like so much has change So yeah。😊。

That's the nature of it though， you data engineering。

 I would say the one constant is change actually morically， yeah。Yeah。

 walk me through your journey you know， so you started out as a data scientist got the data engineering what were your early days as a data engineer like like at the company that I work for we did like again。

 healthcare kind of data analytics we。We're basically just taking like 40 or 50 different insurance provider data sets that we would get access to from various reasons sometimes because the company we were kind of owned by they had they were just a giant insurance company and then also they were trying to broaden their services and offer to like Amazon and Boeing and be like hey。

 we'll do like healthcare analytics for your company because most companies are like half or some level self-insured so if something goes wrong they actually end up paying a lot of it not just the insurance company because it used to be too expensive otherwise and so like if they can like increase the health of their population。

 the view is that you know you reduce the risk and the burden there。

 but yeah we would just take all that data standardize it because the nice thing here is like claims data which is what we were working on is like healthcare claims data is decently standardized minus is the fact that all the data you get comes in different formats but like the data that has inside should be about the same so that's when I learned about like。

All the various ways data can be separated like position delim fields or position space fields are always weird I'm sure you've come across occasion where it's like yeah field zero or row or yeah column zero to whatever 50 is this field and you have to have a schema file just to keep track of all that。

 but yeah really just building a system around that and then also building products on top of that while I was there we built like a product on fraud detection。

 we built something around opioids and in tracking kind of that。

 and who was maybe providing too much in terms of opioids and trying to help that and give that to different things。

 So that's really where it kind of started and we worked honestly just on Powerhell and SQL server and like things that most people will be like that's not sexy at all。

 but that's honestly where it started then you moved over to Facebook which I'm guessing it is a bit different than Powerhell and SQL server I mean it is but like in the same time the problems like are different one Facebook's data infrastructures is very mature So a lot of people sometimes find it boring。

😊，Because you know if you're wanting to work on like quote unquote， a big data problem。

 there are some teams that will work on those big data problems and do have big big big data issues but it's not everyone and it's probably a very small percentage So a lot of your infrastructure is well set out I remember like just pushing code I was like oh I'm just like building a Python script that really wraps around SQL and then I'm just pushing it somewhere and it's really more about like how I communicate and how I find like problems that are worth solving more than like my coding ability some people again I think I don't know if Fer said found it boring because it was like well all all the hard stuff is kind of solved you know。

嗯。That's an interesting comment about communication and finding problems that solve so a big part of this course。

Is identifying。Things that maybe the business is going to find valuable for you to work on。

 right and。Right。I think the temptation for our data engineers is to figure out very complex systems to build and so forth。

 but oftentimes it's at odds with solving legitimate problems。

 walk me through that framework though because I don't think this is something that's often taught how did you figure out that you needed to not just be maybe awesome at coding but also great at communicating and finding problems to solve Yeah。

 I mean in terms of how or why I think one of the things that Facebook forces you to do is like hey there's like a000 other data engineers and if I just do what someone else tells me to do it's very hard for me to differentiate I don't have I don't take some risk or do something that's like you know I think this is worth doing everyone else will just define what I should be doing and I might not do something that I actually impacts the business and so usually what we do is spend a good part of maybe the first few well maybe before the first few months of a half is kind of how we broke down the year so the first part of like maybe in December。

or November we'd like talk to all the teams that we communicate with and work with and be like hey what what problems are you solve or trying to deal with and not just data like what are your daily problems of what's going on we talk about what problems we solved the last like last few months and be like okay what where can we find some correlation of like big problems one of the ways my manager put it？

Was like you know you don't get promoted for solving a thousand00 tasks you get promoted for figuring out how to get rid of a thousand00 tasks right there's a big thing that keeps repeating over and over again that should be a signal that's like hey why is this repeating and how do we you know get rid of this problem and I think that's something that。

Is why Facebook kind of has a very mature infrastructure even in itself like when you think about like they built Presto and hive。

 it's like， well yeah， because they looked at Mapreuce and like。

 well this is terrible right Like if we have to have really expensive engineers。

 it's really slow to put out code， we can't get things out quickly you know， it's not great。

 So if we can put some layers on top of that that automatically makes everyone's life better。

 So yeah， I think that's kind of the mentality。 I often try to。😊。

Have when approaching problems like how do I get rid of these this big the bigger problem。

 not just the little daily problems that you're trying to you know deal with on an everyday basis Yeah。

 that process of elimination of problems is something that yeah hopefully learnerss take away about that' that's solid advice what do you recommend to people who are interested in getting into data engineering what do you have the the Ben Rugu and path to success in data engineering or advice there？

Yeah， I mean， I think you know， your it's funny actually someone asked me this question recently at one of the chats at Snowflake。

 and I was like， oh yeah， you can probably read Joe Reese's book just to get started right to understand hey what exists。

 where can I you start And one of the people on the panel was like no。

 don't do that learn more about the business first。

 And I understood the notion I'm like one of the important parts isn't just the technology side But I think that's where it's all gonna start regardless like you do need to start on the technology side to understand you're gonna need to know SQL Python data warehousing kind of data pipelines and how those exist and how to build them And then kind of everything else will kind come from that do you need to learn snowflake Data breaks BigQu probably at some point you will maybe。

But I'd worried less on that and more about that foundation of like how does this all work Why am I even building a data pipeline Like I think that was the question I didn't ask enough early on was like yeah why are we building data pipelines。

 why am I literally taking data from one place to another just the reason of analytics I was asking Ethan recently because he posted about you posted on someone's a reference to like Airbyite and I was like how much do you think the industry spends just on essentially E like just ingesting like how much cost and time do you think we've spent and he's like he put out like5 billion years which is probably not inaccurate just for ingestion but yeah like even this basic stuff and having that foundation and asking why and why are we doing all this stuff and spending so much money I think is a great place to start So build your solid skills and start asking why you need them and what they actually do for the business。

Yeah， such good advice。Yeah， I often find that。Data pipelines people want to build them for their own reason you know because again you have the word engineer in your title you want to engineer things sometimes oftentimes they either bridges to nowhere or pipelines nowhere so's it's solid advice yeah and I think the comment on the panel is interesting like I think the book is good but the person who made the comment go learn about the business I think they're absolutely correct too you know that's。

That kind of but it's hard too， I mean， how do you recommend that an engineering or technically focused person？

Learn about how to even look at an organization or a business that's definitely a harder question probably to answer because like the easiest way is gonna be to work at a company right to like actually go in and and start when you're early on your career。

 it's almost hard to say like you should because like early on your career。

You want to start asking questions， but you like also want to focus on getting better right like as an engineer more than anything else like you just like hey。

 get good at building pipelines， but start asking you know inquisitive questions about the business how do we make money you know like what is this pipeline for start poking in that direction and then the higher you kind of go up I think the more you know as you're confident in your technical skills you can start shifting over and be like yeah。

 really really start digging to the business， really start talking to other people。

That aren't technical because if you only talk to technical people like we just kind of live in our own bubble sometimes and we're like。

 oh yeah， here's a cool new tool it solves this problem。

 But none of those problems generally have to do with the business it's all like oht know we ingest code or we ingest data faster we can process more data we can do all of this stuff but really at some point you need shift over and be like but why that all comes down to like hey。

 what are we giving the business what do they get because they get data in real time is there a real benefit or we just doing it because it sounds cool someone asked real time it's a forever it's a forever kind of thing that we I think we are all like yes。

 it's the thing we're trying to do and then you get there and you're like but why。

What does real time mean to you， oh gosh？That's the other question I mean that's the question I always love to ask this question yeah it's like what does that actually mean I've had like calls with prospects where like it'll end up being like oh we really meant like 24 like every you know 12 to 24 hours which I was like well that's very different but okay I get it you know。

 the longest one I ever heard was every month I'm not even making this up。😊，Yeah。

 yeah so just like what whatever however you wanted to define that。

 I guess it is what it is yeah I think in part of the course。

 we talk about the notion of a real time being this this sort of。it's。

It's a very shifting definition So you always need to ask like what do you mean by this I think this goes back to your point you're making too of asking good questions of people and asking why like why do we need to do this what's this pipeline for when you say real time like what exactly do you mean by this these are I part of being a good data engineer and's a good practitioner in general is asking good questions yeah that's awesome is there anything you're excited about over the next year or two there's been a lot of shifts I guess in the world recently obviously tabular just got bought out which was I mean it's interesting。

I。I hope we continue to maybe try to shift towards you know。

 building reliable and usable data sets over the long term。

 I think that's my my hope because I don't know even in a world where。

All data exists and maybe one homogenous data source somewhere。 You know。

 you're still gonna have that problem。 I don't even know if companies will do that。

 I think it's the one thing I've thought about with the with tabular data breaks。 Some like。

 this works really well。 like the multis stack or multieng kind of data infrastructure in theory。

 but most companies's like， you know， your Asia like entity has Big worry。

 Your American entity has snowflake。 your marketing team is using redshift。 And it's like。

 it's so everywhere that it's like。There's very few companies。

 I feel like will properly maybe implement that。 But that's a different thing。 I guess。 So yeah。

 I don't， I don't know。 I， I think for me， my， my hope know excitement。

 my hope is will just continue to review the fundamentals and you know， implement them well。

 especially as we're trying to do everything AI like， well， we want to make that better。

 We really need to， to take on some of some of these like fundamentals of data management and data quality。

 So I agree。 Yeah， I think a lot of these topics are getting a second look now precisely because of that。

 I think there's a camp that says you can just throw AI onto everything。 But as you know， a lot of。😊。

Corporate data sets are less than ideal。是。It's a big big issue well thanks Ben thanks for you know I think educating the learners on lot of。

😊，Great ideas in data engineering for people who want to find out more about you。

 how can they do that？Yeah， you can find me on YouTube or substack under the Seattle Data Gu so those are pretty pretty much everywhere。

 I think I try to be a Seattle Data guy so you'll find me in some other places like LinkedIn and so on。

Ceattle Data guy， even though you moved from a while ago， send her data dude yeah。Awesome。

 well thanks， Ben。 So always good to chat with care。 Yeah， you Sw show。 All right， thank you awesome。

😊。
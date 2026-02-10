# 谷歌数据分析师第四课《从脏数据到干净数据的处理》process-data（中英字幕）deepseek翻译 - P14：14_02_02_清洗多源数据.zh_en - GPT中英字幕课程资源 - BV19m4y1J7dG

![](img/c52e36701432f4a5ee9806e07532b430_0.png)

Welcome back。So far， you learned a lot about dirty data and how to clean up the most common errors in a data set。

Now we're going to take that a step further and talk about cleaning up multiple data sets。

Cleaning data that comes from two or more sources is very common for data analysts。

 but it does come with some interesting challenges。A good example is a merger。

 which is an agreement that unites two organizations into a single new one。In the logistics field。

 there's been lots of big changes recently， mostly because of the E-commerce boom。

 with so many people shopping online， it makes sense that the companies responsible for delivering these products to their homes are in the middle of a big shakeup。

When big things happen in an industry， it's common for two organizations to team up and become stronger through a merger。

 Let's talk about how that'll affect our logistics association。As a quick reminder。

 this spreadsheet lists association member ID numbers。First and last names。Adddresses。

How much each member pays and dues？When the membership expires and the membership types。Now。

 let's think about what would happen if the International Logistics Association decided to get together with the Global Logistics Association in order to help their members handle the incredible demands of e-commerce。

First， all the data from each organization would need to be combined using data merging。

Data me is the process of combining two or more data sets into a single data set。

This presents a unique challenge because when two totally different data sets are combined。

 the information is almost guaranteed to be inconsistent and misaligned。For example。

 the Global Logistics Association spreadsheet has a separate column for a person's suite。

 apartment or unit number。But the International Logistics Association combines that information with their street address。

This needs to be corrected to make the number of address columns consistent。Next。

 check out how the Global logisticistics Association。

Uses people's email addresses as their member ID。While the International logisticgistics Association。

Uses numbers。This is a big problem because people in a certain industry， such as logistics。

 typically join multiple professional associations。

 So there's a very good chance that these data sets include membership information on the exact same person。

 just in different ways。It's super important to remove those duplicates。 Also。

 the Global Logistics Association has many more member types than the other organization。

On top of that， it uses the term youngng professional。Instead of student associate。

But both describe members who are still in school or just starting their careers。

If you are merging these two data sets， youd need to work with your team to fix the fact that the two associations describe memberships very differently。

Okay， now you understand why the merging of organizations also requires the merging of data。

 and that can be tricky。But there's lots of other reasons why data analysts merge data sets。

For example， in one of my past jobs， I emerged a lot of data from multiple sources to get insights about our customers' purchases。

The kinds of insights I gained helped me identify customer buying patterns。When merging data sets。

 I always begin by asking myself some key questions to help me avoid redundancy and to confirm that the data sets are compatible。

In data analytics， compatibility describes how well two or more data sets are able to work together。

So the first question I would ask is， do I have all the data I need to gather customer purchase insights。

 I wanted to make sure I had data on customers， their purchases， and where they shopped。Next。

 I would ask， does the data I need exist within these data sets？

As you learned earlier in this program， this involves considering the entire data set analytically。

Looking through the data before I start using it lets me get a feel for what it's all about。

 what the schema looks like。 if it's relevant to my customer purchase insights and if it's clean data。

That brings me to the next question。Do the data sets need to be cleaned or are they ready for me to use？

And because I'm working with more than one source， I will also ask myself。

 are the data sets cleaned to the same standard？For example， what fields are regularly repeated。

How are missing values handled。How recently was the data updated。

Finding the answers to these questions and understanding if I need to fix any problems at the start of a project is a very important step in data merg。



![](img/c52e36701432f4a5ee9806e07532b430_2.png)

In both the examples we explored here， a data analyst could use either the spreadsheet tools or SQL queries to clean up。

 merge and prepare the data sets for analysis。Depending on the tool you decide to use。

 the cleanup process can be simple or very complex。Soon。

 you'll learn how to make the best choice for your situation。And as a final note。

 programming languages like R are also very useful for cleaning data。

 You'll learn more about how to use R and the other concepts we covered soon。😊。


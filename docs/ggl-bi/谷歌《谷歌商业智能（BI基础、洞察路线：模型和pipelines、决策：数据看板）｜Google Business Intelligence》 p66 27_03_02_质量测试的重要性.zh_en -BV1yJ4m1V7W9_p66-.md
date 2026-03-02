# 谷歌《谷歌商业智能（BI基础、洞察路线：模型和pipelines、决策：数据看板）｜Google Business Intelligence》 p66 27_03_02_质量测试的重要性.zh_en -BV1yJ4m1V7W9_p66-

![](img/08c9e0bc07d2a58d22ab66d61f0816f6_0.png)

You're already familiar with E T L pipelines where data is extracted from a source。

 transformed while it's being moved and then loaded into a destination table where it can be actioned on。

 Part of the transformation step in the E T L process is quality testing。In BI。

 quality testing is a process of checking data for defects in order to prevent system failures。

The goal is to ensure the pipeline continues to work properly。Quality testing can be time consuming。

 but it's extremely important for an organization's workflow。

 Quality testing involves7 validation elements， Compleness， consistency， conformity， accuracy。

 redundancy， integrity and timeliness。😊，That's a lot of elements to keep in mind。

 But we're going to break down each in this video， starting with completeness。 Also。

 you may recall some of these concepts from the Google data Analytic certificate。If you'd like。

 take a few minutes to review that content before moving ahead。All right。

 let's start with checking for completeness。This involves confirming that the data contains all desired components or measures。

For example， imagine youre working with sales data and you have an ETL pipeline that delivers monthly data to target tables。

These target tables are used to generate reports for stakeholders。

If the data being moved through the pipeline is missing a week of data or information about one of the best selling products or another key metric。

 then the calculations used to create reports won't have complete accurate data。Next。

 we have consistency。You might have learned that in a data analytics context。

 consistency deals with a degree to which data is repeatable from different points of entry or collection。

In B， it's a bit different。Here， consistency involves confirming that data is compatible and in agreement across all systems。

Imagine two systems。 One is an HR database with employee data， and the other is a payroll system。

If the HR database lists an employee who either isn't in the payroll system or is listed differently there。

 that inconsistency could create problems。Next is conformity。

This element is all about whether the data fits the required destination format。

Consider sales data in an E T L pipeline。 If the data being extracted includes dates of sale that don't match the dates that the destination table is designed to hold。

 That's going to create errors。 Now， accuracy has to do with the data conforming to the actual entity that's being measured or described。

Another way of thinking about this is if the data represents real values。So with that in mind。

 any mistyped entries or errors from the source are problematic because they will be reflected in the destination。

Sour systems requiring a lot of manual data entry are more likely to have issues with accuracy。

Like if a purchase of a hamburger was misentered as selling for a million dollars。

 that's something you need to take care of before the data is loaded。

If you're using a relational storage database， ensuring that there isn't any redundancy in the data is another important element of quality testing。

In a BI context， redundancy is moving， transforming， or storing more than the necessary data。

This occurs when the same piece of data is stored in two or more places。

Moving data through a pipeline requires processing power， time， and resources。

So it's important not to move any more data than you need。 For instance。

 if client company names are listed in multiple places but are only required to appear in one place in the destination table。

 we wouldn't want to waste resources onloading that redundant data。Now， we come to integrity。

Integrity concerns the accuracy， completeness， consistency。

 and trustworthiness of data throughout its life cycle。In quality testing。

 this often means checking for any missing relationships in the data values。 As an example。

 say a company' sales database is relational。BI professionals would depend on those relationships to manipulate data within the database and to query the data。

Maybe they have product Is and descriptions in a database。

 But if there's a description and no corresponding record with the I D。

 theres now an issue with data integrity。It's essential to make sure this is addressed before moving on to analysis。

Data mapping is one way to make sure that the data from the source matches the data in the target database。

You'll learn more about this later， but basically， data mapping is the process of matching fields from one data source to another。

Last but not least， you want to make sure your data is timely。

 Timeliness involves confirming that data is current。

This check is done specifically to make sure data has been updated with the most recent information that can provide relevant insights。

For example， if a data warehouse is supposed to contain daily data but doesn't update properly。

 then the pipeline can't ingest the latest information。

BI professionals are mostly interested in exploring current data in order to allow stakeholders to gain the freshest insights。

This definitely won't be possible if the data being moved is already outdated。 A lot goes into E。 T。

 L quality testing， and it can be a tricky process。

 But remembering these seven key elements is a wonderful first step toward creating high quality pipelines。

😊。

![](img/08c9e0bc07d2a58d22ab66d61f0816f6_2.png)

Coming up， you're going to learn even more about these checks and other performance tests for ETL processes。

Bye for now。
# 杜克大学《Excel 到 MySQL：商业分析（5课全）｜Excel to MySQL： Analytic Techniques for Business》中英 p88 13_03_01_认识您的薪资数据.zh_en -BV1mS421X7yw_p88-

![](img/28a614ed67db553ce76a250729662a06_0.png)

Yeah。I hope you're excited to start learning Tableau。 Before we jump in。

 I wanted to tell you a little bit about the data set we will be analyzing the videos of this course。

When a US company wants to hire someone from outside of the United States for a specialty or technical position。

 they have to file an application with the United States government to get a visa for the applicant so that the applicant is allowed to stay in the country。

Typically， the company will either file a green card application called a perm application or a labor condition application called an LCCA。

LC As include other specialty working visas， like H1 B visas。

One of the primary reasons these applications need to be filed is， of course。

 so that the US government can keep track of who is entering and leaving the country for work related reasons。

But another reason the applications need to be filed is that the government wants to make sure immigrants are either being taken advantage of or causing adverse effects for US workers。

Therefore， each time a company files an application。

 they have to state how much they are planning on paying the employee。

They also have to state the average amount an employee with similar skills and background typically gets paid for the same position。

 a figure called the prevailing wage。In theory， but immigration blog suggests not in reality。

Employs are not allowed to pay foreign employees a dramatically different wage from the prevailing wage for that position and education level。

 This is meant to ensure equity for US and non US workers。Interestingly for us。

 all work visa applications are publicly available and downloadable at the Office of Foreign Labor Certification website。

That means if you have the patience to put all the data together。 and luckily for us。

 people on our team were patient enough。 it would be possible to look up information about what types of salaries people in a particular profession are making。

It would also be possible to look up how these wages vary across different parts of the country。

Since many of you taking the class might be considering making a career move into a data related field。

 I thought it might be interesting to use this publicly available data to explore what types of salaries you might encounter。

So what does this foreign labor data set that we are going to use look like？Well， first of all。

 I want to tell you that an even more complete data set has been assembled and made searchable at this Jobs andtech website。

For this course， we've put together a subset of the 2011 to 2015 data available on the website and included the following fields。

 of course， offer yearly wage for each application。

Prevailing yearly wage for the job in that application。

Date when the decision on the application was made。Company submitting the application。

City in which the job is located， nationality of the job applicant and visa type being applied for。

To make life easier in us， we also included a field that did a search of the job titles and classified them into a general job subcategory。

For the most recent data from 2015， we were also able to pull number of years of experience required to apply for the position。

 education level required to apply for the position and date when the application was received。

It's worth noting that there were a lot of incorrect entries in the data set。

 Some of the applications were for part time work， while others were for full time work。

 and some of the wages were originally entered as hourly by weekly or monthly instead of yearly。

So the data were pretty messy when we pulled them off the Office of Foreign Labor Certification website。

You should also know that a lot of data was missing and therefore remains missing in the data set we will be using。

 Further， none of these numbers reflect bonuses or raises that occurred after the original application was filed。

 All of these things should be taken into consideration as we try to interpret what the data mean。

You and the data have now officially been introduced。

 Let's find out what we can uncover about US tax salaries。



![](img/28a614ed67db553ce76a250729662a06_2.png)
# IBM数据工程专业证书课程4：《关系数据库导论（RDBMS）》｜introduction-to-relational-databases｜ - P27：26_mysql 中加载数据.zh_en - GPT中英字幕课程资源 - BV1Mj4116716

![](img/7d92423dfb1733a40e2e6058a603478b_0.png)

![](img/7d92423dfb1733a40e2e6058a603478b_1.png)

Welcome to Pulating MySQL databases and Ts。

![](img/7d92423dfb1733a40e2e6058a603478b_3.png)

After watching this video you will be able to describe my SQL backup and restore functionality。

 explain how to load small and large amounts of data into my SQL。

 and describe how to export my SQL data to a CSV file。



![](img/7d92423dfb1733a40e2e6058a603478b_5.png)

As a data engineer or database administrator， you will often need to populate databases and tables one method of doing this is to back up an existing database containing your data and restore it to your new destination。



![](img/7d92423dfb1733a40e2e6058a603478b_7.png)

![](img/7d92423dfb1733a40e2e6058a603478b_8.png)

![](img/7d92423dfb1733a40e2e6058a603478b_9.png)

![](img/7d92423dfb1733a40e2e6058a603478b_10.png)

You can use my SQL dump to back up a database to adoptt SQL file containing all of the statements needed to recreate the contents of the database the simplest use of this is shown here。



![](img/7d92423dfb1733a40e2e6058a603478b_12.png)

![](img/7d92423dfb1733a40e2e6058a603478b_13.png)

The dashU parameter specifies the username of RoEmploy is the name of the database。

 and employee backup。sql is the name of the file in which to create the backup。



![](img/7d92423dfb1733a40e2e6058a603478b_15.png)

![](img/7d92423dfb1733a40e2e6058a603478b_16.png)

If you want to just back up specific tables， you can list their names after the name of the database and to restore a backup file。

 you can use my SQL in a similar fashion， This runs all the SQL statements in the backup file to recreate the objects and restore the data in the destination database Note that the greater than signs signifies output to the dotsQL file or backup and the less than sign signifies input to the database or restore。



![](img/7d92423dfb1733a40e2e6058a603478b_18.png)

![](img/7d92423dfb1733a40e2e6058a603478b_19.png)

![](img/7d92423dfb1733a40e2e6058a603478b_20.png)

If you're already at the My SQL command prompt， you can restore a dump file by using the source command with the name of the dump file。

 This method can also be used to execute SQL scripts from file。

You can also back up databases using PhHP My admin， select a database in the tree View。

 then on the exportport tab， click go。

![](img/7d92423dfb1733a40e2e6058a603478b_22.png)

By default， this quick export method generates an SQL file that contains all the script necessary to completely recreate the contents of your database you can then use the import tab to restore this database to this or another instance of my SQL。



![](img/7d92423dfb1733a40e2e6058a603478b_24.png)

![](img/7d92423dfb1733a40e2e6058a603478b_25.png)

![](img/7d92423dfb1733a40e2e6058a603478b_26.png)

Select your destination database， locate the backup file， and then click go again。

 this runs all the SQL statements in the backup file to recreate the objects and restore the data in the destination database。



![](img/7d92423dfb1733a40e2e6058a603478b_28.png)

![](img/7d92423dfb1733a40e2e6058a603478b_29.png)

![](img/7d92423dfb1733a40e2e6058a603478b_30.png)

Alternatively， if you only want to populate a small number of rows in an individual table。

 instead of populating an entire database， you can use the PHP MyAdmin tool to manually enter rows or run SQL insertert statements。



![](img/7d92423dfb1733a40e2e6058a603478b_32.png)

![](img/7d92423dfb1733a40e2e6058a603478b_33.png)

![](img/7d92423dfb1733a40e2e6058a603478b_34.png)

To manually enter rows in PhP My admin on the Insert tab， enter the data， then click go。



![](img/7d92423dfb1733a40e2e6058a603478b_36.png)

By default， you can enter two rows at a time， but you can increase or decrease this as required。

 and after you have entered data into a table， you can view that data on the B tab。



![](img/7d92423dfb1733a40e2e6058a603478b_38.png)

![](img/7d92423dfb1733a40e2e6058a603478b_39.png)

![](img/7d92423dfb1733a40e2e6058a603478b_40.png)

Manualally entering rows and running individual SQL statements is fine for small amounts of data。

 but if you're loading a large number of rows， you will find the import functionality is easier and quicker to use。



![](img/7d92423dfb1733a40e2e6058a603478b_42.png)

![](img/7d92423dfb1733a40e2e6058a603478b_43.png)

You can use the MySQL load data In file statement to import the contents of a CSV file into an existing MySQL table。

 or you can use the MySQL importm utility passing the name of the database that the table resides in and the name of the CSV file。



![](img/7d92423dfb1733a40e2e6058a603478b_45.png)

![](img/7d92423dfb1733a40e2e6058a603478b_46.png)

The table name is inferred from the name of the CSV file。

 so you must ensure that your file name matches your table name exactly。Alternatively。

 PhP My admin provides a visual interface for importing data into tables on the import tab。

 click browserow to select your file。

![](img/7d92423dfb1733a40e2e6058a603478b_48.png)

![](img/7d92423dfb1733a40e2e6058a603478b_49.png)

Check that the format and options have been correctly determined from the data file and clickGo。



![](img/7d92423dfb1733a40e2e6058a603478b_51.png)

Using this method， you can import up to2 megabytes of data at a time。

 you can also use PHP My admin to export data from a table to CSV format。



![](img/7d92423dfb1733a40e2e6058a603478b_53.png)

![](img/7d92423dfb1733a40e2e6058a603478b_54.png)

On the export tab， change the format to CSV， optionally specify which rows to export。



![](img/7d92423dfb1733a40e2e6058a603478b_56.png)

And then， click， go。

![](img/7d92423dfb1733a40e2e6058a603478b_58.png)

In this video， you learned that you can use backup and restore functionality at the command line and in PhHP MyAdmin to populate databases。

 you can manually insert small amounts of data using PhHP MyAdmin。

 and you can use import and export functionality at the command line and in PhHP MyAdmin to populate tables and save their data to files。



![](img/7d92423dfb1733a40e2e6058a603478b_60.png)
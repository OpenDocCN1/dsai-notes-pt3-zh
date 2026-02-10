# IBM数据工程专业证书第3课：《Python数据工程项目课程（IBM）》python-project-for-data-engineering - P3：2_提取 转换 加载 etl.zh_en - GPT中英字幕课程资源 - BV1xz4y1W7Gb

![](img/55b12f496e9162db388d9441d952be64_0.png)

![](img/55b12f496e9162db388d9441d952be64_1.png)

Hello and welcome to Extract Transform and load or ETL for short After watching this video。

 you will be able to define the Ex transform load process or ETL process。

 explain the correct order for ETL functions， and write a simple ETL program。



![](img/55b12f496e9162db388d9441d952be64_3.png)

![](img/55b12f496e9162db388d9441d952be64_4.png)

Have you ever wondered how data was collected from multiple sources and combined to become a single source of information。

 This type of data collection is called batch processing。 And today。

 we will be exploring a type of batch processing called extract， transform and load， extracttract。

 transform and load or ETL does exactly what the name implies。

 It is the process of extracting large amounts of data from multiple sources and formats and transforming it into one specific format before loading it into a database or target file。

 Let us use the following block diagram to represent the ETL pipeline。



![](img/55b12f496e9162db388d9441d952be64_6.png)

![](img/55b12f496e9162db388d9441d952be64_7.png)

![](img/55b12f496e9162db388d9441d952be64_8.png)

![](img/55b12f496e9162db388d9441d952be64_9.png)

![](img/55b12f496e9162db388d9441d952be64_10.png)

![](img/55b12f496e9162db388d9441d952be64_11.png)

For example， let us say you are the owner of a startup that has built an AI to predict if someone is at risk for diabetes using height and body weight。

 Some of your data is in Cv format and the other data in J files。

 You need to extract all this data into one file so the AI can read it。 your data is in imperial。

 but the AI uses metric units， so you must transform it。 The AI only read Cv data in one big file。

 and so you need to load the data as Cv。 let us implement the following ETl with Python。 First。

 we will look at the extraction step with some simple examples。

 but before we discuss the extract function。 let us discuss its composite function。

 Here is the Gb function from the Gob module。 The input is the file extension and the output is a list of files with that particular extension。

 Consider the list of Jason and Cv。

![](img/55b12f496e9162db388d9441d952be64_13.png)

![](img/55b12f496e9162db388d9441d952be64_14.png)

![](img/55b12f496e9162db388d9441d952be64_15.png)

![](img/55b12f496e9162db388d9441d952be64_16.png)

![](img/55b12f496e9162db388d9441d952be64_17.png)

![](img/55b12f496e9162db388d9441d952be64_18.png)

Fles the input is the Gloob file extension preceded by a star and adopt dot。

 The output is a list of CSV files， and we can do the same for JO files。

 We can write a file to extract CSV of names， height and weight the input is the file name of the CSv file。

 The result is a data frame。 We can do the same for JO formats。 The input is the name of the JO file。

 The output is a data frame。 Check out the lab for more examples。



![](img/55b12f496e9162db388d9441d952be64_20.png)

![](img/55b12f496e9162db388d9441d952be64_21.png)

![](img/55b12f496e9162db388d9441d952be64_22.png)

![](img/55b12f496e9162db388d9441d952be64_23.png)

The extract function will extract large amounts of data from multiple sources in batches。

 We create an empty data frame。

![](img/55b12f496e9162db388d9441d952be64_25.png)

The result is an empty data frame with the column names assigned。



![](img/55b12f496e9162db388d9441d952be64_27.png)

Let us look at the process to extract the CSV file。



![](img/55b12f496e9162db388d9441d952be64_29.png)

We start by adding a loop to find all of the CSV files。

This can be accomplished easily by adding a Gob function。 By adding this function。

 it will now find and load all of the CSV file names。 And with each iteration of the loop。

 the CV files are appended to the data frame。 The first iteration would be appended。

 and then the second iteration， resulting in a list of extracted data。

 We will review the parameter ignore underscore index equals true later。😊。



![](img/55b12f496e9162db388d9441d952be64_31.png)

![](img/55b12f496e9162db388d9441d952be64_32.png)

![](img/55b12f496e9162db388d9441d952be64_33.png)

![](img/55b12f496e9162db388d9441d952be64_34.png)

This section of code appends the J files to the data frame。

 Let us see how the parameter ignore underscore index sets the index in the order。

 Each column was appended to the data frame。 We will look at the output extracted data。

 If we did not set the parameter ignore underscore index to true。

 Then the index of the data frame extracted underscore data would be the same as the row number of the original file。

 If we do set the ignore underscore index to true。 then the order of each row would be the same as the order。

 the row was appended to the data frame。

![](img/55b12f496e9162db388d9441d952be64_36.png)

![](img/55b12f496e9162db388d9441d952be64_37.png)

![](img/55b12f496e9162db388d9441d952be64_38.png)

![](img/55b12f496e9162db388d9441d952be64_39.png)

So now that we have collected the data， the next step in the process is to transform it。

 this function will convert the column height， which is inches to millimeters and the column pounds to kilograms and return the output in the variable data。

 let us take a closer look。

![](img/55b12f496e9162db388d9441d952be64_41.png)

In the input data frame， the column height is in feet。

 We apply the following operation to the column to convert it to meters and round it to two decimal places。

 The resulting data frame column height is now in meters， and we can do the same for weight。

 Let us now look at loading and logging。 Now that we have collected and define the data。

 it is time to load it into the target file。 In this case， we save the panda's data frame as a CSV。



![](img/55b12f496e9162db388d9441d952be64_43.png)

![](img/55b12f496e9162db388d9441d952be64_44.png)

We have now gone through the process of how to extract。

 transform and load data from multiple sources and finalize it into one final target file。

 Before completing our task， we need to create a logging entry。 to do this。

 we will create a logging function。 Start by creating a variable named timestamp underscore format。

 which determines the formatting of the time and date。 Next is the now variable。

 and it will capture the current time by calling date time。 With this addition。

 date time was imported for it to work correctly We then pull that information together by opening a file and writing the information to the file with the addition of the a。

 all of the data written will be appended to the existing information。

 By creating this type of entry， we are then able to attach a timestamp to each part of the process of when it begins and when it has completed。



![](img/55b12f496e9162db388d9441d952be64_46.png)

![](img/55b12f496e9162db388d9441d952be64_47.png)

![](img/55b12f496e9162db388d9441d952be64_48.png)

![](img/55b12f496e9162db388d9441d952be64_49.png)

![](img/55b12f496e9162db388d9441d952be64_50.png)

Now that we have defined all the code necessary to run the ETL process on the selected data。

 the last thing we need to do is call all of the functions。

 we first start by calling the extract underscore data function。



![](img/55b12f496e9162db388d9441d952be64_52.png)

The data received from this step will then be transferred to the second step of transforming the data。

 after this has been completed， the data is then loaded into the target file。 Also。

 note that before and after every step， the date and time for start and completion has been added。



![](img/55b12f496e9162db388d9441d952be64_54.png)

![](img/55b12f496e9162db388d9441d952be64_55.png)

![](img/55b12f496e9162db388d9441d952be64_56.png)

![](img/55b12f496e9162db388d9441d952be64_57.png)

In this video， you learned how to write a simple extract function。

 how to write a simple transform function， how to write a simple load function。

 and how to write a simple logging function。 Check out the labs for more。



![](img/55b12f496e9162db388d9441d952be64_59.png)

![](img/55b12f496e9162db388d9441d952be64_60.png)
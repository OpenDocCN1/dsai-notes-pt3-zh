# IBM应用人工智能（从0开始搭建AI机器人）｜IBM Applied AI （中英字幕） - P79：13_使用pandas加载数据.zh_en - GPT中英字幕课程资源 - BV1p64y1H7LM

Depenencies or libraries are pre written code to help solve problems In this video。

 we will introduce Pandas， a popular library for data analysis。



![](img/bc63774810e1edc394ab376fa582e1de_1.png)

![](img/bc63774810e1edc394ab376fa582e1de_2.png)

![](img/bc63774810e1edc394ab376fa582e1de_3.png)

We can import the library or a dependency like pandas using the following command。

 We start with the import command， followed by the name of the library。

 We now have access to a large number of prebuilt classes and functions。

 This assumes the library is installed。 in our lab environment。

 All the necessary libraries are installed。 Let's say we would like to load a CSV file using the pandas built in function。

 Read CV A CV is a typical file type used to store data。 We simply type the word pandas。

 Then a dot and the name of the function with all the inputs。

 typing pandas all the time may get tedious。 We can use the as statement to shorten the name of the library。

 In this case， we use the standard abbreviation P D。 Now。

 we type P D and a dot followed by the name of the function we would like to use。 In this case。

 read underscore CV。

![](img/bc63774810e1edc394ab376fa582e1de_5.png)

![](img/bc63774810e1edc394ab376fa582e1de_6.png)

![](img/bc63774810e1edc394ab376fa582e1de_7.png)

![](img/bc63774810e1edc394ab376fa582e1de_8.png)

![](img/bc63774810e1edc394ab376fa582e1de_9.png)

![](img/bc63774810e1edc394ab376fa582e1de_10.png)

![](img/bc63774810e1edc394ab376fa582e1de_11.png)

![](img/bc63774810e1edc394ab376fa582e1de_12.png)

![](img/bc63774810e1edc394ab376fa582e1de_13.png)

![](img/bc63774810e1edc394ab376fa582e1de_14.png)

![](img/bc63774810e1edc394ab376fa582e1de_15.png)

We are not limited to the abbreviation P D。 In this case， we use the term banana。

 We will stick with P D for the rest of this video。 Let's examine this code， more in depth。



![](img/bc63774810e1edc394ab376fa582e1de_17.png)

![](img/bc63774810e1edc394ab376fa582e1de_18.png)

One way pandas allows you to work with data is with a data frame。

 Let's go over the process to go from a CSV file to a data frame。



![](img/bc63774810e1edc394ab376fa582e1de_20.png)

![](img/bc63774810e1edc394ab376fa582e1de_21.png)

This variable stores the path of the C SV。 It is used as an argument to the read。

 underscore C SV function。 The result is stored to the variable D F。 This is short for data frame。



![](img/bc63774810e1edc394ab376fa582e1de_23.png)

![](img/bc63774810e1edc394ab376fa582e1de_24.png)

![](img/bc63774810e1edc394ab376fa582e1de_25.png)

Now that we have the data in a data frame， we can work with it。



![](img/bc63774810e1edc394ab376fa582e1de_27.png)

We can use the method head to examine the first five rows of a data frame。

 The process for loading an Excel file is similar。 We use the path of the Excel file。

 The function reads Excel。 The result is a data frame。



![](img/bc63774810e1edc394ab376fa582e1de_29.png)

![](img/bc63774810e1edc394ab376fa582e1de_30.png)

![](img/bc63774810e1edc394ab376fa582e1de_31.png)

A data frame is comprised of rows and columns。 We can create a data frame out of a dictionary。

 The keys correspond to the column labels。 The values are lists corresponding to the rows。

 We then cast the dictionary to a data frame using the function data frame。

 We can see the direct correspondence between the table。 The keys correspond to the table headers。

 The values are lists corresponding to the rows。😊，We can create a new data frame consisting of one column。

 We just put the data frame name， in this case， D F and the name of the column header enclosed in double brackets。

The result is a new data frame comprised of the original column。

You can do the same thing for multiple columns。 We just put the data frame name， in this case。

 D F and the name of the multiple column headers enclosed in double brackets。



![](img/bc63774810e1edc394ab376fa582e1de_33.png)

![](img/bc63774810e1edc394ab376fa582e1de_34.png)

The result is a new data frame comprised of the specified columns。


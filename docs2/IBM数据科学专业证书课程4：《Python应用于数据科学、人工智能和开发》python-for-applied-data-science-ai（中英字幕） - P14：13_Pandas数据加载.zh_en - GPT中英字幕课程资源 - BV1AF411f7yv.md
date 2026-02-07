# IBM数据科学专业证书课程4：《Python应用于数据科学、人工智能和开发》python-for-applied-data-science-ai（中英字幕） - P14：13_Pandas数据加载.zh_en - GPT中英字幕课程资源 - BV1AF411f7yv

Depenencies or libraries are pre written code to help solve problems。 In this video。

 we will introduce Padas， a popular library for data analysis。



![](img/4ab665d1dc6abb401a393f4111e6e201_1.png)

![](img/4ab665d1dc6abb401a393f4111e6e201_2.png)

![](img/4ab665d1dc6abb401a393f4111e6e201_3.png)

We can import the library or a dependency like pandas using the following command。

 We start with the import command。 followed by the name of the library。

 We now have access to a large number of prebuilt classes and functions。

 This assumes the library is installed。 in our lab environment。

 All the necessary libraries are installed。 Let's say we would like to load a CV file using the pandas built in function。

 Read CV。 A CV is a typical file type used to store data。 We simply type the word pandas。

 Then a dot and the name of the function with all the inputs。

 typing pandas all the time may get tedious。 We can use the as statement to shorten the name of the library。

 In this case， we use the standard abbreviation P D。 Now。

 we type P D and a dot followed by the name of the function we would like to use。 In this case， read。

 underscore CV。

![](img/4ab665d1dc6abb401a393f4111e6e201_5.png)

![](img/4ab665d1dc6abb401a393f4111e6e201_6.png)

![](img/4ab665d1dc6abb401a393f4111e6e201_7.png)

![](img/4ab665d1dc6abb401a393f4111e6e201_8.png)

![](img/4ab665d1dc6abb401a393f4111e6e201_9.png)

![](img/4ab665d1dc6abb401a393f4111e6e201_10.png)

![](img/4ab665d1dc6abb401a393f4111e6e201_11.png)

![](img/4ab665d1dc6abb401a393f4111e6e201_12.png)

![](img/4ab665d1dc6abb401a393f4111e6e201_13.png)

![](img/4ab665d1dc6abb401a393f4111e6e201_14.png)

![](img/4ab665d1dc6abb401a393f4111e6e201_15.png)

We are not limited to the abbreviation。 P D。 In this case， we use the term banana。

 We will stick with P D for the rest of this video。 Let's examine this code more in depth。

 One way pandas allows you to work with data is with a data frame。

 Let's go over the process to go from a CV file to a data frame。



![](img/4ab665d1dc6abb401a393f4111e6e201_17.png)

![](img/4ab665d1dc6abb401a393f4111e6e201_18.png)

![](img/4ab665d1dc6abb401a393f4111e6e201_19.png)

![](img/4ab665d1dc6abb401a393f4111e6e201_20.png)

This variable stores the path of the C SV。 It is used as an argument to the read。

 underscore CV function。 The result is stored to the variable D F。 This is short for data frame。



![](img/4ab665d1dc6abb401a393f4111e6e201_22.png)

![](img/4ab665d1dc6abb401a393f4111e6e201_23.png)

![](img/4ab665d1dc6abb401a393f4111e6e201_24.png)

Now that we have the data in a data frame， we can work with it。



![](img/4ab665d1dc6abb401a393f4111e6e201_26.png)

We can use the method head to examine the first five rows of a data frame。

 The process for loading an Excel file is similar。 We use the path of the Excel file。

 The function reads Excel。 The result is a data frame。



![](img/4ab665d1dc6abb401a393f4111e6e201_28.png)

![](img/4ab665d1dc6abb401a393f4111e6e201_29.png)

![](img/4ab665d1dc6abb401a393f4111e6e201_30.png)

A data frame is comprised of rows and columns。 We can create a data frame out of a dictionary。

 The keys correspond to the column labels。 The values are lists corresponding to the rows。

 We then cast the dictionary to a data frame using the function data frame。

 We can see the direct correspondence between the table。 The keys correspond to the table headers。

 The values are lists corresponding to the rows。😊，We can create a new data frame consisting of one column。

 We just put the data frame name， in this case， D F and the name of the column header enclosed in double brackets。



![](img/4ab665d1dc6abb401a393f4111e6e201_32.png)

![](img/4ab665d1dc6abb401a393f4111e6e201_33.png)

The result is a new data frame comprised of the original column。

You can do the same thing for multiple columns。 We just put the data frame name， in this case。

 D F and the name of the multiple column headers enclosed in double brackets。



![](img/4ab665d1dc6abb401a393f4111e6e201_35.png)

![](img/4ab665d1dc6abb401a393f4111e6e201_36.png)

The result is a new data frame comprised of the specified columns。


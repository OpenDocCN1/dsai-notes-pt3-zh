# IBM数据科学专业证书课程4：《Python应用于数据科学、人工智能和开发》python-for-applied-data-science-ai（中英字幕） - P24：23_多种文件格式处理（CSV-XML-JSON-XLSX）.zh_en - GPT中英字幕课程资源 - BV1AF411f7yv

![](img/3694168a4f31e31a6990ca815878b938_0.png)

![](img/3694168a4f31e31a6990ca815878b938_1.png)

Hello， welcome to working with different file formats After watching this video。

 you will be able to define different file formats such as CSV。

 XML and Jason write simple programs to read and output data and list what Python libraries are needed to extract data。



![](img/3694168a4f31e31a6990ca815878b938_3.png)

![](img/3694168a4f31e31a6990ca815878b938_4.png)

When collecting data， you will find there are many different file formats that need to be collected or read in order to complete a data driven story or analysis When gathering the data。

 Python can make the process simpler with its predefined libraries， but before we explore Python。

 let us first check out some of the various file formats。



![](img/3694168a4f31e31a6990ca815878b938_6.png)

![](img/3694168a4f31e31a6990ca815878b938_7.png)

![](img/3694168a4f31e31a6990ca815878b938_8.png)

![](img/3694168a4f31e31a6990ca815878b938_9.png)

Looking at a file name， you will notice an extension at the end of the title these extensions let you know what type of file it is and what is needed to open it。

 For instance， if you see a title like file example do CSv， you will know this is a CSV file。

 but this is only one example of different file types， there are many more such as Jason or XML。



![](img/3694168a4f31e31a6990ca815878b938_11.png)

![](img/3694168a4f31e31a6990ca815878b938_12.png)

![](img/3694168a4f31e31a6990ca815878b938_13.png)

![](img/3694168a4f31e31a6990ca815878b938_14.png)

![](img/3694168a4f31e31a6990ca815878b938_15.png)

When coming across these different file formats and trying to access their data。

 we need to utilize Python libraries to make this process easier the first Python library to become familiar with is called pandas by importing this library in the beginning of the code we are then able to easily read the different file types。



![](img/3694168a4f31e31a6990ca815878b938_17.png)

![](img/3694168a4f31e31a6990ca815878b938_18.png)

![](img/3694168a4f31e31a6990ca815878b938_19.png)

![](img/3694168a4f31e31a6990ca815878b938_20.png)

Since we have now imported the Pada library， let us use it to read the first CSV file In this instance。

 we have come across the file example do CSv file。 The first step is to assign the file to a variable。

 then create another variable to read the file with the help of the Pada library。

 We can then call read underscore CSv function to output the data to the screen。



![](img/3694168a4f31e31a6990ca815878b938_22.png)

![](img/3694168a4f31e31a6990ca815878b938_23.png)

![](img/3694168a4f31e31a6990ca815878b938_24.png)

![](img/3694168a4f31e31a6990ca815878b938_25.png)

![](img/3694168a4f31e31a6990ca815878b938_26.png)

With this example， there were no headers for the data， so it added the first line as the header。

 since we do not want the first line of data as the header。

 let us find out how to correct this issue。

![](img/3694168a4f31e31a6990ca815878b938_28.png)

Now that we have learned how to read and output the data from a CSV file。

 let us make it look a little more organized。

![](img/3694168a4f31e31a6990ca815878b938_30.png)

![](img/3694168a4f31e31a6990ca815878b938_31.png)

From the last example， we were able to print out the data， but because the file had no headers。

 it printed the first line of data as the header。 we easily solve this by adding a data frame attribute。

 We use the variable Df to call the file， then add the columns attribute by adding this one line to our program。

 we can then neatly organize the data output into the specified headers for each column。



![](img/3694168a4f31e31a6990ca815878b938_33.png)

![](img/3694168a4f31e31a6990ca815878b938_34.png)

![](img/3694168a4f31e31a6990ca815878b938_35.png)

![](img/3694168a4f31e31a6990ca815878b938_36.png)

![](img/3694168a4f31e31a6990ca815878b938_37.png)

![](img/3694168a4f31e31a6990ca815878b938_38.png)

The next file format we will explore is the J file format in this type of file。

 the text is written in a language independent data format and is similar to a Python dictionary。

 The first step in reading this type of file is to import Jason。



![](img/3694168a4f31e31a6990ca815878b938_40.png)

![](img/3694168a4f31e31a6990ca815878b938_41.png)

After importing Jason， we can add a line to open the file。

 call the load attribute of Jason to begin and read the file， and lastly， we can then print the file。

 The next file format type is XML， also known as extensible markup language while the panda's library does not have an attribute to read this type of file。

 let us explore how to parse this type of file。

![](img/3694168a4f31e31a6990ca815878b938_43.png)

![](img/3694168a4f31e31a6990ca815878b938_44.png)

![](img/3694168a4f31e31a6990ca815878b938_45.png)

![](img/3694168a4f31e31a6990ca815878b938_46.png)

![](img/3694168a4f31e31a6990ca815878b938_47.png)

The first step to read this type of file is to import XML by importing this library。

 we can then use the E tree attribute to parse the XML file。

 we then add the column headers and assign them to the data frame。



![](img/3694168a4f31e31a6990ca815878b938_49.png)

![](img/3694168a4f31e31a6990ca815878b938_50.png)

Then create a loop to go through the document to collect the necessary data and append the data to a data frame。



![](img/3694168a4f31e31a6990ca815878b938_52.png)

In this video， you learned how to recognize different file types。

 how to use Python libraries to extract data， and how to use data frames when collecting data。



![](img/3694168a4f31e31a6990ca815878b938_54.png)

![](img/3694168a4f31e31a6990ca815878b938_55.png)

![](img/3694168a4f31e31a6990ca815878b938_56.png)

![](img/3694168a4f31e31a6990ca815878b938_57.png)
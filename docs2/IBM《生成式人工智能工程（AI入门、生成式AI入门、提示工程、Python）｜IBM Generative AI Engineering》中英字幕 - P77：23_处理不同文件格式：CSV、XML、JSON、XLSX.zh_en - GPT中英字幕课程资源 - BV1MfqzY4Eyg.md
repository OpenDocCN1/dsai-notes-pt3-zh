# IBM《生成式人工智能工程（AI入门、生成式AI入门、提示工程、Python）｜IBM Generative AI Engineering》中英字幕 - P77：23_处理不同文件格式：CSV、XML、JSON、XLSX.zh_en - GPT中英字幕课程资源 - BV1MfqzY4Eyg

![](img/788e51f85277ac92ed489db73d19ceaa_0.png)

![](img/788e51f85277ac92ed489db73d19ceaa_1.png)

Hello， welcome to working with different file formats After watching this video。

 you will be able to define different file formats such as CSV。

 XML and Jason write simple programs to read and output data and list what Python libraries are needed to extract data。



![](img/788e51f85277ac92ed489db73d19ceaa_3.png)

![](img/788e51f85277ac92ed489db73d19ceaa_4.png)

When collecting data， you will find there are many different file formats that need to be collected or read in order to complete a data driven story or analysis When gathering the data。

 Python can make the process simpler with its predefined libraries， but before we explore Python。

 let us first check out some of the various file formats。



![](img/788e51f85277ac92ed489db73d19ceaa_6.png)

Looking at a file name， you will notice an extension at the end of the title these extensions let you know what type of file it is and what is needed to open it。

 For instance， if you see a title like file example do CSv， you will know this is a CSV file。

 but this is only one example of different file types， there are many more such as Jason or XML。



![](img/788e51f85277ac92ed489db73d19ceaa_8.png)

When coming across these different file formats and trying to access their data。

 we need to utilize Python libraries to make this process easier the first Python library to become familiar with is called pandas by importing this library in the beginning of the code we are then able to easily read the different file types。



![](img/788e51f85277ac92ed489db73d19ceaa_10.png)

Since we have now imported the Pada library， let us use it to read the first CSV file In this instance。

 we have come across the file example do CSv file。 The first step is to assign the file to a variable。

 then create another variable to read the file with the help of the Pada library。

 We can then call read underscore CSv function to output the data to the screen。



![](img/788e51f85277ac92ed489db73d19ceaa_12.png)

With this example， there were no headers for the data， so it added the first line as the header。

 since we do not want the first line of data as the header。

 let us find out how to correct this issue。

![](img/788e51f85277ac92ed489db73d19ceaa_14.png)

Now that we have learned how to read and output the data from a CSV file。

 let us make it look a little more organized。

![](img/788e51f85277ac92ed489db73d19ceaa_16.png)

From the last example， we were able to print out the data， but because the file had no headers。

 it printed the first line of data as the header。 we easily solve this by adding a data frame attribute。

 We use the variable Df to call the file， then add the columns attribute by adding this one line to our program。

 we can then neatly organize the data output into the specified headers for each column。



![](img/788e51f85277ac92ed489db73d19ceaa_18.png)

![](img/788e51f85277ac92ed489db73d19ceaa_19.png)

![](img/788e51f85277ac92ed489db73d19ceaa_20.png)

The next file format we will explore is the J file format in this type of file。

 the text is written in a language independent data format and is similar to a Python dictionary。

 The first step in reading this type of file is to import Jason。After importing Jason。

 we can add a line to open the file， call the load attribute of Jason to begin and read the file。

 and lastly， we can then print the file。 The next file format type is XML。

 also known as extensible markup language while the panda's library does not have an attribute to read this type of file。

 let us explore how to parse this type of file。

![](img/788e51f85277ac92ed489db73d19ceaa_22.png)

The first step to read this type of file is to import XML by importing this library。

 we can then use the E tree attribute to parse the XML file。

 we then add the column headers and assign them to the data frame。



![](img/788e51f85277ac92ed489db73d19ceaa_24.png)

![](img/788e51f85277ac92ed489db73d19ceaa_25.png)

Then create a loop to go through the document to collect the necessary data and append the data to a data frame。



![](img/788e51f85277ac92ed489db73d19ceaa_27.png)

In this video， you learned how to recognize different file types。

 how to use Python libraries to extract data， and how to use data frames when collecting data。



![](img/788e51f85277ac92ed489db73d19ceaa_29.png)

![](img/788e51f85277ac92ed489db73d19ceaa_30.png)

![](img/788e51f85277ac92ed489db73d19ceaa_31.png)
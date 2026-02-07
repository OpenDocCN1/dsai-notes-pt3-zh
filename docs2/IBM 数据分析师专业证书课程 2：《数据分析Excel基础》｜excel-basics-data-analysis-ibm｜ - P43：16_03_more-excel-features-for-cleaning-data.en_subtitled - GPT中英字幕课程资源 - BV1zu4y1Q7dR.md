# IBM 数据分析师专业证书课程 2：《数据分析Excel基础》｜excel-basics-data-analysis-ibm｜ - P43：16_03_more-excel-features-for-cleaning-data.en_subtitled - GPT中英字幕课程资源 - BV1zu4y1Q7dR

嗯。Now that we've learned how to change the case of text。

 how to change date formatting and how to trim whitespace from data in this video。

 we'll discuss how to use the flash fill and text to columns features in Excel to help clean data。

 We used flash filled briefly earlier in the course as a quick method of entering data that fits a specific pattern。

 such as the names of months or days of the week。 but it can also be used as a data cleaning tool。

 It can split a column of full names into two separate columns for the for name and surname。

 and it can also help to modify the naming convention used in a column of names。 For example。

 in the vehicle toy sales worksheet。 There is a column containing the last names of contacts and another containing their first names。

😊。

![](img/97854ac33d52a6fbf76508ae83eb7578_1.png)

If you want to use the flash fill feature to combine these names into one name column。

 you first insert a helper column。 let's call it contact name。

 Then in the first row in the new column， you enter the full name of the first contact in the format of your choice。

 For example， you might want surname。 then a comma， then the for name。

 or you might want surname and just an initial and so on。 In this case。

 let's just enter the name in the standard format of forname， then surname with a space between them。

 and then we press enter。 Next， you'll start typing the second contacts name。

 And you'll see that flash fill displays a preview of the remaining names for you。

 If you're happy with what's in the preview。 All you have to do is press enter。

 and it fills in the remaining names for you write down the column。

 It even works when there are two names in one of the columns， such as wing C here。 and dauna here。😊。

Now you can remove the original columns if you no longer need them。So in the previous task。

 we saw how to combine two columns of data into one column using flash fill。 Now。

 let's see how to use it to modify the naming convention in a column。

 Let's switch to the customer contacts worksheet。Then in the first data row of the next column。

 that is B2， we type the name of the first contact using whatever naming convention we want。

 We'll use surname。 then comma， then space。 then the for name and press enter。 again。

 when we start typing the second contact name in the next row down。 That is B3。

 F fill detects the pattern。 and fills in the remaining names in column B when we press enter。

 You could then copy and paste the column header and delete the original column A。



![](img/97854ac33d52a6fbf76508ae83eb7578_3.png)

What we couldn't do with Flash fill was take a single column with two names in and split that into two separate columns。

 We need to use the text to columns feature to do that。

So we'll close this worksheet and we won't save the changes。Now。

 let's see how the text to columns feature can help with data cleaning too， as the name suggests。

 an unlike flash fill， the text to columns feature can take a column containing multipart text。

 and split that text into one or more other columns。

 This can be useful for splitting any multipart text。

 such as names or addresses into separate component parts。

 Let's open the customer context worksheet again， Then we'll add column headings for the next two columns and copy the cell format used in the first column header。

 Then we'll widen the columns。😊。

![](img/97854ac33d52a6fbf76508ae83eb7578_5.png)

If we then select the data in column A from A2 to A23 and on the data tab， click Tex to columns。

 a wizard is launched。On the first page of the wizard。

 ensure that delimited is selected On the second page。

 ensure that only space is selected as the delimiter。 On the third page of the wizard。

 click the little arrow next to destination。 and select B2 on the worksheet。

 Then click the little arrow again to return to the wizard。 We're now finished with this wizard。

You can now see that the full customer contact names in column A have now been successfully split into two new columns in B and C。

 And you could now remove column A if you no longer need it。 will'll close this worksheet。 And again。

 we won't save the changes。 You can also achieve the same result using functions。

 This would be required if you were using Excel for the web， the online version of Excel。

 as this doesn't have the text to columns feature。😊。

There's also a bit more flexibility with functions。

 which can be especially useful if you have names that are complex and mixed。

 such as having hyphenated names or some names with a middle name。

 some with two middle initials and some with no middle initial。

So we open the customer contact worksheet again。 Then we'll add column headings for the next two columns and copy the cell format used in the first column header。

 Then we'll widen the columns。 Next， we enter the formula in B2 to extract the for name part of the name。

 This formula extracts five characters from cell A 2。 starting from the left and including the space。

Then in cell C 2， we enter the formula to extract the surname part of the name。

 This formula extracts 7 characters from cell a2， starting from the right。

Then we'll double click the fill handle and cell B2 to use Autofill to complete the column。

And we do the same to the fill handle in cell C2 to use Autofill to complete that column also。



![](img/97854ac33d52a6fbf76508ae83eb7578_7.png)

In this video， we learned how to use Flashfi and text to columns features in Excel to help clean data。



![](img/97854ac33d52a6fbf76508ae83eb7578_9.png)
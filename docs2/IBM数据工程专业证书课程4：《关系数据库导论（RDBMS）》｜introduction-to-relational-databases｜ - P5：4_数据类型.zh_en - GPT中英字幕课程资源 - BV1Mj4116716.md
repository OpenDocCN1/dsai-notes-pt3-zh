# IBM数据工程专业证书课程4：《关系数据库导论（RDBMS）》｜introduction-to-relational-databases｜ - P5：4_数据类型.zh_en - GPT中英字幕课程资源 - BV1Mj4116716

![](img/db1ed592a227b2e7775e11564788c390_0.png)

![](img/db1ed592a227b2e7775e11564788c390_1.png)

Welcome to Data typess After watching this video， you will be able to explain what data types are。

 explain how data types are used in a database。

![](img/db1ed592a227b2e7775e11564788c390_3.png)

![](img/db1ed592a227b2e7775e11564788c390_4.png)

Identify some common data types and describe the advantages of using appropriate data types。

 A database table represents a single entity， and the columns in the table represent attributes of that entity。

 For example， a table named book could contain columns for title。

 P date and the number of pages that they contain。 The information entered into each column should always be of the same sort or type of data。

 In this example， the title column should contain textual data。

 The published date column should contain a date。 and the pages column should contain a number。

 We can use this idea to define the type of data or data type that a column can store The data type that you assign to a column controls the data that the column can store。



![](img/db1ed592a227b2e7775e11564788c390_6.png)

![](img/db1ed592a227b2e7775e11564788c390_7.png)

![](img/db1ed592a227b2e7775e11564788c390_8.png)

![](img/db1ed592a227b2e7775e11564788c390_9.png)

![](img/db1ed592a227b2e7775e11564788c390_10.png)

![](img/db1ed592a227b2e7775e11564788c390_11.png)

![](img/db1ed592a227b2e7775e11564788c390_12.png)

![](img/db1ed592a227b2e7775e11564788c390_13.png)

For example， a text column can contain alphanumeric data。

 but a date column can only contain dates in a valid date format。

 and a numeric column can only contain numbers。 Different database management systems may use different names for similar data types。

 but they generally support a standard set。 So let us look at the commonly used data types in an RDBMS。

 characteract string data types include fixed length data types and variable length。

 The length of a fixed length character string is often denoted in brackets after the type name。

 such as car 10。 This type uses the same amount of space in the database Irespective of the length of the actual data stored in it。

 For example， storing a city code such as NY why for New York in a car 10 column will still take up 10 characters of space。



![](img/db1ed592a227b2e7775e11564788c390_15.png)

![](img/db1ed592a227b2e7775e11564788c390_16.png)

![](img/db1ed592a227b2e7775e11564788c390_17.png)

![](img/db1ed592a227b2e7775e11564788c390_18.png)

![](img/db1ed592a227b2e7775e11564788c390_19.png)

![](img/db1ed592a227b2e7775e11564788c390_20.png)

![](img/db1ed592a227b2e7775e11564788c390_21.png)

![](img/db1ed592a227b2e7775e11564788c390_22.png)

![](img/db1ed592a227b2e7775e11564788c390_23.png)

Variable length character strings often named VarA can specify a maximum length for the string。



![](img/db1ed592a227b2e7775e11564788c390_25.png)

Nummeric data types include integer types and decimal types。



![](img/db1ed592a227b2e7775e11564788c390_27.png)

Integer data types only hold whole numbers with no decimal places。 So 12 would be a valid entry。

 whereas 12。5 would not。 Integer data types typically use two or four bys of storage to hold at numbers from negative 2 million or 32000 to positive 2 million or 32000。

 Small ints enable you to use less space for smaller numbers。

 and big ints increase the size of the number that the data type can hold。

 Decimal data types can store whole numbers and decimal numbers。

 The sizes and precision of these data types vary between RDBMSss and have names such as numeric decimal deck。

 real double float， deck float， et cetera。 Ds slash time data can be categorized into dates。

 times and timestamps。 Ds consist of three part values for the year month and day。

 and times also generally consist of a 3。

![](img/db1ed592a227b2e7775e11564788c390_29.png)

![](img/db1ed592a227b2e7775e11564788c390_30.png)

![](img/db1ed592a227b2e7775e11564788c390_31.png)

![](img/db1ed592a227b2e7775e11564788c390_32.png)

![](img/db1ed592a227b2e7775e11564788c390_33.png)

![](img/db1ed592a227b2e7775e11564788c390_34.png)

![](img/db1ed592a227b2e7775e11564788c390_35.png)

![](img/db1ed592a227b2e7775e11564788c390_36.png)

![](img/db1ed592a227b2e7775e11564788c390_37.png)

Partt value for the hours， minutes and seconds。 A timestamp column is a combination of both and consists of seven parts。

 year， Mon， day， hour， minute， second and microsecond。

 Other commonly used data types include a boolean， which only holds one bit of information。 a0 or a1。

 You can use these for true false or yes， no type data。

 A binary string which holds a sequence of bytes that represent image， voice or other media data。

 a large object or L O B， which is generally a very large object such as a file。

 Often this type of data is stored outside of the main database table and a pointer to it。

 is held in the table。

![](img/db1ed592a227b2e7775e11564788c390_39.png)

![](img/db1ed592a227b2e7775e11564788c390_40.png)

![](img/db1ed592a227b2e7775e11564788c390_41.png)

![](img/db1ed592a227b2e7775e11564788c390_42.png)

![](img/db1ed592a227b2e7775e11564788c390_43.png)

![](img/db1ed592a227b2e7775e11564788c390_44.png)

![](img/db1ed592a227b2e7775e11564788c390_45.png)

![](img/db1ed592a227b2e7775e11564788c390_46.png)

![](img/db1ed592a227b2e7775e11564788c390_47.png)

The XML data type can store platform agnostic unstructured data in a hierarchical form In addition to the various built-in data types covered in this video。

 many relational databases also allow you to create your own custom or user definedfined data types UDTs that are derived or extended from the built in types As you might have guessed。

 you can avoid using specific data types altogether and define every column to hold character data。

 However， using the appropriate data types provides many advantages when you define the data type that a column should hold you avoid incorrect data being inserted into that column For example。

 if you try to add an author's name into the publish date column of the books table the insert will fail and you can take appropriate action when date time and numeric data is correctly typed。

 you can accurately sort that data For example， if you sort a character。



![](img/db1ed592a227b2e7775e11564788c390_49.png)

![](img/db1ed592a227b2e7775e11564788c390_50.png)

![](img/db1ed592a227b2e7775e11564788c390_51.png)

![](img/db1ed592a227b2e7775e11564788c390_52.png)

![](img/db1ed592a227b2e7775e11564788c390_53.png)

![](img/db1ed592a227b2e7775e11564788c390_54.png)

![](img/db1ed592a227b2e7775e11564788c390_55.png)

![](img/db1ed592a227b2e7775e11564788c390_56.png)

![](img/db1ed592a227b2e7775e11564788c390_57.png)

![](img/db1ed592a227b2e7775e11564788c390_58.png)

Column containing numbers into ascending order102 may be listed before 12 or the query may fail。

 However， if the column is defined as numeric， you can be sure that the numbers will be returned in numerical order as generally expected。

 Similarlyly， you can accurately select ranges of data when it is correctly typed。 For example。

 selecting all books published between January 1 2001 and December 312001。

 you can perform numeric calculations on types data。 For example。

 calculating the total cost of an order， and you can take advantage of standard functions。

 such as returning the average of a column of ages or adding two days to an order date to estimate a shipping date。

 In this video you learned that data types define the type of data that can be stored in a column There are many different data types for all kinds of data and using the correct data。



![](img/db1ed592a227b2e7775e11564788c390_60.png)

![](img/db1ed592a227b2e7775e11564788c390_61.png)

![](img/db1ed592a227b2e7775e11564788c390_62.png)

![](img/db1ed592a227b2e7775e11564788c390_63.png)

![](img/db1ed592a227b2e7775e11564788c390_64.png)

![](img/db1ed592a227b2e7775e11564788c390_65.png)

![](img/db1ed592a227b2e7775e11564788c390_66.png)

![](img/db1ed592a227b2e7775e11564788c390_67.png)

pe4 a column has many advantages。

![](img/db1ed592a227b2e7775e11564788c390_69.png)
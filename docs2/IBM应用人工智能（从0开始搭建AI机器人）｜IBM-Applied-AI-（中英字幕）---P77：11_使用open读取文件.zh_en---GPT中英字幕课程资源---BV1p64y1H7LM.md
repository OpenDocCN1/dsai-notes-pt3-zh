# IBM应用人工智能（从0开始搭建AI机器人）｜IBM Applied AI （中英字幕） - P77：11_使用open读取文件.zh_en - GPT中英字幕课程资源 - BV1p64y1H7LM

In this section， we will use Python's built in open function to create a file object and obtain the data from a TXT file。

 We will use Python's open function to get a file object。

 We can apply a method to that object to read data from the file。

 We can open the file example 1 dot TXT as follows。



![](img/71a26e369d67235ac363be86e8f5be57_1.png)

![](img/71a26e369d67235ac363be86e8f5be57_2.png)

![](img/71a26e369d67235ac363be86e8f5be57_3.png)

We use the open function。 The first argument is the file path。 This is made up of the file name。

 and the file directory。The second parameter is the mode。 Common values used include R for reading。

 W for writing and A for app。 We will use R for reading。 Finally， we have the file object。



![](img/71a26e369d67235ac363be86e8f5be57_5.png)

We can now use the file object to obtain information about the file。

 We can use the data attribute name to get the name of the file。

 The result is a string that contains the name of the file。

 We can see what mode the object is in using the data attribute mode。

 and R is shown representing read。 You should always close the file object using the method close。

 This may get tedious sometimes。 So let's use the width statement。

 using a width statement to open the file is better practice because it automatically closes the file。



![](img/71a26e369d67235ac363be86e8f5be57_7.png)

![](img/71a26e369d67235ac363be86e8f5be57_8.png)

![](img/71a26e369d67235ac363be86e8f5be57_9.png)

![](img/71a26e369d67235ac363be86e8f5be57_10.png)

![](img/71a26e369d67235ac363be86e8f5be57_11.png)

The code will run everything in the indent block， then closes the file。

 This code reads the file example 1 dot T X， T。 We can use the file object file 1。

 The code will perform all operations in the indent block。

 Then close the file at the end of the indent。

![](img/71a26e369d67235ac363be86e8f5be57_13.png)

![](img/71a26e369d67235ac363be86e8f5be57_14.png)

The method read stores the values of the file in the variable file underscore stuff as a string。

 You can print the file content。 You can check if the file content is closed。

 but you cannot read from it outside the indent。 but you can print the file content outside the indent as well。

 We can print the file content。 We will see the following。



![](img/71a26e369d67235ac363be86e8f5be57_16.png)

![](img/71a26e369d67235ac363be86e8f5be57_17.png)

![](img/71a26e369d67235ac363be86e8f5be57_18.png)

When we examine the raw string， we will see the slash N。 This is so Python knows to start a new line。



![](img/71a26e369d67235ac363be86e8f5be57_20.png)

We can output every line as an element in a list using the method Read lines。

 The first line corresponds to the first element in the list。

 The second line corresponds to the second element in the list， and so on。



![](img/71a26e369d67235ac363be86e8f5be57_22.png)

![](img/71a26e369d67235ac363be86e8f5be57_23.png)

We can use the method read line to read the first line of the file。 If we run this command。

 it will store the first line in the variable file underscore stuff。 Then print the first line。



![](img/71a26e369d67235ac363be86e8f5be57_25.png)

![](img/71a26e369d67235ac363be86e8f5be57_26.png)

![](img/71a26e369d67235ac363be86e8f5be57_27.png)

We can use the method read line twice。 The first time it's called。

 It will save the first line in the variable file underscore stuff， and then print the first line。



![](img/71a26e369d67235ac363be86e8f5be57_29.png)

![](img/71a26e369d67235ac363be86e8f5be57_30.png)

The second time it's called， it will save the second line in the variable file underscore stuff and then print the second line。

 We can use a loop to print out each line individually， as follows。



![](img/71a26e369d67235ac363be86e8f5be57_32.png)

![](img/71a26e369d67235ac363be86e8f5be57_33.png)

Let's represent every character in a string as a grid。

 We can specify the number of characters we would like to read from a string as an argument to the method read lines。



![](img/71a26e369d67235ac363be86e8f5be57_35.png)

![](img/71a26e369d67235ac363be86e8f5be57_36.png)

When we use a4 as an argument in the method read lines。

 we print out the first four characters in the file。



![](img/71a26e369d67235ac363be86e8f5be57_38.png)

![](img/71a26e369d67235ac363be86e8f5be57_39.png)

Each time we call the method， we will progress through the text。

 If we call the method with the argument 16， the first 16 characters are printed out。

 and then the new line。 If we call the method a second time。

 the next five characters are printed out。 Finally。

 if we call the method the last time where the argument 9。 the last9 characters are printed out。

 check out the labs for more examples of methods and other file types。



![](img/71a26e369d67235ac363be86e8f5be57_41.png)

![](img/71a26e369d67235ac363be86e8f5be57_42.png)

![](img/71a26e369d67235ac363be86e8f5be57_43.png)

![](img/71a26e369d67235ac363be86e8f5be57_44.png)

![](img/71a26e369d67235ac363be86e8f5be57_45.png)
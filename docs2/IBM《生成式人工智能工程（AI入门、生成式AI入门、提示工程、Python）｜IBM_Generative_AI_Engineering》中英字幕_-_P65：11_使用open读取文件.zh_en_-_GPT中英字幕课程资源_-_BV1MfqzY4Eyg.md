# IBM《生成式人工智能工程（AI入门、生成式AI入门、提示工程、Python）｜IBM Generative AI Engineering》中英字幕 - P65：11_使用open读取文件.zh_en - GPT中英字幕课程资源 - BV1MfqzY4Eyg

In this section， we will use Python's built in open function to create a file object and obtain the data from a T X T file。

 We will use Python's open function to get a file object。

 We can apply a method to that object to read data from the file。

 We can open the file example 1 dot T X T as follows。 We use the open function。

 The first argument is the file path。 This is made up of the file name and the file directory。😊。



![](img/9dac733861b5460a1a0abebac3c00af1_1.png)

![](img/9dac733861b5460a1a0abebac3c00af1_2.png)

The second parameter is the mode。 Common values used include R for reading。

 W for writing and A for app。 We will use R for reading。 Finally， we have the file object。



![](img/9dac733861b5460a1a0abebac3c00af1_4.png)

We can now use the file object to obtain information about the file。

 We can use the data attribute name to get the name off the file。

 The result is a string that contains the name of the file。

 We can see what mode the object is in using the data attribute mode。

 and R is shown representing read。 You should always close the file object using the method close。

 This may get tedious sometimes。 So let's use the width statement。

 using a width statement to open the file is better practice because it automatically closes the file。

😊。

![](img/9dac733861b5460a1a0abebac3c00af1_6.png)

The code will run everything in the indent block， then closes the file。

 This code reads the file example 1 dot T， X， T。 We can use the file object file 1。

 The code will perform all operations in the indent block。

 Then close the file at the end of the indent。The method read stores the values of the file in the variable file underscore stuff as a string。

 You can print the file content。 You can check if the file content is closed。

 but you cannot read from it outside the indent， but you can print the file content outside the indent as well。

 We can print the file content。 We will see the following。



![](img/9dac733861b5460a1a0abebac3c00af1_8.png)

When we examine the raw string， we will see the slash N。 This is so Python knows to start a new line。



![](img/9dac733861b5460a1a0abebac3c00af1_10.png)

We can output every line as an element in a list using the method Read lines。

 The first line corresponds to the first element in the list。

 The second line corresponds to the second element in the list， and so on。



![](img/9dac733861b5460a1a0abebac3c00af1_12.png)

![](img/9dac733861b5460a1a0abebac3c00af1_13.png)

We can use the method read line to read the first line of the file。 If we run this command。

 it will store the first line in the variable file underscore stuff。 Then print the first line。



![](img/9dac733861b5460a1a0abebac3c00af1_15.png)

We can use the method read line twice。 The first time it's called。

 It will save the first line in the variable file underscore stuff， and then print the first line。



![](img/9dac733861b5460a1a0abebac3c00af1_17.png)

The second time it's called， it will save the second line in the variable file underscore stuff。

 and then print the second line。

![](img/9dac733861b5460a1a0abebac3c00af1_19.png)

We can use a loop to print out each line individually， as follows。



![](img/9dac733861b5460a1a0abebac3c00af1_21.png)

Let's represent every character in a string as a grid。

 We can specify the number of characters we would like to read from a string as an argument to the method read lines。



![](img/9dac733861b5460a1a0abebac3c00af1_23.png)

When we use a4 as an argument in the method read lines。

 we print out the first four characters in the file。



![](img/9dac733861b5460a1a0abebac3c00af1_25.png)

Each time we call the method， we will progress through the text。

 If we call the method with the argument 16， the first 16 characters are printed out。

 and then the new line。 If we call the method a second time。

 the next five characters are printed out。 Finally。

 if we call the method the last time where the argument 9。 The last nine characters are printed out。

 check out the labs for more examples of methods and other file types。



![](img/9dac733861b5460a1a0abebac3c00af1_27.png)
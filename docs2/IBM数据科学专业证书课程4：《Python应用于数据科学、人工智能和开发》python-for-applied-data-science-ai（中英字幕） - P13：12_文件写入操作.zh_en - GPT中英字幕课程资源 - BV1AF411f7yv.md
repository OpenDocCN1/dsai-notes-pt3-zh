# IBM数据科学专业证书课程4：《Python应用于数据科学、人工智能和开发》python-for-applied-data-science-ai（中英字幕） - P13：12_文件写入操作.zh_en - GPT中英字幕课程资源 - BV1AF411f7yv

![](img/7fb59999986501f1112c43622aafa85f_0.png)

We can also write to files using the open function。

We will use Python's open function to get a file object to create a text file。

 we can apply method right to write data to that file as a result， text will be written to the file。



![](img/7fb59999986501f1112c43622aafa85f_2.png)

![](img/7fb59999986501f1112c43622aafa85f_3.png)

We can create the file example 2 dot T X T as follows。 We use the open function。

 The first argument is the file path。 This is made up of the file name。

 If you have that file in your directory， it will be overwritten and the file directory。

 We set the mode parameter to W for writing。 Finally， we have the file object。

 As before we use the with statement。 The code will run everything in the indent block。

 then close the file。 We create the file object file1。



![](img/7fb59999986501f1112c43622aafa85f_5.png)

![](img/7fb59999986501f1112c43622aafa85f_6.png)

![](img/7fb59999986501f1112c43622aafa85f_7.png)

We use the open function。 This creates a file example2 dot T X， T in your directory。

 We use the method right to write data into the file。 The argument is the text we would like。

 input into the file。

![](img/7fb59999986501f1112c43622aafa85f_9.png)

![](img/7fb59999986501f1112c43622aafa85f_10.png)

![](img/7fb59999986501f1112c43622aafa85f_11.png)

If we use the right method successively， each time it's called， it will write to the file。

 The first time it is called， we will write。 this is line A with a slash N to represent a new line。

 The second time we call the method， it will write this is line B。 Then it will close the file。

 We can write each element in a list to a file。

![](img/7fb59999986501f1112c43622aafa85f_13.png)

![](img/7fb59999986501f1112c43622aafa85f_14.png)

![](img/7fb59999986501f1112c43622aafa85f_15.png)

As before we use a with command and the open function to create a file。

 the list lines has three elements consisting of text。

 We use a four loop to read each element of the first lines and pass it to the variable line。



![](img/7fb59999986501f1112c43622aafa85f_17.png)

![](img/7fb59999986501f1112c43622aafa85f_18.png)

![](img/7fb59999986501f1112c43622aafa85f_19.png)

The first iteration of the loop writes the first element of the list to the file example2。



![](img/7fb59999986501f1112c43622aafa85f_21.png)

The second iteration writes the second element of the list， and so on。



![](img/7fb59999986501f1112c43622aafa85f_23.png)

At the end of the loop， the file will be closed。

![](img/7fb59999986501f1112c43622aafa85f_25.png)

We can set the mode to append it using a lower case A。 This will not create a new file。

 but just use the existing file。 If we call the method right。



![](img/7fb59999986501f1112c43622aafa85f_27.png)

![](img/7fb59999986501f1112c43622aafa85f_28.png)

It will just write to the existing file， then add this is line C， then close the file。



![](img/7fb59999986501f1112c43622aafa85f_30.png)

![](img/7fb59999986501f1112c43622aafa85f_31.png)

We can copy one file to a new file as follows。 First。

 we read the file example 1 and interact with it via the file object， read file。

 Then we create a new file example 3 and use the file object right file to interact with it。



![](img/7fb59999986501f1112c43622aafa85f_33.png)

![](img/7fb59999986501f1112c43622aafa85f_34.png)

The for loop takes a line from the file object read file and stores it in the file example3。

 using the file object right file。

![](img/7fb59999986501f1112c43622aafa85f_36.png)

![](img/7fb59999986501f1112c43622aafa85f_37.png)

The first iteration copies the first line。 The second iteration copies the second line till the end of the file is reached。

 Then both files are closed。

![](img/7fb59999986501f1112c43622aafa85f_39.png)

![](img/7fb59999986501f1112c43622aafa85f_40.png)

Check out the labs for more examples。
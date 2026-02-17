# IBM《生成式人工智能工程（AI入门、生成式AI入门、提示工程、Python）｜IBM Generative AI Engineering》中英字幕 - P63：9_异常处理.zh_en - GPT中英字幕课程资源 - BV1MfqzY4Eyg

![](img/8e52dd9b2f32d961f3c123a37280d427_0.png)

![](img/8e52dd9b2f32d961f3c123a37280d427_1.png)

Hello and welcome to exception handling After watching this video you will be able to explain exception handling。

 demonstrate the use of exception handling， and understand the basics of exception handling。



![](img/8e52dd9b2f32d961f3c123a37280d427_3.png)

![](img/8e52dd9b2f32d961f3c123a37280d427_4.png)

![](img/8e52dd9b2f32d961f3c123a37280d427_5.png)

Have you ever mistakenly entered a number when you were supposed to enter text in an input field。

 most of us have either in error or when testing out a program。

 but do you know why it gave an error message instead of completing and terminating the program In order for the error message to appear。

 An event was triggered in the background。 This event was activated because the program tried to perform a computation on the name entry and realized the entry contained numbers and not letters by encasing this code in an exception handler。

 the program knew how to deal with this type of error and was able to output the error message to continue with the program This is one of many errors that can happen when asking for user input。

 So let us see how exception handling works We will first explore the tryex statement。

 This type of statement will first attempt to execute the code in the try block。

 But if an error occurs， it will kick out and begin searching。



![](img/8e52dd9b2f32d961f3c123a37280d427_7.png)

![](img/8e52dd9b2f32d961f3c123a37280d427_8.png)

For the exception that matches the error Once it finds the correct exception to handle the error。

 it will then execute that line of code。 For example。

 perhaps you are writing a program that will open and write a file After starting the program and error occurred as the data was not able to be read because of this error。

 the program skipped over the code lines under the try statement and went directly to the exception line Since this error fell within the IO error guidelines。

 it printed unable to open or read the data in the file to our console When writing simple program。

 we can sometimes get away with only one accept statement but what happens if another error occurs that is not caught by the IO error If that happened。

 we would need to add another accept statement for this except statement。

 you will notice that the type of error to catch is not specified while this may seem a logical step so the program will catch all errors and not term。



![](img/8e52dd9b2f32d961f3c123a37280d427_10.png)

![](img/8e52dd9b2f32d961f3c123a37280d427_11.png)

![](img/8e52dd9b2f32d961f3c123a37280d427_12.png)

This is not a best practice。 For example， perhaps our small program was just one section of a much larger program that was over1 thousand lines of code。

 Our task was to debug the program as it kept throwing an error causing a disruption for our users when investigating the program。

 you found this error kept appearing。 because this error had no details。

 you ended up spending hours trying to pinpoint and fix the error。 So far in our program。

 we have defined that an error message should print out if an error occurs。

 but we do not receive any messages that the program executed properly。

 This is where we can now add an else statement to give us that notification。

 by adding this else statement， it will provide us a notification to the console that the file was written successfully。

 Now that we have defined what will happen if our program executes properly， or if an error occurs。

 there is one last statement to add for this example。



![](img/8e52dd9b2f32d961f3c123a37280d427_14.png)

![](img/8e52dd9b2f32d961f3c123a37280d427_15.png)

![](img/8e52dd9b2f32d961f3c123a37280d427_16.png)

![](img/8e52dd9b2f32d961f3c123a37280d427_17.png)

![](img/8e52dd9b2f32d961f3c123a37280d427_18.png)

We are opening a file the last thing we need to do is close the file by adding a final statement。

 it will tell the program to close the file no matter the end result and print file is now closed to our console In this video you learned how to write a try accept statement why it is important to always define errors when creating exceptions and how to add an else and final statement。



![](img/8e52dd9b2f32d961f3c123a37280d427_20.png)

![](img/8e52dd9b2f32d961f3c123a37280d427_21.png)

![](img/8e52dd9b2f32d961f3c123a37280d427_22.png)
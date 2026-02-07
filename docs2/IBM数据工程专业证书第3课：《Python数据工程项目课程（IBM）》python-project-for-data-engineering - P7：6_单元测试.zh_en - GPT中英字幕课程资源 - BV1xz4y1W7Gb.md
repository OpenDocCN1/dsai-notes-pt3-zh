# IBM数据工程专业证书第3课：《Python数据工程项目课程（IBM）》python-project-for-data-engineering - P7：6_单元测试.zh_en - GPT中英字幕课程资源 - BV1xz4y1W7Gb

![](img/bcb0861715520176234141b6640fa014_0.png)

Welcome to unitt Testing。After watching this video， you will be able to define unit testing。

 Ex the unit test process， build and execute unit tests， and review the output of a unit test。😊。



![](img/bcb0861715520176234141b6640fa014_2.png)

![](img/bcb0861715520176234141b6640fa014_3.png)

![](img/bcb0861715520176234141b6640fa014_4.png)

Unit testing is a method to validate if units of code are operating as designed。 A unit is a smaller。

 testable part of an application。 Here is an example of a unit which has two functions。

 Square and doubleubr in the my module dot pi file。

 The square function is written as depth square number return number asterisk asterisk2。 Similarly。

 the code for the doubler function is written as depth， doubleubr number return number asterisk 2。😊。



![](img/bcb0861715520176234141b6640fa014_6.png)

![](img/bcb0861715520176234141b6640fa014_7.png)

To develop unit tests， you will use the unit Test library。

 which is an installed Python module providing a framework containing test functionality。

Let's briefly review the end to end testing process from unit testing through publishing to the production code base。



![](img/bcb0861715520176234141b6640fa014_9.png)

During code development， you will test each unit。 The test is performed in two phases。



![](img/bcb0861715520176234141b6640fa014_11.png)

In the first phase， you will test the unit on your local system。 If the test fails。

 you will determine the reason for the failure and fix the issue。 Then you will again， test the unit。



![](img/bcb0861715520176234141b6640fa014_13.png)

After the unit test passes， you will need to test the unit in a server environment。

 such as the continuous integration continuous delivery or C， ICD test server。



![](img/bcb0861715520176234141b6640fa014_15.png)

If the unit fails the server test， you will receive the failure details。



![](img/bcb0861715520176234141b6640fa014_17.png)

You will need to determine and fix the issue。

![](img/bcb0861715520176234141b6640fa014_19.png)

Once the unit passes the server test， the unit is integrated into the final code base。



![](img/bcb0861715520176234141b6640fa014_21.png)

After an overview to the unit test process， let's review some test functions to understand how to build unit tests。

Notice the code for the unit and the unit test， observe that the name of the unit file is my module dot pi。



![](img/bcb0861715520176234141b6640fa014_23.png)

The unit test file has the word test， appended or preended。This is a good naming convention。

 as it helps to clearly differentiate the unit file from the unit test file。😊。

Let's look at the steps to create a unit test file。



![](img/bcb0861715520176234141b6640fa014_25.png)

The first step is to import the unit Test Python library， type import unit Test。



![](img/bcb0861715520176234141b6640fa014_27.png)

Next， import the functions to test， for example， to import the square and Dubr from the My moduleule unit to unit Test。

 type from My module Import square comma Dubr。

![](img/bcb0861715520176234141b6640fa014_29.png)

Then build the unit testing class to call the unit test from a single class object。 For example。

 to create a class named test my module， enter class test with uppercase T in the first occurrence。

 My with uppercase M module with capital M， unit Test dot test case with T and C in uppercase。😊。



![](img/bcb0861715520176234141b6640fa014_31.png)

![](img/bcb0861715520176234141b6640fa014_32.png)

![](img/bcb0861715520176234141b6640fa014_33.png)

![](img/bcb0861715520176234141b6640fa014_34.png)

Notice how the class name has test prefixed to the unit name in the example。

 It is a good naming convention to prefix test to the class name to help distinguish between the unit class and the unit test class。

😊。

![](img/bcb0861715520176234141b6640fa014_36.png)

Next， make the class inherit the test case class of the unit Test library。For example。

 test case is the test case class of the unit Test library。

Inheriting the class allows you to leverage the existing methods in the test case class。

Then create functions in the unit testing class corresponding to each function that needs to be tested。

 For example， in the test My module class， two functions。

 test square and test Dr correspond to the square and Doppler functions in the my module unit。😊。



![](img/bcb0861715520176234141b6640fa014_38.png)

![](img/bcb0861715520176234141b6640fa014_39.png)

Note， make sure that the functions are preended with the test in the unit test module。

 because only functions that start with test are run。Finally， you can create test cases。



![](img/bcb0861715520176234141b6640fa014_41.png)

When creating the test cases， add one or more assertion methods to ensure that the unit test condition is met。



![](img/bcb0861715520176234141b6640fa014_43.png)

One assertion function is assertt equal， notice that the method has been added to the test case class in the code。



![](img/bcb0861715520176234141b6640fa014_45.png)

![](img/bcb0861715520176234141b6640fa014_46.png)

The As equal function compares two values or entities and determines that they are equal。



![](img/bcb0861715520176234141b6640fa014_48.png)

The method is used to check it functions are returning the correct values。

One of the parameters that the assert equal function takes is the actual value for the actual value。

 you will call the function that you want to test。

![](img/bcb0861715520176234141b6640fa014_50.png)

The second parameter is the expected value where you will add what the function is expected to return。

In the example， the first test is for the square function using the number two。

 which should return a value 4 if the function executes correctly。



![](img/bcb0861715520176234141b6640fa014_52.png)

As part of the test， first， the function is evaluated。

 Then the two values are compared to see if they are equal。



![](img/bcb0861715520176234141b6640fa014_54.png)

Depending on the output of the comparison， the test passes or fails。



![](img/bcb0861715520176234141b6640fa014_56.png)

After running the test file， an output is generated， the output displays the test results。

 along with some additional details。 For example， if the output displays that two tests were run in 0 seconds。



![](img/bcb0861715520176234141b6640fa014_58.png)

![](img/bcb0861715520176234141b6640fa014_59.png)

O， indicates that the test passed and the two functions were implemented correctly。



![](img/bcb0861715520176234141b6640fa014_61.png)

But what happens if the function was not implemented correctly。



![](img/bcb0861715520176234141b6640fa014_63.png)

Consider the square function where you wrote the code to calculate the cube of a number instead of square。

 The function fails， and an output is generated。😊。

![](img/bcb0861715520176234141b6640fa014_65.png)

Let's review the sample output of a failed unit test。

 The output clearly displays that the unit test failed。 For example。

 the output states failed test square main test My module with capital T and M and no spaces。

 You can also view the function where the unit test failed。 For example。

 test square self dot assert no space equal with capital E square 2。

4 indicates that the square function failed。Assertion error with initial A and E in capital letters。

8 equals 4 indicates the value mismatch。The detailed output enables you to correct a mistake before the actual deployment of your solution。

 In this video， you learn that。😊。

![](img/bcb0861715520176234141b6640fa014_67.png)

Unit testing is a method to validate if units of code are operating as designed。



![](img/bcb0861715520176234141b6640fa014_69.png)

During code development， each unit is tested。 The unit is tested in two phases。

 Once the unit passes the server test， the unit is merged into the final code base。

 Make sure that the test files are preapended or appended with the word test to clearly differentiate them from the module file。

You can use different test functions to build unit tests。

Assert equal function is a commonly used assertion method to compare two values。

You can review the unit test output and determine if the test passed or failed。


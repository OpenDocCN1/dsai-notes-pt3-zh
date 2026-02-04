# IBM应用人工智能（从0开始搭建AI机器人）｜IBM Applied AI （中英字幕） - P97：7_单元测试.zh_en - GPT中英字幕课程资源 - BV1p64y1H7LM

In this video， we will discuss unit testing。 Unit testing is a systematic and reproducible way to test your code。

 Unit testing is a method to validate if units of code are operating as designed。

 A unit is a smaller， testable part of an application， typicallyy functions and modules。 Here。

 our unit is the function square and double in the my module dot Py file。

 We will be using the unit test library， which is an installed Python module。

 providing a framework containing test functionality。



![](img/6c3ef5baf318097ffffc64f66eff3847_1.png)

![](img/6c3ef5baf318097ffffc64f66eff3847_2.png)

![](img/6c3ef5baf318097ffffc64f66eff3847_3.png)

![](img/6c3ef5baf318097ffffc64f66eff3847_4.png)

![](img/6c3ef5baf318097ffffc64f66eff3847_5.png)

![](img/6c3ef5baf318097ffffc64f66eff3847_6.png)

![](img/6c3ef5baf318097ffffc64f66eff3847_7.png)

This is the process of testing from unit testing through publishing to the production code base。



![](img/6c3ef5baf318097ffffc64f66eff3847_9.png)

During code development， each unit is tested。 If the test fails。

 the developer determines the reason and fix。 Then the unit is tested again。



![](img/6c3ef5baf318097ffffc64f66eff3847_11.png)

![](img/6c3ef5baf318097ffffc64f66eff3847_12.png)

Once the unit test passes， the unit is tested in a continuous integration。

 continuous delivery test server environment。

![](img/6c3ef5baf318097ffffc64f66eff3847_14.png)

![](img/6c3ef5baf318097ffffc64f66eff3847_15.png)

If the unit fails the server test， the code is returned to the developer to determine the reason and fix。



![](img/6c3ef5baf318097ffffc64f66eff3847_17.png)

And the process restarts。

![](img/6c3ef5baf318097ffffc64f66eff3847_19.png)

Once the unit passes the server test， the unit is merged into the final main code base。



![](img/6c3ef5baf318097ffffc64f66eff3847_21.png)

Let us take a look at the test functions file and see how we can build our tests。



![](img/6c3ef5baf318097ffffc64f66eff3847_23.png)

First， notice that the name of the file has test appended or prepened to identify it as a unit testing file。

 this is a good naming convention。

![](img/6c3ef5baf318097ffffc64f66eff3847_25.png)

Next， we import the unit Test library。Then we import the functions we want to test。



![](img/6c3ef5baf318097ffffc64f66eff3847_27.png)

Now we can build our unit testing class First we create a test class。

 it is a good naming convention to name the file you are testing and prepen test for the class name。



![](img/6c3ef5baf318097ffffc64f66eff3847_29.png)

![](img/6c3ef5baf318097ffffc64f66eff3847_30.png)

Next we make the class inherit the test case class of the unit Test library。

 this allows our class to use methods in the test case class。



![](img/6c3ef5baf318097ffffc64f66eff3847_32.png)

![](img/6c3ef5baf318097ffffc64f66eff3847_33.png)

Now we create a function in the test My module class for each function we want to test。

 We name the functions by prepending test to the function we want to test。

 note that this step is mandatory as only functions that start with test are run。



![](img/6c3ef5baf318097ffffc64f66eff3847_35.png)

![](img/6c3ef5baf318097ffffc64f66eff3847_36.png)

![](img/6c3ef5baf318097ffffc64f66eff3847_37.png)

Finally， we can start creating test cases。This is done by using the Ast equalqu function to run our test cases when the file is run。

 we add this block。

![](img/6c3ef5baf318097ffffc64f66eff3847_39.png)

![](img/6c3ef5baf318097ffffc64f66eff3847_40.png)

Let us look closer at the assert equal used in the test class。



![](img/6c3ef5baf318097ffffc64f66eff3847_42.png)

Aert equal compares two values and determines if they are equal。

 This is used to check if functions are returning the correct values for the actual value。

 we call the function we are testing and for the expected value。

 we put what the function is expected to return。

![](img/6c3ef5baf318097ffffc64f66eff3847_44.png)

![](img/6c3ef5baf318097ffffc64f66eff3847_45.png)

![](img/6c3ef5baf318097ffffc64f66eff3847_46.png)

In the first test， we are testing the square function using the number two。

 which should return a4 if the function operates correctly。



![](img/6c3ef5baf318097ffffc64f66eff3847_48.png)

First， the function is evaluated。

![](img/6c3ef5baf318097ffffc64f66eff3847_50.png)

Then the two values are compared to see if they are equal。After running our test file。

 we will get an output like this。 The two functions were implemented correctly。



![](img/6c3ef5baf318097ffffc64f66eff3847_52.png)

![](img/6c3ef5baf318097ffffc64f66eff3847_53.png)

But what happens if our function was not implemented correctly？

 Consider the following functions where square is incorrectly implemented as it cubes a number Instead of squaring it。

 The evaluation of the assert equal would look like this， resulting in a fail。

 The output of the test file would look like this。

![](img/6c3ef5baf318097ffffc64f66eff3847_55.png)

![](img/6c3ef5baf318097ffffc64f66eff3847_56.png)

![](img/6c3ef5baf318097ffffc64f66eff3847_57.png)

![](img/6c3ef5baf318097ffffc64f66eff3847_58.png)

We can easily see the function that failed a unit test。

 and we can see the assert equal failed and what the function evaluated to。


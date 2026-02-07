# IBM应用人工智能（从0开始搭建AI机器人）｜IBM Applied AI （中英字幕） - P96：6_打包.zh_en - GPT中英字幕课程资源 - BV1p64y1H7LM

![](img/9d798d535d72184a6afde660cd860bdd_0.png)

Welcome to Packaging After watching this video， you will be able to differentiate between Python module。

 package and library。😊。

![](img/9d798d535d72184a6afde660cd860bdd_2.png)

![](img/9d798d535d72184a6afde660cd860bdd_3.png)

Create a Python package， verify a Python package， and use a Python package。



![](img/9d798d535d72184a6afde660cd860bdd_5.png)

Modules， packages and libraries are frequently used terms in Python。

 Let's look at each of the terms in detail。😊。

![](img/9d798d535d72184a6afde660cd860bdd_7.png)

![](img/9d798d535d72184a6afde660cd860bdd_8.png)

A Python module is a dot Py file containing Python definitions， statements， functions and classes。



![](img/9d798d535d72184a6afde660cd860bdd_10.png)

You can import a module to other scripts and notebooks， for example。

 consider a module named moduleule dot Pi that has two functions。



![](img/9d798d535d72184a6afde660cd860bdd_12.png)

The first function is depth square open round bracket number， close round bracket， colon。

 returnturn number asterisk asterisk 2， which squares the input and returns the result as an output。

The second function is Death doubleubr open round bracket， number close round bracket colon。

 return number asterisk 2， which doubles the input and returns the result as an output。

If the function is in the same directory， you can import it and use the functions in that module。

Let's consider using the square function with print command。Print open round bracket。

 double quotes4 carrot symbol2， double quotes， comma square open round bracket。

 four close round bracket， close round bracket。The output is displayed as4 carroatt simple 2 equals 16。

Similarly， for the print Dor function with value 4， the output is 2 asterisk4 equals 8。

A package is a collection of Python modules into a dictionary with an underscore underscore in it underscore underscore dot Pi file。

 which distinguishes it from just a dictionary of Python scripts。



![](img/9d798d535d72184a6afde660cd860bdd_14.png)

![](img/9d798d535d72184a6afde660cd860bdd_15.png)

The example shows the package my project in parent directory with two modules。

 moduleule 1 dot pi and Moule 2 dot pi。

![](img/9d798d535d72184a6afde660cd860bdd_17.png)

![](img/9d798d535d72184a6afde660cd860bdd_18.png)

It also contains the underscore underscore in it， underscore underscore dot P file。



![](img/9d798d535d72184a6afde660cd860bdd_20.png)

When you import a module or a package， the corresponding object created by Python is always of type module。



![](img/9d798d535d72184a6afde660cd860bdd_22.png)

Note that the distinction between module and package is only at the file system level。



![](img/9d798d535d72184a6afde660cd860bdd_24.png)

A library is a collection of packages， or it can be a single package。



![](img/9d798d535d72184a6afde660cd860bdd_26.png)

Examples include nue， pie torch， and pandas。

![](img/9d798d535d72184a6afde660cd860bdd_28.png)

Note that the terms package and library are often used interchangeably。 Therefore。

 nuy pietorrch and pandas are also referred to as packages。



![](img/9d798d535d72184a6afde660cd860bdd_30.png)

![](img/9d798d535d72184a6afde660cd860bdd_31.png)

Let's look at the steps to create a Python package。



![](img/9d798d535d72184a6afde660cd860bdd_33.png)

Consider there are two modules。 Module 1 dot pi has two functions。

 Square and Dubr Moule 2 dot pi has one function。 mean to make my project folder into a package。

 you must have underscore underscore in it underscore underscore dot pi as a file in the my project folder。

 The contents of the underscore underscore in it， underscore underscore dot pi file must be from dot import module 1 and from dot import module 2。

😊。

![](img/9d798d535d72184a6afde660cd860bdd_35.png)

![](img/9d798d535d72184a6afde660cd860bdd_36.png)

![](img/9d798d535d72184a6afde660cd860bdd_37.png)

![](img/9d798d535d72184a6afde660cd860bdd_38.png)

Typical steps to create a package include。First， create a folder with the package name。

 Then create an empty underscore underscore in it， underscore underscore dot pi file。

 create the required modules。 Finally， in the underscore underscore init。

 underscore underscore dot pi file。 Add code to reference the modules needed in the package After creating the package。

 you need to verify the package。 to verify the package。 First， open a bash terminal。

 make sure the directory is the same as the folder where your package is located。😊。



![](img/9d798d535d72184a6afde660cd860bdd_40.png)

![](img/9d798d535d72184a6afde660cd860bdd_41.png)

![](img/9d798d535d72184a6afde660cd860bdd_42.png)

Open the Python interpreter by running the command Python in the shell。



![](img/9d798d535d72184a6afde660cd860bdd_44.png)

Using the Python prompt， type import followed by project name， for example， importmport My project。

 if the command runs without errors， it is an indication that the package is successfully loaded。



![](img/9d798d535d72184a6afde660cd860bdd_46.png)

![](img/9d798d535d72184a6afde660cd860bdd_47.png)

The general structure for testing your package is the package name， dot module name。

 dot function name， followed by the parameters without the curly brackets。

 but keeping the round brackets， for example， using my project， my project dot basic dot square。

 open round bracket2 close round bracket， the function will return the value 4。😊。



![](img/9d798d535d72184a6afde660cd860bdd_49.png)

![](img/9d798d535d72184a6afde660cd860bdd_50.png)

![](img/9d798d535d72184a6afde660cd860bdd_51.png)

After creating the package， you can use it in the other scripts if the package folder is in the same directory。



![](img/9d798d535d72184a6afde660cd860bdd_53.png)

In this case， you have the file Test。 Pi in the parent directory。

You can import the functions in the package， for example。

 using the Python code from my project moduleule 1。

 import square comma doubleubr from my project moduleule 2， import mean print open round bracket。

 double quotes4 carrot symbol2 equals doubles comma square round bracket，4 close round bracket。

 close round bracket， print open round bracket2 asterisk 4 equals double quotea doubler open round bracket。

4 close round bracket， close round bracket， print open bracket double quote open round bracket 2 plus1 plus3。

 close round bracket， divided by three equals double comma mean open round bracket。

 open square bracket，2 comma1 comma 3 close square bracket， close round bracket， close round bracket。

😊，You can then run the functions and check if you get the correct results。In this video。

 you learn that a Python module is a Dot P file containing Python definitions， statements， functions。

 and classes。

![](img/9d798d535d72184a6afde660cd860bdd_55.png)

A package is a collection of Python modules into a dictionary with an underscore underscore in it。

 underscore underscore。P file。

![](img/9d798d535d72184a6afde660cd860bdd_57.png)

A library is a collection of packages， or it can be a single package。To create a package。

 create a folder with the package name， create an empty underscore underscore in it，_ underscore。

t Pfi。Create the required modules in the underscore underscore in it。

 underscore underscore dot P file， add code to reference the modules needed in the package。

You can verify the package via the bash terminal After creating the package。

 you can use it on other scripts if the package folder is in the same directory。😊。



![](img/9d798d535d72184a6afde660cd860bdd_59.png)
# IBM《生成式人工智能工程｜Falsk、生成式AI应用、数据分析、机器学习、Keras、架构和数据、NLP基础、transformer、微调、高级微调、RAG》 p05 4_Python风格指南和编码实践.zh_en -BV1NAq6Y9E7z_p5-

Welcome to Python Style Guide and Coding Practices。



![](img/8107f17e56cf79de54eeede2eebf2e0c_1.png)

After watching this video， you'll be able to describe the importance of writing readable code。

 list the Python coding conventions， explain static code analysis。



![](img/8107f17e56cf79de54eeede2eebf2e0c_3.png)

![](img/8107f17e56cf79de54eeede2eebf2e0c_4.png)

When you write code， you need to ensure the team can read and understand it easily。

 This task requires some coding standards and conventions。Python。

org has released a document called Python Enhancement Proposal 8 or PEP8 that provides conventions and guidelines to make your Python code readable and consistently formatted。

Let's start with the key guidelines for improving the readability of the code。

PEep 8 recommends the use of spaces instead of tabs for indentation。

Wondering why different text editors and integrated development environments or IDEs interpret the number of spaces in a tab differently；

 for example， one editor might interpret a tab as three spaces。

 while another might interpret it as four。Using a tap or indentation can lead to non uniformity in code。

 resulting in formatting errors。 For example， observe the spacing difference when tab is pressed for statement 1 for the if condition under editor 1。

 when compared with the space before statement 1， for the if condition under editor 2。

To avoid such errors， you should use a consistent number of spaces when indenting your code。



![](img/8107f17e56cf79de54eeede2eebf2e0c_6.png)

For uniformity， the guideline is to use four spaces for every indentation level in a code；

 four spaces for an indentation are sufficient for appropriate readability。

Please note that the four dots have been added before State 1 and State 2 to depict four spaces。



![](img/8107f17e56cf79de54eeede2eebf2e0c_8.png)

PEP 8 also recommends using blank lines to separate functions and classes in the code。

Notice that in the left block， which does not follow PEEP8 guidelines。

 there is no space between where function 1 ends and class user class， capital U and capital C。

 no space。However， the right side shows the correct representation with a space before the class definition。

The blank lines help establish the beginning and end of different parts of the code。



![](img/8107f17e56cf79de54eeede2eebf2e0c_10.png)

To improve code readability， use spaces around operators and after commas。

 using spaces will make the commands look spacious and discet， improving command readability。

Let's look at some examples。When you write A equals B plus C without any spaces， it can be confusing。

 However， when you add the spaces， for example， A space equals space， B， space plus space C。

 readability improves。Next， let's look at some coding conventions to maintain consistency and re manageageability。

 A key coding convention is to create separate functions for functionalities with larger blocks of code。

 You can then call the functions from the main program。 For example， in the code。

 the if else syntax does not have a function and will need to be written every time you need the functionality。

 However， if you notice function underscore1 written as depth function underscore1 with two parameters A and B。

 it can be called easily。😊，For example， C equals function underscore 1 Open round bracket A。

 comma B close round bracket， This increases the execution speed of the code and supports the reuse of the code block in a much more convenient way。



![](img/8107f17e56cf79de54eeede2eebf2e0c_12.png)

Another coding convention is to name the functions and files using lowercase with underscores。

 wondering why Python uses the naming convention and has many built in libraries and predefined functions that use the common naming conventions。

 therefore， using a lowercase function name preferably with underscores is advisable to make the functions unique。

For example， instead of writing function name as comp surface with capital S radiation with capital R。

 open round bracket close round bracket， write， comp underscore surface underscore radiation， open。

 round bracket， close round bracket， an exception to the rule is the naming criteria for Python packages。

 where underscores are generally discouraged， for example， instead of writing My underscore package。

 write My package。

![](img/8107f17e56cf79de54eeede2eebf2e0c_14.png)

Naming the classes using Caml case is also a coding convention。

Camel case or the CA Word case is a naming convention for classes that is well accepted in the coding community。

CamelC also helps distinguish between classes and functions in the code。For example。

 instead of writing class La_ Sirrel underscore C， the best practice is to name the class as Lamb SirrelC with the initial LS and C in capital letters。

Use the coding convention of capitalizing all words and separating them with underscores for consistency。

The name usually indicates the constant's purpose， for example。

 Max file upload size in capital letters we discuss the coding convention and guidelines。

 software developers commonly use static code analysis to manage compliance with these style guidelines。

Static code analysis is a method to evaluate code against a predefined style and standard without executing the code。

Statatic analysis helps find issues such as programming errors， coding standard violations。

 undefined values， syntax violations， and security vulnerabilities。

You can use the Pland library to check the compliance of your Python code with PEP8 guidelines。



![](img/8107f17e56cf79de54eeede2eebf2e0c_16.png)

In this video， you learn that writing consistent code helps all team members read and understand the code easily。

The PEP 8 guidelines for better code readability include the following， four spaces for indentation。

 use blank lines to separate functions in classes， and use spaces around operators and after commas。

Some coding conventions for code consistency and manageability include。

Add larger blocks of code inside functions。 Na functions and files using lowercase with underscores。

 name classes using Caml case and name constants in all capital letters with underscores separating words。

😊，Use static code analysis method to evaluate your code against a predefined style and standard without executing the code。



![](img/8107f17e56cf79de54eeede2eebf2e0c_18.png)

![](img/8107f17e56cf79de54eeede2eebf2e0c_19.png)
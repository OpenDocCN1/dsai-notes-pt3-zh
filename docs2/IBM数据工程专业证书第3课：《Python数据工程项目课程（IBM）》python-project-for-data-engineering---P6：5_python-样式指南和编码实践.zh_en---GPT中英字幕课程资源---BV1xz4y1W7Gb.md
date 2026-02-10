# IBM数据工程专业证书第3课：《Python数据工程项目课程（IBM）》python-project-for-data-engineering - P6：5_python 样式指南和编码实践.zh_en - GPT中英字幕课程资源 - BV1xz4y1W7Gb

![](img/3229a2ab7bdbc020d7a161a3392cb8bf_0.png)

Welcome to Python Style Guide and Coing Practices。

![](img/3229a2ab7bdbc020d7a161a3392cb8bf_2.png)

After watching this video， you'll be able to describe the importance of writing readable code。

 list the Python coding conventions， explain static code analysis。



![](img/3229a2ab7bdbc020d7a161a3392cb8bf_4.png)

![](img/3229a2ab7bdbc020d7a161a3392cb8bf_5.png)

When you write code， you need to ensure the team can read and understand it easily。

 This task requires some coding standards and conventions。



![](img/3229a2ab7bdbc020d7a161a3392cb8bf_7.png)

![](img/3229a2ab7bdbc020d7a161a3392cb8bf_8.png)

Python。org has released a document called Python Enhancement Proposal 8 or PEP8 that provides conventions and guidelines to make your Python code readable and consistently formatted。



![](img/3229a2ab7bdbc020d7a161a3392cb8bf_10.png)

![](img/3229a2ab7bdbc020d7a161a3392cb8bf_11.png)

Let's start with the key guidelines for improving the readability of the code。



![](img/3229a2ab7bdbc020d7a161a3392cb8bf_13.png)

PEep 8 recommends the use of spaces instead of tabs for indentation。



![](img/3229a2ab7bdbc020d7a161a3392cb8bf_15.png)

Wondering why different text editors and integrated development environments or IDEs interpret the number of spaces in a tab differently；

 For example， one editor might interpret a tab as three spaces。

 while another might interpret it as four。

![](img/3229a2ab7bdbc020d7a161a3392cb8bf_17.png)

![](img/3229a2ab7bdbc020d7a161a3392cb8bf_18.png)

![](img/3229a2ab7bdbc020d7a161a3392cb8bf_19.png)

Using a tap or indentation can lead to non uniformity in code， resulting in formatting errors。

 For example， observe the spacing difference when tab is pressed for statement 1 for the if condition under editor 1。

 when compared with the space before statement 1 for the if condition under editor 2。

To avoid such errors， you should use a consistent number of spaces when indenting your code。

For uniformity， the guideline is to use four spaces for every indentation level in a code；

 four spaces for an indentation are sufficient for appropriate readability。



![](img/3229a2ab7bdbc020d7a161a3392cb8bf_21.png)

![](img/3229a2ab7bdbc020d7a161a3392cb8bf_22.png)

Please note that the four dots have been added before statement 1 and statement 2 to depict four spaces。



![](img/3229a2ab7bdbc020d7a161a3392cb8bf_24.png)

PEP 8 also recommends using blank lines to separate functions and classes in the code。

Notice that in the left block， which does not follow PEEP8 guidelines。

 there is no space between where function 1 ends and class user class， capital U and capital C。

 no space。

![](img/3229a2ab7bdbc020d7a161a3392cb8bf_26.png)

However， the right side shows the correct representation with a space before the class definition。



![](img/3229a2ab7bdbc020d7a161a3392cb8bf_28.png)

The blank lines help establish the beginning and end of different parts of the code。

To improve code readability， use spaces around operators and after commas。

 using spaces will make the commands look spacious and discet， improving command readability。😊。



![](img/3229a2ab7bdbc020d7a161a3392cb8bf_30.png)

![](img/3229a2ab7bdbc020d7a161a3392cb8bf_31.png)

Let's look at some examples。When you write A equals B plus C without any spaces， it can be confusing。

 However， when you add the spaces， for example， A space equals space， B， space plus space C。

 readability improves。

![](img/3229a2ab7bdbc020d7a161a3392cb8bf_33.png)

![](img/3229a2ab7bdbc020d7a161a3392cb8bf_34.png)

Next， let's look at some coding conventions to maintain consistency and manageability。

 A key coding convention is to create separate functions for functionalities with larger blocks of code。

 you can then call the functions from the main program。 For example， in the code。

 The if else syntax does not have a function and will need to be written every time you need the functionality。

 However， if you notice function underscore1 written as depth function underscore1 with two parameters A and B。

 it can be called easily。😊。

![](img/3229a2ab7bdbc020d7a161a3392cb8bf_36.png)

![](img/3229a2ab7bdbc020d7a161a3392cb8bf_37.png)

![](img/3229a2ab7bdbc020d7a161a3392cb8bf_38.png)

![](img/3229a2ab7bdbc020d7a161a3392cb8bf_39.png)

For example， C equals function underscore 1 Open round bracket A， comma B close round bracket。

 This increases the execution speed of the code and supports the reuse of the code block in a much more convenient way。



![](img/3229a2ab7bdbc020d7a161a3392cb8bf_41.png)

![](img/3229a2ab7bdbc020d7a161a3392cb8bf_42.png)

Another coding convention is to name the functions and files using lowercase with underscores。

 wondering why。

![](img/3229a2ab7bdbc020d7a161a3392cb8bf_44.png)

![](img/3229a2ab7bdbc020d7a161a3392cb8bf_45.png)

Python uses the naming convention and has many built in libraries and predefined functions that use the common naming conventions。



![](img/3229a2ab7bdbc020d7a161a3392cb8bf_47.png)

Therefore， using a lower case function name preferably with underscores is advisable to make the functions unique。



![](img/3229a2ab7bdbc020d7a161a3392cb8bf_49.png)

For example， instead of writing function name as comp surface with capital S。

 radiation with capital R， open round bracket close round bracket， write。

 comp underscore surface underscore， radiation， open， round bracket， close round bracket。

 an exception to the rule is the naming criteria for Python packages。

 where underscores are generally discouraged， for example， instead of writing my underscore package。

 write my package。

![](img/3229a2ab7bdbc020d7a161a3392cb8bf_51.png)

![](img/3229a2ab7bdbc020d7a161a3392cb8bf_52.png)

![](img/3229a2ab7bdbc020d7a161a3392cb8bf_53.png)

![](img/3229a2ab7bdbc020d7a161a3392cb8bf_54.png)

![](img/3229a2ab7bdbc020d7a161a3392cb8bf_55.png)

Naming the classes using Caml case is also a coding convention。



![](img/3229a2ab7bdbc020d7a161a3392cb8bf_57.png)

Camel case or the CA Word case is a naming convention for classes that is well accepted in the coding community。



![](img/3229a2ab7bdbc020d7a161a3392cb8bf_59.png)

CamelC also helps distinguish between classes and functions in the code。



![](img/3229a2ab7bdbc020d7a161a3392cb8bf_61.png)

For example， instead of writing class La_ Sirrel underscore C。

 the best practice is to name the class as Lamb Sirrel C with the initial LS and C in capital letters。



![](img/3229a2ab7bdbc020d7a161a3392cb8bf_63.png)

![](img/3229a2ab7bdbc020d7a161a3392cb8bf_64.png)

Use the coding convention of capitalizing all words and separating them with underscores for consistency。



![](img/3229a2ab7bdbc020d7a161a3392cb8bf_66.png)

The name usually indicates the constant's purpose， for example。

 Max file upload size in capital letters we discuss the coding convention and guidelines。

 software developers commonly use static code analysis to manage compliance with these style guidelines。



![](img/3229a2ab7bdbc020d7a161a3392cb8bf_68.png)

![](img/3229a2ab7bdbc020d7a161a3392cb8bf_69.png)

![](img/3229a2ab7bdbc020d7a161a3392cb8bf_70.png)

Static code analysis is a method to evaluate code against a predefined style and standard without executing the code。



![](img/3229a2ab7bdbc020d7a161a3392cb8bf_72.png)

Statatic analysis helps find issues such as programming errors， coding standard violations。

 undefined values， syntax violations， and security vulnerabilities。



![](img/3229a2ab7bdbc020d7a161a3392cb8bf_74.png)

You can use the Pland library to check the compliance of your Python code with PEP8 guidelines。

In this video， you learn that writing consistent code helps all team members read and understand the code easily。



![](img/3229a2ab7bdbc020d7a161a3392cb8bf_76.png)

The PEP 8 guidelines for better code readability include the following， four spaces for indentation。

 use blank lines to separate functions in classes， and use spaces around operators and after commas。



![](img/3229a2ab7bdbc020d7a161a3392cb8bf_78.png)

Some coding conventions for code consistency and manageability include。

Add larger blocks of code inside functions， Na functions and files using lowercase with underscores。

 name classes using Caml case and name constants in all capital letters with underscores separating words。

😊，Use static code analysis method to evaluate your code against a predefined style and standard without executing the code。



![](img/3229a2ab7bdbc020d7a161a3392cb8bf_80.png)
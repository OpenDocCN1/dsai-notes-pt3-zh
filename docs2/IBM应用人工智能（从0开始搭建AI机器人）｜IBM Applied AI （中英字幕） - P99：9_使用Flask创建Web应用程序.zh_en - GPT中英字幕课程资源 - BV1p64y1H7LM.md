# IBM应用人工智能（从0开始搭建AI机器人）｜IBM Applied AI （中英字幕） - P99：9_使用Flask创建Web应用程序.zh_en - GPT中英字幕课程资源 - BV1p64y1H7LM

![](img/dd95a412911bb50ce266649daeb5fd9f_0.png)

![](img/dd95a412911bb50ce266649daeb5fd9f_1.png)

In this video， you will learn about the flask micro frameworkramework。



![](img/dd95a412911bb50ce266649daeb5fd9f_3.png)

After watching this video， you will be able to describe what a framework is and list popular Python frameworks。

 create Python web applications using Flask microcroframemework。

 connect to the endpoints in the web application through a browser and pass parameters to the endpoints that you connect to。

In Python， a framework is a collection of packages or modules which are developed and made available for a specific purpose。

 while there are many Python frameworks， the most commonly used Python frameworks include flask。

 Django， Dash tornado， web2i， etc Microframeme is a minimalistic web application framework while you can create a bare minimum web application。

 they depend on the other packages to have additional functionalities。

 Flask is an open source extensible microframe written in Python。



![](img/dd95a412911bb50ce266649daeb5fd9f_5.png)

![](img/dd95a412911bb50ce266649daeb5fd9f_6.png)

![](img/dd95a412911bb50ce266649daeb5fd9f_7.png)

![](img/dd95a412911bb50ce266649daeb5fd9f_8.png)

Let us look at flask a bit more in detail。 Flask， as we saw earlier。

 is a micro framework for creating a web application quickly and easily with Python。

 Flask is based on workszoig and Ginja 2 Workzoig is a web server gateway interface toolkit。

 which implements request response and other web utility functions and enables building a web framework on top of it。

 Gingja 2 is a templating engine for Python， which helps render dynamic web pages。

 Flask supports crud， which is create， read， update and delete requests by allowing us to make post。

 put， get， update and delete requests。 Flask canserve static files。

 The flask application is set up to look inside a static folder for Hms， CsS and JS assets。

 Flask web application is extensible。 though flask by itself is a microframe。 It is extensible。

 meaning there are。😊。

![](img/dd95a412911bb50ce266649daeb5fd9f_10.png)

![](img/dd95a412911bb50ce266649daeb5fd9f_11.png)

![](img/dd95a412911bb50ce266649daeb5fd9f_12.png)

Hackages that can be used with flask for other features like user authentication， data storage， etc。

 Don't worry if you are not familiar with all the terms we just mentioned。

 they will become clear as we proceed。What you are seeing on the screen is the basic structure of a flask application。

 This is the logo of the flask package。 As we saw earlier。

 flask web applications can be used for crud operations， but for better understanding。

 let us take an example of a user management web application。



![](img/dd95a412911bb50ce266649daeb5fd9f_14.png)

![](img/dd95a412911bb50ce266649daeb5fd9f_15.png)

Post and put requests are used for creating objects or data In our user management application example。

 you usePo or put to create a new user The difference between the two is that post creates on every request whereas put creates on the first request and thereafter updates it in most web applications you will see post being used for creation。



![](img/dd95a412911bb50ce266649daeb5fd9f_17.png)

![](img/dd95a412911bb50ce266649daeb5fd9f_18.png)

Get requests are used for reading the data from the server in the user management example。

 we will use the get request to read user information。

 Update requests are used to update the existing data or objects。

 Dete requests are used to delete the existing data or objects。

 Most web applications tend to use post for creation。

 update and deletion and use get for read Flask API end points can be created to return responses in the form of string J Hm error object。

 etc cetera， along with a response status code In order to create a web application with flask。

 we need to first install the flask package using Pip。

 the standard package manager for Python like all other packages， we can use the command。

 Pip install flask， which will get the most current version of flask。 Once it is installed。

 we are all set to create the web application。 We can now import flask。



![](img/dd95a412911bb50ce266649daeb5fd9f_20.png)

![](img/dd95a412911bb50ce266649daeb5fd9f_21.png)

![](img/dd95a412911bb50ce266649daeb5fd9f_22.png)

![](img/dd95a412911bb50ce266649daeb5fd9f_23.png)

![](img/dd95a412911bb50ce266649daeb5fd9f_24.png)

![](img/dd95a412911bb50ce266649daeb5fd9f_25.png)

Instiate flask class， create a web application， then run the application。



![](img/dd95a412911bb50ce266649daeb5fd9f_27.png)

We will look at a sample Web application that serves the root API endpoint as a get request and returns Hello world string as a response Before we create this application。

 as we saw earlier， we need to install flask。 As you see on line one。

 we import the flask module from the flask package。

 We create an object of the flask class as a web application with the name。

 My first application and store it as an app。 app is just a reference name and can be anything。

 But most applications use the reference name app for clarity purpose。

 we then define the route and the method that will be invoked when this route is accessed。

 You can see that we have not specified whether it is a get or a post。 When we specifying nothing。

 It is by default， get and this endpoint will now be able to serve get requests to the root。

 Hello is the method which will be invoked when the API endpoint。 we just defined。😊。



![](img/dd95a412911bb50ce266649daeb5fd9f_29.png)

![](img/dd95a412911bb50ce266649daeb5fd9f_30.png)

![](img/dd95a412911bb50ce266649daeb5fd9f_31.png)

![](img/dd95a412911bb50ce266649daeb5fd9f_32.png)

![](img/dd95a412911bb50ce266649daeb5fd9f_33.png)

![](img/dd95a412911bb50ce266649daeb5fd9f_34.png)

Acced It takes no parameters and returns the string Hello world。 Finally。

 if name attribute is set to main， we run the web application by default。

 name is set to main unless it is explicitly changed and we can save and run this like any other Python application。



![](img/dd95a412911bb50ce266649daeb5fd9f_36.png)

![](img/dd95a412911bb50ce266649daeb5fd9f_37.png)

![](img/dd95a412911bb50ce266649daeb5fd9f_38.png)

To start the server in development environment， we simply save the code in a Python file and run it like we run any other Python application When the web application server starts。

 it gives you the IP address and the port the application can be accessed from to check the endpoints we can open the browser and connect to this endpoint you see in the server output 127。

0。0。1 at port 5000 and see stringingHello world being returned from the web server application。



![](img/dd95a412911bb50ce266649daeb5fd9f_40.png)

![](img/dd95a412911bb50ce266649daeb5fd9f_41.png)

![](img/dd95a412911bb50ce266649daeb5fd9f_42.png)

![](img/dd95a412911bb50ce266649daeb5fd9f_43.png)

Templates are nothing but precreated HTML pages that are served from the web application。

 They can be both static and dynamic By default， the flask application looks for the templates in a directory called templates under the root directory If these templates need to use images style sheets or JavaScriptscript files。

 Those are stored in a folder named static in the root directory。

 The static pages are rendered as is The dynamic pages usually have information that is filled in dynamically for each request。

 Often these are based on the values passed as arguments。

 The arguments can either be passed through the URL or be passed as request parameters。



![](img/dd95a412911bb50ce266649daeb5fd9f_45.png)

Let us look at a sample flask application， we start with importing flask to create a web application request to handle the incoming request and render template for rendering static and dynamic HTML。



![](img/dd95a412911bb50ce266649daeb5fd9f_47.png)

Next， we instantiate flask and set the static folder by default， the folder name is static。

 but you can have static contents in a directory with a different name as long as you set it explicitly。

 We have defined three end points in this web application。 The first is slash sample。

 This will render a static h page and the image in this HTML is sourced from the static directory。

 The next one is slash user slash username where the username that you see within angle brackets is the parameter。

 You see the method has been explicitly set to get。

 This is just to show how you can set the type of request。 If nothing is specified。

 it is considered as a get request。 The page is rendered with the parameter we passed in the URL。

 and the last one is slash user where username is passed as request parameter。

 The page is rendered with the parameter we passed in as request。



![](img/dd95a412911bb50ce266649daeb5fd9f_49.png)

![](img/dd95a412911bb50ce266649daeb5fd9f_50.png)

![](img/dd95a412911bb50ce266649daeb5fd9f_51.png)

![](img/dd95a412911bb50ce266649daeb5fd9f_52.png)

![](img/dd95a412911bb50ce266649daeb5fd9f_53.png)

You will see this in the lab session。

![](img/dd95a412911bb50ce266649daeb5fd9f_55.png)

In this video， you learned application frameworks automate the common tasks associated with building applications。

 Flask microcro frameworkmework can be used to create web applications。

 and popular Python application frameworks include Django， Flask， tornado and Web2 Pi。



![](img/dd95a412911bb50ce266649daeb5fd9f_57.png)

![](img/dd95a412911bb50ce266649daeb5fd9f_58.png)
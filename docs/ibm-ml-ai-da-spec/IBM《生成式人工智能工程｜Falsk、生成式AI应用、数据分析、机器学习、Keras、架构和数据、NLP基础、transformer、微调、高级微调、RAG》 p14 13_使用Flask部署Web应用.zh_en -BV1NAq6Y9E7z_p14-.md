# IBM《生成式人工智能工程｜Falsk、生成式AI应用、数据分析、机器学习、Keras、架构和数据、NLP基础、transformer、微调、高级微调、RAG》 p14 13_使用Flask部署Web应用.zh_en -BV1NAq6Y9E7z_p14-

。Welcome to deployying Web apps using Flask。 After watching this video。

 you will be able to describe flask features， install Flask。

 create and deploy a Python web app using Flask。😊。

![](img/efb040b83f4c19fb03b7c4a4bf6941ab_1.png)

![](img/efb040b83f4c19fb03b7c4a4bf6941ab_2.png)

Bask is a micro framework for creating web applications quickly and easily with Python。

FLask supports cruUd， which is nothing but create， read， update， and delete requests by making post。

 put， get， update and delete requests。

![](img/efb040b83f4c19fb03b7c4a4bf6941ab_4.png)

Here is the basic structure of a flask application。 Notice the logo of the flask package。

Let's look at how you can use flask for crud operations。

Post and put requests are used for creating objects or data。 For example。

 you can use post and put request to create a user。

 The difference between the two is that post creates the object or data on every request。

 While put creates the object or data only on the first request and continues to update the object or data in consecutive request。

In most web applications， you will see posts being used for creating objects or data。

You can use the get request to read data from the server。

You can use updated requests to update the existing data or objects。

You can use De requests to delete the existing data or objects。Note。

 most web applications tend to use posts for creating。

 updating and deleting objects and data and get for reading。😊，Another video explains the post。

 put and get requests in detail。 Next， let's look at how to create a web application with flask。😊。



![](img/efb040b83f4c19fb03b7c4a4bf6941ab_6.png)

The first step is to install the flask package using Pip， the standard package manager for Python。

Like all other packages， you can use the command Pip install flask。

 which will get the most current version of flask。The flask package is installed。

 and you are all set to create the web application。Next， import the flask package。

 instantiate flask class， create a web application。

 and then run the application for the purposes of demonstration。

 Let's look at the web application that returns hellello world string as a response to a get request。

 step 1， install flask。 step 2， Im the flask module from the flask package to do this type from flask with lowercase F importm flask with capital F。

😊，Step 3， create an object of the flask class as a web application with the name。

 My first web application， and store it as app。 For example。

 app equal to flask with capital F Open round bracket。

 double quotes my with capital M first application double quotes close round bracket。😊。

Most applications use the reference name app for clarity purposes。 however。

 app is just a reference name and you can use any other name。Step 4。

 define the route and the method that will be invoked when this route is accessed。 For example。

 enter at app dot root， open round bracket， single s single quote， close round bracket。

Notice in this example， neither get nor post have been specified。

When you do not specify a request by default， get as requested。Therefore， in the example。

 the endpoint will now be able to serve get requests to the route。Step 5。

 Ho is the method written as deaf。 Ho， open round bracket， close round bracket colon。

The Hlo method will be invoked when the system accesses the API endpoint that was defined in the previous step。

The code to do this is app dot run open round bracket debug。

It takes no parameters and returns the string， Hello world。In the code。

 this is written as return single quote， hello world exclamation sign quote。Step 6。

 add a condition that web application should run only if underscore， underscore name， underscore。

 underscore attribute is set to underscore， underscore， main， underscore underscore。By default。

 underscore， underscore name， underscore， underscore is set to underscore， underscore main。

 underscore， underscore unless it is explicitly changed。

You can save and run this like any other Python application。

Type app dot run Open round bracket debug equals true with capital T， close round bracket。



![](img/efb040b83f4c19fb03b7c4a4bf6941ab_8.png)

To start the server in a development environment， you need to save the code in a Python file and run it like any other Python application。

When the Web application server starts， it gives you the IP address and the port the application can be accessed from。

To check the endpoints， you can open the browser and connect to this endpoint you see in the server output。

 127。0。0。1。

![](img/efb040b83f4c19fb03b7c4a4bf6941ab_10.png)

At port 5000 and see the string Ho world being returned from the Web server application。

 Templates are nothing but prereated H pages that are served from the Web application。



![](img/efb040b83f4c19fb03b7c4a4bf6941ab_12.png)

They can be both static and dynamic。By default， the flask application looks for the templates in a directory called templates under the root directory。

 If the templates need to use images， Styling sheets or javascript files。

 which are stored in a folder named static in the root directory。

 The static pages are rendered as is。The dynamic pages usually have information that is filled in dynamically for each request。

 These pages are often based on the values passed as arguments。

The arguments can either be passed through the URL or be passed as request parameters。

 Let's look at a sample flask application。

![](img/efb040b83f4c19fb03b7c4a4bf6941ab_14.png)

You start with importing flask to create web application request to handle the incoming request and render underscore template for rendering static and dynamic HTML pages。

Type from Flask F lowercase， import flask with capital S comma， render， underscore T comma request。

Next， instantiate flask and set the static folder。 For example。

 app equals flask open round bracket double quote my with capital M first。

 application with capital A。The default folder name is static。

 but you can have the static contents in a directory with a different name。

 as long as you said it explicitly。Notice there are three endpoints in this web application。

The first is slash sample。 This will render a static H M L page。

 The image in this H M L is sourced from the static directory。

The code to accomplish this is app dot root open round bracket。

 single quote slash sample single quote close round bracket。In the second line。

 type def get sample with a capital SHTML with capital H， open round bracket。

 close round bracket colon。Note， there is no space between get sample HTML。In the third line， type。

 returnturn render underscore T open bracket， single quote sample dot HTML。

 single quote close round bracket。The next one is slash user/lash username。

 where the username that you see within angle brackets is the parameter。

The code is written as at app dot root open round bracket。

 single slash user slash specified the username， single comma methods equals open square bracket。

 single get。 in all capital letters， single close square bracket close round bracket。

 If you see the method has been explicitly set to get。

 This is just to show how you can set the type of request。 If nothing is specified。

 It is considered a get request。 The page rendered with the parameter we passed in the URL。😊。



![](img/efb040b83f4c19fb03b7c4a4bf6941ab_16.png)

The last one is slash user slash username， where the username is passed as a request parameter。

The page is rendered with the parameter， which was passed as a request。



![](img/efb040b83f4c19fb03b7c4a4bf6941ab_18.png)

In this video， you learn that Flask is a micro framework for creating web applications and supports Crud。

😊，Install the flask package， using Pip。To create a web application using flask， import flask。

 instantiate Flask， run the app。You can render both static and dynamic templates， with flask。



![](img/efb040b83f4c19fb03b7c4a4bf6941ab_20.png)

![](img/efb040b83f4c19fb03b7c4a4bf6941ab_21.png)
# IBM应用人工智能（从0开始搭建AI机器人）｜IBM Applied AI （中英字幕） - P106：16_使用Flask部署Web应用程序.zh_en - GPT中英字幕课程资源 - BV1p64y1H7LM

![](img/b92ca5738b30ec2623e6d19f11a3ec38_0.png)

![](img/b92ca5738b30ec2623e6d19f11a3ec38_1.png)

Welcome to Deloying Web apps usingsing Flask。

![](img/b92ca5738b30ec2623e6d19f11a3ec38_3.png)

After watching this video， you will be able to describe flask features， install flask。

 create and deploy a Python web app using flask。😊。

![](img/b92ca5738b30ec2623e6d19f11a3ec38_5.png)

![](img/b92ca5738b30ec2623e6d19f11a3ec38_6.png)

Bask is a micro framework for creating web applications quickly and easily with Python。😊。



![](img/b92ca5738b30ec2623e6d19f11a3ec38_8.png)

Flaask supports crud， which is nothing but create， read， update and delete requests by making post。

 put， get， update and delete requests。

![](img/b92ca5738b30ec2623e6d19f11a3ec38_10.png)

![](img/b92ca5738b30ec2623e6d19f11a3ec38_11.png)

Here is the basic structure of a flask application。 Notice the logo of the flask package。



![](img/b92ca5738b30ec2623e6d19f11a3ec38_13.png)

Let's look at how you can use flask for crud operations。



![](img/b92ca5738b30ec2623e6d19f11a3ec38_15.png)

Post and put requests are used for creating objects or data。 For example。

 you can use post and put request to create a user。

 The difference between the two is that post creates the object or data on every request。

 While put creates the object or data only on the first request and continues to update the object or data in consecutive request。



![](img/b92ca5738b30ec2623e6d19f11a3ec38_17.png)

![](img/b92ca5738b30ec2623e6d19f11a3ec38_18.png)

![](img/b92ca5738b30ec2623e6d19f11a3ec38_19.png)

![](img/b92ca5738b30ec2623e6d19f11a3ec38_20.png)

In most web applications， you will see posts being used for creating objects or data。



![](img/b92ca5738b30ec2623e6d19f11a3ec38_22.png)

You can use the gett request to read data from the server。



![](img/b92ca5738b30ec2623e6d19f11a3ec38_24.png)

You can use update requests to update the existing data or objects。😊。



![](img/b92ca5738b30ec2623e6d19f11a3ec38_26.png)

You can use delete requests to delete the existing data or objects。



![](img/b92ca5738b30ec2623e6d19f11a3ec38_28.png)

Note， most web applications tend to use posts for creating。

 updating and deleting objects and data and get for reading。😊。



![](img/b92ca5738b30ec2623e6d19f11a3ec38_30.png)

![](img/b92ca5738b30ec2623e6d19f11a3ec38_31.png)

Another video explains the post， put and get requests in detail。 Next。

 let's look at how to create a web application with flask。😊。



![](img/b92ca5738b30ec2623e6d19f11a3ec38_33.png)

![](img/b92ca5738b30ec2623e6d19f11a3ec38_34.png)

The first step is to install the flask package using Pip， the standard package manager for Python。

Like all other packages， you can use the command Pip install flask。

 which will get the most current version of flask。

![](img/b92ca5738b30ec2623e6d19f11a3ec38_36.png)

The flask package is installed， and you are all set to create the web application。



![](img/b92ca5738b30ec2623e6d19f11a3ec38_38.png)

Next， import the flask package， instantiate flask class， create a web application。

 and then run the application for the purposes of demonstration。

 Let's look at the web application that returns hellello world string as a response to a get request。

 step1， install flask。 step 2， Im the flask module from the flask package to do this type from flask with lowercase F importm flask with capital F。

😊。

![](img/b92ca5738b30ec2623e6d19f11a3ec38_40.png)

![](img/b92ca5738b30ec2623e6d19f11a3ec38_41.png)

![](img/b92ca5738b30ec2623e6d19f11a3ec38_42.png)

![](img/b92ca5738b30ec2623e6d19f11a3ec38_43.png)

Step 3， create an object of the flask class as a web application with the name。

 My first web application and store it as app。 For example。

 app equal to flask with capital F Open round bracket。

 double quotes my with capital M first application double quotes close round bracket。😊。



![](img/b92ca5738b30ec2623e6d19f11a3ec38_45.png)

![](img/b92ca5738b30ec2623e6d19f11a3ec38_46.png)

![](img/b92ca5738b30ec2623e6d19f11a3ec38_47.png)

Most applications use the reference name app for clarity purposes。 However。

 app is just a reference name and you can use any other name。😊。



![](img/b92ca5738b30ec2623e6d19f11a3ec38_49.png)

![](img/b92ca5738b30ec2623e6d19f11a3ec38_50.png)

Step 4， to the route and the method that will be invoked when this route is accessed。 For example。

 enter at app dot root open round bracket， single s single quote， close round bracket。

Notice in this example， neither get nor post have been specified。

When you do not specify a request by default， get as requested。Therefore， in the example。

 the endpoint will now be able to serve get requests to the route。



![](img/b92ca5738b30ec2623e6d19f11a3ec38_52.png)

Step 5， Ho is the method written as deaf。 Ho， open round bracket， close round bracket， colon。

The Hlo method will be invoked when the system accesses the API endpoint that was defined in the previous step。

The code to do this is app dot run open round bracket debug。



![](img/b92ca5738b30ec2623e6d19f11a3ec38_54.png)

It takes no parameters and returns the string， Hello world。



![](img/b92ca5738b30ec2623e6d19f11a3ec38_56.png)

In the code， this is written as return single quote Hallelle world exclamation sign。



![](img/b92ca5738b30ec2623e6d19f11a3ec38_58.png)

Step 6。Add a condition that web application should run only if underscore， underscore name。

 underscore underscore attribute is set to underscore underscore main， underscore underscore。

By default， underscore， underscore name， underscore， underscore is set to underscore。

 underscore main， underscore underscore， unless it is explicitly changed。

You can save and run this like any other Python application。

Type app dot run Open round bracket debug equals true with capital T， close round bracket。



![](img/b92ca5738b30ec2623e6d19f11a3ec38_60.png)

To start the server in a development environment， you need to save the code in a Python file and run it like any other Python application。



![](img/b92ca5738b30ec2623e6d19f11a3ec38_62.png)

![](img/b92ca5738b30ec2623e6d19f11a3ec38_63.png)

When the Web application server starts， it gives you the IP address and the port the application can be accessed from。



![](img/b92ca5738b30ec2623e6d19f11a3ec38_65.png)

To check the endpoints， you can open the browser and connect to this endpoint you see in the server output。

 127。0。0。1。

![](img/b92ca5738b30ec2623e6d19f11a3ec38_67.png)

![](img/b92ca5738b30ec2623e6d19f11a3ec38_68.png)

At port 5000 and see the string Hello world being returned from the Web server application。

 Templates are nothing but prereated H T M L pages that are served from the Web application。😊。



![](img/b92ca5738b30ec2623e6d19f11a3ec38_70.png)

![](img/b92ca5738b30ec2623e6d19f11a3ec38_71.png)

![](img/b92ca5738b30ec2623e6d19f11a3ec38_72.png)

They can be both static and dynamic。By default， the flask application looks for the templates in a directory called templates under the root directory。

 If the templates need to use images， Styling sheets or javascript files。

 which are stored in a folder named static in the root directory。

 The static pages are rendered as is。

![](img/b92ca5738b30ec2623e6d19f11a3ec38_74.png)

![](img/b92ca5738b30ec2623e6d19f11a3ec38_75.png)

![](img/b92ca5738b30ec2623e6d19f11a3ec38_76.png)

![](img/b92ca5738b30ec2623e6d19f11a3ec38_77.png)

The dynamic pages usually have information that is filled in dynamically for each request。

 These pages are often based on the values passed as arguments。



![](img/b92ca5738b30ec2623e6d19f11a3ec38_79.png)

The arguments can either be passed through the URL or be passed as request parameters。

 Let's look at a sample flask application。

![](img/b92ca5738b30ec2623e6d19f11a3ec38_81.png)

![](img/b92ca5738b30ec2623e6d19f11a3ec38_82.png)

You start with importing flask to create web application request to handle the incoming request and render underscore template for rendering static and dynamic H pages。

Type from Flask F lowercase， import flask with capital S comma， render underscore T comma request。



![](img/b92ca5738b30ec2623e6d19f11a3ec38_84.png)

Next， instantiate flask and set the static folder。 For example。

 app equals flask open round bracket double quote my with capital M first application with capital A。



![](img/b92ca5738b30ec2623e6d19f11a3ec38_86.png)

The default folder name is static， but you can have the static contents in a directory with a different name as long as you said it explicitly。



![](img/b92ca5738b30ec2623e6d19f11a3ec38_88.png)

![](img/b92ca5738b30ec2623e6d19f11a3ec38_89.png)

Notice there are three endpoints in this web application。



![](img/b92ca5738b30ec2623e6d19f11a3ec38_91.png)

The first is slash sample。 This will render a static H M L page。

 The image in this H T M L is sourced from the static directory。



![](img/b92ca5738b30ec2623e6d19f11a3ec38_93.png)

The code to accomplish this is app dot root open round bracket single quote slash sample single quote close round bracket。

In the second line， type def get sample with a capital SHTML with capital H， open round bracket。

 close round bracket colon。Note， there is no space between get sample H。In the third line， type。

 returnturn render underscore T open bracket， single quote sample dot HTML。

 single quote close round bracket。

![](img/b92ca5738b30ec2623e6d19f11a3ec38_95.png)

The next one is slash user/lash username， where the username that you see within angle brackets is the parameter。



![](img/b92ca5738b30ec2623e6d19f11a3ec38_97.png)

The code is written as at app dot root open round bracket。

 single slash user slash specified the username， single comma methods equals open square bracket。

 single get in all capital letters， single， close square bracket close round bracket。

 If you see the method has been explicitly set to get。

 This is just to show how you can set the type of request。 If nothing is specified。

 it is considered a get request。 The pages rendered with the parameter we passed in the URL。😊。



![](img/b92ca5738b30ec2623e6d19f11a3ec38_99.png)

![](img/b92ca5738b30ec2623e6d19f11a3ec38_100.png)

![](img/b92ca5738b30ec2623e6d19f11a3ec38_101.png)

The last one is slash user slash username， where the username is passed as a request parameter。



![](img/b92ca5738b30ec2623e6d19f11a3ec38_103.png)

The page is rendered with the parameter， which was passed as a request。



![](img/b92ca5738b30ec2623e6d19f11a3ec38_105.png)

In this video， you learn that Flask is a micro framework for creating web applications and supports crud。

😊。

![](img/b92ca5738b30ec2623e6d19f11a3ec38_107.png)

Instal the flask package， using Pip。

![](img/b92ca5738b30ec2623e6d19f11a3ec38_109.png)

To create a web application using flask， import flask， instantiate flask， run the app。



![](img/b92ca5738b30ec2623e6d19f11a3ec38_111.png)

You can render both static and dynamic templates with flask。



![](img/b92ca5738b30ec2623e6d19f11a3ec38_113.png)
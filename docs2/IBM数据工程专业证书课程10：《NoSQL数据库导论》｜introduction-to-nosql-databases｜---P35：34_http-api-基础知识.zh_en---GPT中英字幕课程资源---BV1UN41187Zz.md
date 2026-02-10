# IBM数据工程专业证书课程10：《NoSQL数据库导论》｜introduction-to-nosql-databases｜ - P35：34_http api 基础知识.zh_en - GPT中英字幕课程资源 - BV1UN41187Zz

![](img/39dbf84a95cbc58453635a4921613d46_0.png)

![](img/39dbf84a95cbc58453635a4921613d46_1.png)

Welcome to HTTP API Bass After watching this video。

 you will be able to describe what the HTTP API is， Ex what curl is， and use simple curl commands。



![](img/39dbf84a95cbc58453635a4921613d46_3.png)

![](img/39dbf84a95cbc58453635a4921613d46_4.png)

![](img/39dbf84a95cbc58453635a4921613d46_5.png)

In an earlier video and a lab， you saw how to use the Cloudant dashboard to perform basic CD operations。

 that is how to create， read， update， and delete data in a Cloudant database。



![](img/39dbf84a95cbc58453635a4921613d46_7.png)

![](img/39dbf84a95cbc58453635a4921613d46_8.png)

The Cloud and Dboard itself is a webbased app that makes hyperpertext transfer protocol or HTTP calls to the application programming interface or API in Cloudant。

 because CloudIn databases have an HTTP API， they have the substantial advantage that they can be accessed from any internet device that wants to read data from them or write data to them。

 and they can do this by using requests from the standard HTTP library。



![](img/39dbf84a95cbc58453635a4921613d46_10.png)

![](img/39dbf84a95cbc58453635a4921613d46_11.png)

A device does not require specialized software or drivers or proprietary protocols or anything of that nature in order to work with Cloud and databases。

The following kinds of devices or technologies can communicate successfully using standard HTTP。

 web browsers， mobile devices， common programming languages。

 and command line scripting tools such as curl。In this video。

 you will get an overview of the curlL Command line and scripting tool to see how to make those HTTP calls or requests so that you can use it to perform the same CRD operations you performed earlier in the course using the dashboard。

Curl is a free open source command line tool that you can use to make HtTP requests to your cloudant API。

 It is part of the client URL or curl Computer softwareft project that was originally released in 1997。



![](img/39dbf84a95cbc58453635a4921613d46_13.png)

![](img/39dbf84a95cbc58453635a4921613d46_14.png)

Curl can get and send data， including files using standard URL syntax directly from the command line。

 or for more repetitive tasks， you could use it in scripts instead。

It also supports securecu HTTP or HTTPS requests by using Secu Sockets layerer or SSL Cate verification。

You can access the latest curl source code at Github。com forward/curl forward slash curl。

If you just want to retrieve a web page from the curl command line prompt。

 you simply enter the word curl， then the URL of the web page。

 The example on this screen will retrieve the IBM Cloud homeage。



![](img/39dbf84a95cbc58453635a4921613d46_16.png)

![](img/39dbf84a95cbc58453635a4921613d46_17.png)

![](img/39dbf84a95cbc58453635a4921613d46_18.png)

But to stop you from having to enter the URL of your cloud and service every time you connect。

 you can create a variable。

![](img/39dbf84a95cbc58453635a4921613d46_20.png)

The example on this screen uses the export URL command to save our Cloudon URL as a variable called URL。

 You do need to replace the username， passwordword and hostpart with your own information from your cloud and service credentials。

 You will do this as part of your hands on labs at the end of this lesson。



![](img/39dbf84a95cbc58453635a4921613d46_22.png)

![](img/39dbf84a95cbc58453635a4921613d46_23.png)

![](img/39dbf84a95cbc58453635a4921613d46_24.png)

![](img/39dbf84a95cbc58453635a4921613d46_25.png)

You could also create an alias that is a shortcut for curl。

 The example on this screen will create an alias called a curl and specifies the J content type header。

 It also uses some useful command line switches。 The lowercase S makes your request silent。 That is。

 you won't see any progress or error messages returned。 Lowercase G disables the URL Gloing parser。

 and uppercase H allows you to specify the content type header。



![](img/39dbf84a95cbc58453635a4921613d46_27.png)

![](img/39dbf84a95cbc58453635a4921613d46_28.png)

![](img/39dbf84a95cbc58453635a4921613d46_29.png)

![](img/39dbf84a95cbc58453635a4921613d46_30.png)

![](img/39dbf84a95cbc58453635a4921613d46_31.png)

![](img/39dbf84a95cbc58453635a4921613d46_32.png)

To test connectivity to your database in Cloudant， you can use the a curl alias and the URL variable。

 The variable must be preceded by a dollar sign。 If you are successful。

 you will get some J code returned that includes a welcome message， a version number。

 a vendor name and features information about your cloudant instance。



![](img/39dbf84a95cbc58453635a4921613d46_34.png)

![](img/39dbf84a95cbc58453635a4921613d46_35.png)

![](img/39dbf84a95cbc58453635a4921613d46_36.png)

![](img/39dbf84a95cbc58453635a4921613d46_37.png)

To retrieve a list of all your databases， you again use the a curl alias and the Doar sign URL variable。

 but with the underscore all underscore DBS End point。



![](img/39dbf84a95cbc58453635a4921613d46_39.png)

![](img/39dbf84a95cbc58453635a4921613d46_40.png)

As an additional option， if you have Python installed on your operating system。

 you can add the pipe command at the end of this line This sends the output of your command to Python for improved JSON formatting in the terminal to transform the JON data into a more readable format。



![](img/39dbf84a95cbc58453635a4921613d46_42.png)

![](img/39dbf84a95cbc58453635a4921613d46_43.png)

![](img/39dbf84a95cbc58453635a4921613d46_44.png)

![](img/39dbf84a95cbc58453635a4921613d46_45.png)

There is also another JSO formatter called JQ， which you can freely download and install。

 which will do a similar job of formatting JSON data into a more readable form。



![](img/39dbf84a95cbc58453635a4921613d46_47.png)

![](img/39dbf84a95cbc58453635a4921613d46_48.png)

The pipe command for specifying this JO formater is pipepe JQ。



![](img/39dbf84a95cbc58453635a4921613d46_50.png)

If you want to view the details of a single database。

 just specify the name of the database after the forward slash。



![](img/39dbf84a95cbc58453635a4921613d46_52.png)

This example on the screen will retrieve the details of a database called training。 Again。

 you can use one of the two optional pipe commands to send the output of your command to Python or dot JQ for improved readability in the curl terminal。



![](img/39dbf84a95cbc58453635a4921613d46_54.png)

![](img/39dbf84a95cbc58453635a4921613d46_55.png)

![](img/39dbf84a95cbc58453635a4921613d46_56.png)

To view the documents contained in a database， just specify the name of the database after the forward slash。

 and then the underscore all underscore docs and point。

 This will retrieve only the underscore IDd and underscore rev values for all the documents。



![](img/39dbf84a95cbc58453635a4921613d46_58.png)

![](img/39dbf84a95cbc58453635a4921613d46_59.png)

To retrieve the bodies of the documents too， you specify question mark include underscore docs equals true at the end of the command as seen in this on screen example。

And to retrieve a single document from your database。

 you specify the document's document ID after the name of the database it's contained in。

In this video you learned that Cloudin databases have an HTTP API so they can be accessed by using requests from the standard HTTP library。

 HTTP is used by web browsers mobile devices， common programming languages and command line scripting tools such as curl Cur is a free open source command line tool that can make HTTP requests to the cloudant API curl can get and send data including files using standard URL syntax from the command line or in a script You should create a variable to access your cloud and service you can use an alias as a shortcut for curl and you can pipe the output of your curl commands to Python or JQ for improved J formatting in the terminal。



![](img/39dbf84a95cbc58453635a4921613d46_61.png)

![](img/39dbf84a95cbc58453635a4921613d46_62.png)
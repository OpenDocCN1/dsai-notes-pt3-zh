# IBM应用人工智能（从0开始搭建AI机器人）｜IBM Applied AI （中英字幕） - P103：13_使用GET和POST模式的请求和响应对象.zh_en - GPT中英字幕课程资源 - BV1p64y1H7LM

![](img/b0f423b1ee3f1e0ac594a3136ce1becb_0.png)

![](img/b0f423b1ee3f1e0ac594a3136ce1becb_1.png)

Welcome to Request and Repon Ob After watching this video。

 you will be able to explain the flask request object and explain the flask response object。



![](img/b0f423b1ee3f1e0ac594a3136ce1becb_3.png)

![](img/b0f423b1ee3f1e0ac594a3136ce1becb_4.png)

![](img/b0f423b1ee3f1e0ac594a3136ce1becb_5.png)

Let's learn how to customize routes in flask。 You define the path using the route decorator and the add app out route decorator defaults to the get method。

 Clients can only send get requests to the specified path。 Now。

 you can pass in a second argument of methods to control what H TTP methods the path responds to。

 For example， look at the following two methods that are the same。

 The get method is implicit in this code。 While this code explicitly specifies the get method。



![](img/b0f423b1ee3f1e0ac594a3136ce1becb_7.png)

![](img/b0f423b1ee3f1e0ac594a3136ce1becb_8.png)

![](img/b0f423b1ee3f1e0ac594a3136ce1becb_9.png)

![](img/b0f423b1ee3f1e0ac594a3136ce1becb_10.png)

Here's another example。 The slash health URL will respond to get and post requests。

 If the request is get， the code outputs the status of O and the method of get。

 If the request is post， the code outputs the status of O and the method of post。

 This is the output from the get curl command， While this is the output from the post curl command。



![](img/b0f423b1ee3f1e0ac594a3136ce1becb_12.png)

![](img/b0f423b1ee3f1e0ac594a3136ce1becb_13.png)

![](img/b0f423b1ee3f1e0ac594a3136ce1becb_14.png)

All HTTP calls to flask contain the request object created from the flask。

t request class when a client requests a resource from the Flask server。

 it is handled by the Add app dot route decorator you can examine and explore the request object in the same method。



![](img/b0f423b1ee3f1e0ac594a3136ce1becb_16.png)

![](img/b0f423b1ee3f1e0ac594a3136ce1becb_17.png)

![](img/b0f423b1ee3f1e0ac594a3136ce1becb_18.png)

Now， the following information is available in the request object。

 the address of the server in the form of a Tuple hosts port。

 the header sent with the request and the URL that is the resource asked by the request。



![](img/b0f423b1ee3f1e0ac594a3136ce1becb_20.png)

![](img/b0f423b1ee3f1e0ac594a3136ce1becb_21.png)

![](img/b0f423b1ee3f1e0ac594a3136ce1becb_22.png)

Access route that lists all the I addresses for requests that are forwarded multiple times。

 Full path that represents the complete path of the request。

 including any query string is secure is true If a client makes a request using HtTPS or WSS protocol I Jason is true If the request contains Jason data。

 and the cookies dictionary contains any cookies sent with the request。



![](img/b0f423b1ee3f1e0ac594a3136ce1becb_24.png)

![](img/b0f423b1ee3f1e0ac594a3136ce1becb_25.png)

![](img/b0f423b1ee3f1e0ac594a3136ce1becb_26.png)

![](img/b0f423b1ee3f1e0ac594a3136ce1becb_27.png)

![](img/b0f423b1ee3f1e0ac594a3136ce1becb_28.png)

In addition， you can access the following data from the header Ca control holds information on how to cache in browsers。

 except informs the browser what kind of content type is understood by the client except encoding indicates the code content Use agent identifies the client application。

 operating system or version except language requests for a specific language and locale and hosts specifies the host and port number of the requested server Now you can replace the request object with a custom request object。

 which is usually optional as the flask request class attributes and methods are enough。

Let's now look at some actual values printed on the server when a client makes a request In this case。

 the client is the curl command from the terminal， The request server is 127。0。0。

1 or local host at port 5000。

![](img/b0f423b1ee3f1e0ac594a3136ce1becb_30.png)

![](img/b0f423b1ee3f1e0ac594a3136ce1becb_31.png)

You next， print out some headers。 The host is the full path of local host Col 5000。

 The user agent is curl version 7。79。1， and the client has requested the content type of application slash Jason。



![](img/b0f423b1ee3f1e0ac594a3136ce1becb_33.png)

![](img/b0f423b1ee3f1e0ac594a3136ce1becb_34.png)

![](img/b0f423b1ee3f1e0ac594a3136ce1becb_35.png)

Okay， let's look at some more attributes from the request object。

 The URL requested is H T TP colon forward slash forward slash Local host colon 5，0，0。

0 The access route list contains the single value of 1，27 do 0 dot 0 dot 1。

 The full path for the request is the home path indicated by a single forward slash I Jason is false as we are not sending any data with the get request is secure is false。

 as the URL is H T T P and not H T T P S and the length of the cookies dictionary is 0。



![](img/b0f423b1ee3f1e0ac594a3136ce1becb_37.png)

![](img/b0f423b1ee3f1e0ac594a3136ce1becb_38.png)

![](img/b0f423b1ee3f1e0ac594a3136ce1becb_39.png)

![](img/b0f423b1ee3f1e0ac594a3136ce1becb_40.png)

![](img/b0f423b1ee3f1e0ac594a3136ce1becb_41.png)

![](img/b0f423b1ee3f1e0ac594a3136ce1becb_42.png)

There are multiple ways to get information from the request object。

 use the get data to access data from the post request as bytes。

 you are then responsible for parsing this data you can also use the getJSO method to get data parsed as JO from the post request。



![](img/b0f423b1ee3f1e0ac594a3136ce1becb_44.png)

![](img/b0f423b1ee3f1e0ac594a3136ce1becb_45.png)

![](img/b0f423b1ee3f1e0ac594a3136ce1becb_46.png)

Now， FlLask also provides more focused methods to get exact information from the request。

 so you don't have to parse the data into a specific type。



![](img/b0f423b1ee3f1e0ac594a3136ce1becb_48.png)

![](img/b0f423b1ee3f1e0ac594a3136ce1becb_49.png)

Args will give you query parameters as a dictionary Jason will parse the data into a dictionary files will provide your user uploaded files form contains all values posted in a form submission and values combines the AGs data with the form data。



![](img/b0f423b1ee3f1e0ac594a3136ce1becb_51.png)

Now that you know what the request object looks like and the methods to get data from the request parameters and body。

 let's see how to extract specific values from this data。



![](img/b0f423b1ee3f1e0ac594a3136ce1becb_53.png)

![](img/b0f423b1ee3f1e0ac594a3136ce1becb_54.png)

The return types for the methods you have seen so far are either a multiDict， immutable multidict。

 or a combined multidict， All these data structures behave like a Python dictionary and you can use indexing or the get method to extract values。



![](img/b0f423b1ee3f1e0ac594a3136ce1becb_56.png)

![](img/b0f423b1ee3f1e0ac594a3136ce1becb_57.png)

For the given URL， you would like to extract the query parameters of capstone and rating。 First。

 you import flask and the request modules in your method。

 You extract the value for the course argument by using indexing。

 Then you extract the value for the rating argument by using the get method。

 The get method returns a value of none。 If the argument is not present。

 whereas the indexing method returns an error and stops the server with a 400 bad request。

 The message shows the request in the browser with a course of capstone and a rating of 10。



![](img/b0f423b1ee3f1e0ac594a3136ce1becb_59.png)

![](img/b0f423b1ee3f1e0ac594a3136ce1becb_60.png)

FLask will provide a response object just like it provides a request object。

 and you can use the response object to send custom attributes and headers back to the client。



![](img/b0f423b1ee3f1e0ac594a3136ce1becb_62.png)

![](img/b0f423b1ee3f1e0ac594a3136ce1becb_63.png)

Some common response attributes include the following Status code indicates the success or failure of the request。

 The headers give more information about the response。

 Content type shows the media type of the requested resource。

 Content length is the size of the response message body。

 Content encoding indicates any encoding applied to the response。

 so the client knows how to decode the data。 mime type sets the media type of the response and expires contains the date or time after which the response is considered expired。



![](img/b0f423b1ee3f1e0ac594a3136ce1becb_65.png)

![](img/b0f423b1ee3f1e0ac594a3136ce1becb_66.png)

Here are some standard methods on response Ob Se cookie sets a browser cookie on the client and Delete cookie deletes a cookie on the client。

Let's now learn how flask works with the response object using the different methods。

 a response object with a status code of 200 and a mindme type of HTML is automatically created for you when you return data from the at route method。

 Jsonfi also creates a response object automatically。

 You can use make response to create a custom response。

 Flask provides a special redirect method to return a 302 status code and redirect the client to another URL。

 And finally， Flask provides an abort method to return a response with an error condition。



![](img/b0f423b1ee3f1e0ac594a3136ce1becb_68.png)

![](img/b0f423b1ee3f1e0ac594a3136ce1becb_69.png)

![](img/b0f423b1ee3f1e0ac594a3136ce1becb_70.png)

![](img/b0f423b1ee3f1e0ac594a3136ce1becb_71.png)

![](img/b0f423b1ee3f1e0ac594a3136ce1becb_72.png)

![](img/b0f423b1ee3f1e0ac594a3136ce1becb_73.png)

![](img/b0f423b1ee3f1e0ac594a3136ce1becb_74.png)

In this video you learned that Flask provides a request and a response object for each client call。

 you can get additional information from the Flask request like headers。

 you can parsse the request object to Get query parameters， body and other arguments。

 and you can set status on response objects before sending response back to the client。



![](img/b0f423b1ee3f1e0ac594a3136ce1becb_76.png)

![](img/b0f423b1ee3f1e0ac594a3136ce1becb_77.png)
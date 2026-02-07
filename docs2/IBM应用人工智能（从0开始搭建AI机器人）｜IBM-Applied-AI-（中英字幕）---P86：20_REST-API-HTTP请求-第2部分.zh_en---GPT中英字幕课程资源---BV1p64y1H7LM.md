# IBM应用人工智能（从0开始搭建AI机器人）｜IBM Applied AI （中英字幕） - P86：20_REST API HTTP请求 第2部分.zh_en - GPT中英字幕课程资源 - BV1p64y1H7LM

![](img/321dfcc24456f2c479328def63705ddb_0.png)

![](img/321dfcc24456f2c479328def63705ddb_1.png)

In this video we will discuss the HTTP protocol using the Requests library。

 a popular method for dealing with the HTTP protocol in Python。

 we will review Python Library requests for working with the HTTP protocols。

 and we will provide an overview of get requests and post requests。



![](img/321dfcc24456f2c479328def63705ddb_3.png)

![](img/321dfcc24456f2c479328def63705ddb_4.png)

![](img/321dfcc24456f2c479328def63705ddb_5.png)

![](img/321dfcc24456f2c479328def63705ddb_6.png)

Let us review the request module in Python。 This is one of several libraries。

 including HtTP Lib and URL Lib that can work with the HtTP protocol。

 Res is a Python library that allows you to send HtTP s 1。1 requests easily。

 We can import the library as follows。 You can make a get request via the method get to www。

 IBM do com。 We have the response object R。 This has information about the request like the status of the request。

 We can view the status code using the attribute status underscore code， which is 200 for okay。

 You can view the request headers。

![](img/321dfcc24456f2c479328def63705ddb_8.png)

![](img/321dfcc24456f2c479328def63705ddb_9.png)

![](img/321dfcc24456f2c479328def63705ddb_10.png)

![](img/321dfcc24456f2c479328def63705ddb_11.png)

![](img/321dfcc24456f2c479328def63705ddb_12.png)

![](img/321dfcc24456f2c479328def63705ddb_13.png)

![](img/321dfcc24456f2c479328def63705ddb_14.png)

You can view the request body in the following line as there is no body for a get request。

 we get a nun。 You can view the HTTP response header using the attribute headers。

 This returns a Python dictionary of HTTP response headers。 We can look at the dictionary values。



![](img/321dfcc24456f2c479328def63705ddb_16.png)

We can obtain the date the request was sent by using the key date。

 The key content type indicates the type of data using the response object R。

 we can also check the encoding。

![](img/321dfcc24456f2c479328def63705ddb_18.png)

![](img/321dfcc24456f2c479328def63705ddb_19.png)

![](img/321dfcc24456f2c479328def63705ddb_20.png)

As the content type is text or HTML， we can use the attribute text to display the HTML in the body。

 we can review the first 100 characters you can also download other content， see the lab for more。



![](img/321dfcc24456f2c479328def63705ddb_22.png)

![](img/321dfcc24456f2c479328def63705ddb_23.png)

![](img/321dfcc24456f2c479328def63705ddb_24.png)

You can use the get method to modify the results of your query， for example。

 retrieving data from an API in the lab， we will use httPB。org。

 a simple httP request and response service。

![](img/321dfcc24456f2c479328def63705ddb_26.png)

![](img/321dfcc24456f2c479328def63705ddb_27.png)

![](img/321dfcc24456f2c479328def63705ddb_28.png)

We send a get request to the server， like before we have the base URL in the route。

 We append slash get。 This indicates we would like to perform a get request。

 This is demonstrated in the following table。

![](img/321dfcc24456f2c479328def63705ddb_30.png)

![](img/321dfcc24456f2c479328def63705ddb_31.png)

![](img/321dfcc24456f2c479328def63705ddb_32.png)

After get is requested， we have the query string This is part of a uniform resource locator or URL。

 and this sends other information to the web server The start of the query is a question mark followed by a series of parameter and value pairs。

 as shown in the table below。

![](img/321dfcc24456f2c479328def63705ddb_34.png)

![](img/321dfcc24456f2c479328def63705ddb_35.png)

![](img/321dfcc24456f2c479328def63705ddb_36.png)

The first parameter name is name， and the value is Joseph。



![](img/321dfcc24456f2c479328def63705ddb_38.png)

The second parameter name is ID， and the value is 1，2，3。

 Each pair parameter and value is separated by an equal sign。

 The series of pairs is separated by the Ampersand。 Let us complete an example in Python。



![](img/321dfcc24456f2c479328def63705ddb_40.png)

![](img/321dfcc24456f2c479328def63705ddb_41.png)

![](img/321dfcc24456f2c479328def63705ddb_42.png)

![](img/321dfcc24456f2c479328def63705ddb_43.png)

We have the base URL with get appended to the end to create a query string。

 we use the dictionary payload， the keys are the parameter names and the values are the value of the query string。

 then we pass the dictionary payload to the parameter's parameter of the get function。



![](img/321dfcc24456f2c479328def63705ddb_45.png)

![](img/321dfcc24456f2c479328def63705ddb_46.png)

We can print out the URL and see the name and values。

 we can see the request body as the info is sent in the URL， the body has a value of none。

 we can print out the status code。

![](img/321dfcc24456f2c479328def63705ddb_48.png)

![](img/321dfcc24456f2c479328def63705ddb_49.png)

![](img/321dfcc24456f2c479328def63705ddb_50.png)

We can view the response as text and we can look at the key content type to look at the content type as the content content type is in the J。

 we format it using the method Jason， It returns a Python dit。

 The key args has the name and values for the query string。 Like a G request。

 a post request is used to send data to a server， but the post request sends the data in a request body。

 not the URL。 in order to send the post request in the URL， we change the route to post。

 This endpoint will expect data， and it is a convenient way to configure an HtTP request to send data to a server。

 We have the payload dictionary to make a post request we use the post function。

 The variable payload is passed to the parameter data。



![](img/321dfcc24456f2c479328def63705ddb_52.png)

![](img/321dfcc24456f2c479328def63705ddb_53.png)

![](img/321dfcc24456f2c479328def63705ddb_54.png)

![](img/321dfcc24456f2c479328def63705ddb_55.png)

![](img/321dfcc24456f2c479328def63705ddb_56.png)

![](img/321dfcc24456f2c479328def63705ddb_57.png)

![](img/321dfcc24456f2c479328def63705ddb_58.png)

![](img/321dfcc24456f2c479328def63705ddb_59.png)

![](img/321dfcc24456f2c479328def63705ddb_60.png)

![](img/321dfcc24456f2c479328def63705ddb_61.png)

Comparing the URL using the attribute URL from the response object of the get and post request。

 we see the post request has no name or value pairs in its URL。

 We can compare the post and get request body， we see only the post request has a body。

 and we can view the key form to get the payload。

![](img/321dfcc24456f2c479328def63705ddb_63.png)

![](img/321dfcc24456f2c479328def63705ddb_64.png)

![](img/321dfcc24456f2c479328def63705ddb_65.png)

![](img/321dfcc24456f2c479328def63705ddb_66.png)

![](img/321dfcc24456f2c479328def63705ddb_67.png)

![](img/321dfcc24456f2c479328def63705ddb_68.png)
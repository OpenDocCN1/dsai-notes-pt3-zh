# IBM《生成式人工智能工程（AI入门、生成式AI入门、提示工程、Python）｜IBM Generative AI Engineering》中英字幕 - P74：20_REST API：HTTP请求（第2部分）.zh_en - GPT中英字幕课程资源 - BV1MfqzY4Eyg

![](img/719af6e73367f003b9ab5782f7888985_0.png)

![](img/719af6e73367f003b9ab5782f7888985_1.png)

In this video we will discuss the HTTP protocol using the Requests library。

 a popular method for dealing with the HTTP protocol in Python。

 we will review Python Library requests for working with the HTTP protocols。

 and we will provide an overview of get requests and post requests。



![](img/719af6e73367f003b9ab5782f7888985_3.png)

![](img/719af6e73367f003b9ab5782f7888985_4.png)

Let us review the request module in Python。 This is one of several libraries。

 including HtTP LibB and URL Lib that can work with the HtTP protocol。

 requests is a Python library that allows you to send HtTP s 1。1 requests easily。

 We can import the library as follows。 You can make a get request via the method get to www。 IBM。 co。

 We have the response object R。 This has information about the request like the status of the request。

 We can view the status code using the attribute status underscore code， which is 2004 okay。

 You can view the request headers。

![](img/719af6e73367f003b9ab5782f7888985_6.png)

![](img/719af6e73367f003b9ab5782f7888985_7.png)

![](img/719af6e73367f003b9ab5782f7888985_8.png)

You can view the request body in the following line as there is no body for a get request。

 we get a nu。 You can view the HTTP response header using the attribute headers。

 This returns a Python dictionary of HTTP response headers。 We can look at the dictionary values。

We can obtain the date the request was sent by using the key date。

 The key content type indicates the type of data using the response object R。

 we can also check the encoding。As the content type is text or HTML。

 we can use the attribute text to display the HTML in the body we can review the first 100 characters you can also download other content。

 see the lab for more。

![](img/719af6e73367f003b9ab5782f7888985_10.png)

You can use the get method to modify the results of your query， for example。

 retrieving data from an API in the lab， we will use httPB。org。

 a simple httP request and response service。

![](img/719af6e73367f003b9ab5782f7888985_12.png)

We send a get request to the server， like before we have the base URL in the route。

 We append slash get。 This indicates we would like to perform a get request。

 This is demonstrated in the following table。

![](img/719af6e73367f003b9ab5782f7888985_14.png)

After get is requested， we have the query string This is part of a uniform resource locator or URL and this sends other information to the web server The start of the query is a question mark followed by a series of parameter and value pairs。

 as shown in the table below。The first parameter name is name， and the value is Joseph。

The second parameter name is ID， and the value is 1，2，3。

 Each pair parameter and value is separated by an equal sign。

 The series of pairs is separated by the Ampersand。 Let us complete an example in Python。



![](img/719af6e73367f003b9ab5782f7888985_16.png)

![](img/719af6e73367f003b9ab5782f7888985_17.png)

We have the base URL with get appended to the end to create a query string。

 we use the dictionary payload， the keys are the parameter names and the values are the value of the query string。

 then we pass the dictionary payload to the parameter's parameter of the get function。

We can print out the URL and see the name and values。

 we can see the request body as the info is sent in the URL， the body has a value of none。

 we can print out the status code。

![](img/719af6e73367f003b9ab5782f7888985_19.png)

We can view the response as text and we can look at the key content type to look at the content type as the content content type is in the J。

 we format it using the method Jason， It returns a Python di。

 The key args has the name and values for the query string Like a G request。

 a post request is used to send data to a server， but the post request sends the data in a request body。

 not the URL。 in order to send the post request in the URL， we change the route to post。

 This endpoint will expect data， and it is a convenient way to configure an HtTP request to send data to a server。

 We have the payload dictionary。 to make a post request。 we use the post function。

 The variable payload is passed to the parameter data。



![](img/719af6e73367f003b9ab5782f7888985_21.png)

![](img/719af6e73367f003b9ab5782f7888985_22.png)

![](img/719af6e73367f003b9ab5782f7888985_23.png)

![](img/719af6e73367f003b9ab5782f7888985_24.png)

Comparing the URL using the attribute URL from the response object of the get and post request。

 we see the post request has no name or value pairs in its URL。

 we can compare the post and get request body， we see only the post request has a body and we can view the key form to get the payload。



![](img/719af6e73367f003b9ab5782f7888985_26.png)

![](img/719af6e73367f003b9ab5782f7888985_27.png)

![](img/719af6e73367f003b9ab5782f7888985_28.png)

![](img/719af6e73367f003b9ab5782f7888985_29.png)

![](img/719af6e73367f003b9ab5782f7888985_30.png)
# IBM数据科学专业证书课程4：《Python应用于数据科学、人工智能和开发》python-for-applied-data-science-ai（中英字幕） - P21：20_REST API与HTTP请求（下）.zh_en - GPT中英字幕课程资源 - BV1AF411f7yv

![](img/12e1d1f0a25977ea3013e2b2d8ba3645_0.png)

![](img/12e1d1f0a25977ea3013e2b2d8ba3645_1.png)

In this video we will discuss the HTTP protocol using the Requests library。

 a popular method for dealing with the HTTP protocol in Python。

 we will review Python Library requests for working with the HTTP protocols。

 and we will provide an overview of get requests and post requests。



![](img/12e1d1f0a25977ea3013e2b2d8ba3645_3.png)

![](img/12e1d1f0a25977ea3013e2b2d8ba3645_4.png)

![](img/12e1d1f0a25977ea3013e2b2d8ba3645_5.png)

![](img/12e1d1f0a25977ea3013e2b2d8ba3645_6.png)

Let us review the request module in Python。 This is one of several libraries。

 including HtTP LibB and URL Lib that can work with the HtTP protocol。

 requests is a Python library that allows you to send HtTP s 1。1 requests easily。

 We can import the library as follows。 You can make a get request via the method get to www。 IBM。 co。

 We have the response object R。 This has information about the request like the status of the request。

 We can view the status code using the attribute status underscore code， which is 2004 okay。

 You can view the request headers。

![](img/12e1d1f0a25977ea3013e2b2d8ba3645_8.png)

![](img/12e1d1f0a25977ea3013e2b2d8ba3645_9.png)

![](img/12e1d1f0a25977ea3013e2b2d8ba3645_10.png)

![](img/12e1d1f0a25977ea3013e2b2d8ba3645_11.png)

![](img/12e1d1f0a25977ea3013e2b2d8ba3645_12.png)

![](img/12e1d1f0a25977ea3013e2b2d8ba3645_13.png)

![](img/12e1d1f0a25977ea3013e2b2d8ba3645_14.png)

You can view the request body in the following line as there is no body for a get request。

 we get a nu。 You can view the HTTP response header using the attribute headers。

 This returns a Python dictionary of HTTP response headers。 We can look at the dictionary values。



![](img/12e1d1f0a25977ea3013e2b2d8ba3645_16.png)

We can obtain the date the request was sent by using the key date。

 The key content type indicates the type of data using the response object R。

 we can also check the encoding。

![](img/12e1d1f0a25977ea3013e2b2d8ba3645_18.png)

![](img/12e1d1f0a25977ea3013e2b2d8ba3645_19.png)

![](img/12e1d1f0a25977ea3013e2b2d8ba3645_20.png)

As the content type is text or HTML， we can use the attribute text to display the HTML in the body we can review the first 100 characters you can also download other content。

 see the lab for more。

![](img/12e1d1f0a25977ea3013e2b2d8ba3645_22.png)

![](img/12e1d1f0a25977ea3013e2b2d8ba3645_23.png)

![](img/12e1d1f0a25977ea3013e2b2d8ba3645_24.png)

You can use the get method to modify the results of your query， for example。

 retrieving data from an API in the lab， we will use httPB。org。

 a simple httP request and response service。

![](img/12e1d1f0a25977ea3013e2b2d8ba3645_26.png)

![](img/12e1d1f0a25977ea3013e2b2d8ba3645_27.png)

![](img/12e1d1f0a25977ea3013e2b2d8ba3645_28.png)

We send a get request to the server， like before we have the base URL in the route。

 We append slash get。 This indicates we would like to perform a get request。

 This is demonstrated in the following table。

![](img/12e1d1f0a25977ea3013e2b2d8ba3645_30.png)

![](img/12e1d1f0a25977ea3013e2b2d8ba3645_31.png)

![](img/12e1d1f0a25977ea3013e2b2d8ba3645_32.png)

After get is requested， we have the query string This is part of a uniform resource locator or URL and this sends other information to the web server The start of the query is a question mark followed by a series of parameter and value pairs。

 as shown in the table below。

![](img/12e1d1f0a25977ea3013e2b2d8ba3645_34.png)

![](img/12e1d1f0a25977ea3013e2b2d8ba3645_35.png)

![](img/12e1d1f0a25977ea3013e2b2d8ba3645_36.png)

The first parameter name is name， and the value is Joseph。



![](img/12e1d1f0a25977ea3013e2b2d8ba3645_38.png)

The second parameter name is ID， and the value is 1，2，3。

 Each pair parameter and value is separated by an equal sign。

 The series of pairs is separated by the Ampersand。 Let us complete an example in Python。



![](img/12e1d1f0a25977ea3013e2b2d8ba3645_40.png)

![](img/12e1d1f0a25977ea3013e2b2d8ba3645_41.png)

![](img/12e1d1f0a25977ea3013e2b2d8ba3645_42.png)

![](img/12e1d1f0a25977ea3013e2b2d8ba3645_43.png)

We have the base URL with get appended to the end to create a query string。

 we use the dictionary payload， the keys are the parameter names and the values are the value of the query string。

 then we pass the dictionary payload to the parameter's parameter of the get function。



![](img/12e1d1f0a25977ea3013e2b2d8ba3645_45.png)

![](img/12e1d1f0a25977ea3013e2b2d8ba3645_46.png)

We can print out the URL and see the name and values。

 we can see the request body as the info is sent in the URL， the body has a value of none。

 we can print out the status code。

![](img/12e1d1f0a25977ea3013e2b2d8ba3645_48.png)

![](img/12e1d1f0a25977ea3013e2b2d8ba3645_49.png)

![](img/12e1d1f0a25977ea3013e2b2d8ba3645_50.png)

We can view the response as text and we can look at the key content type to look at the content type as the content content type is in the J。

 we format it using the method Jason， It returns a Python di。

 The key args has the name and values for the query string Like a G request。

 a post request is used to send data to a server， but the post request sends the data in a request body。

 not the URL。 in order to send the post request in the URL， we change the route to post。

 This endpoint will expect data， and it is a convenient way to configure an HtTP request to send data to a server。

 We have the payload dictionary。 to make a post request。 we use the post function。

 The variable payload is passed to the parameter data。



![](img/12e1d1f0a25977ea3013e2b2d8ba3645_52.png)

![](img/12e1d1f0a25977ea3013e2b2d8ba3645_53.png)

![](img/12e1d1f0a25977ea3013e2b2d8ba3645_54.png)

![](img/12e1d1f0a25977ea3013e2b2d8ba3645_55.png)

![](img/12e1d1f0a25977ea3013e2b2d8ba3645_56.png)

![](img/12e1d1f0a25977ea3013e2b2d8ba3645_57.png)

![](img/12e1d1f0a25977ea3013e2b2d8ba3645_58.png)

![](img/12e1d1f0a25977ea3013e2b2d8ba3645_59.png)

![](img/12e1d1f0a25977ea3013e2b2d8ba3645_60.png)

![](img/12e1d1f0a25977ea3013e2b2d8ba3645_61.png)

Comparing the URL using the attribute URL from the response object of the get and post request。

 we see the post request has no name or value pairs in its URL。

 we can compare the post and get request body， we see only the post request has a body and we can view the key form to get the payload。



![](img/12e1d1f0a25977ea3013e2b2d8ba3645_63.png)

![](img/12e1d1f0a25977ea3013e2b2d8ba3645_64.png)

![](img/12e1d1f0a25977ea3013e2b2d8ba3645_65.png)

![](img/12e1d1f0a25977ea3013e2b2d8ba3645_66.png)

![](img/12e1d1f0a25977ea3013e2b2d8ba3645_67.png)

![](img/12e1d1f0a25977ea3013e2b2d8ba3645_68.png)
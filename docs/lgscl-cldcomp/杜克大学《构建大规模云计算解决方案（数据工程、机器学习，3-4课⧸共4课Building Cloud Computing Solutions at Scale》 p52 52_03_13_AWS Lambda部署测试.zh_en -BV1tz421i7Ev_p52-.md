# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p52 52_03_13_AWS Lambda部署测试.zh_en -BV1tz421i7Ev_p52-

![](img/054cfad98c9d6a19cd21f8a7519a82b0_0.png)

Now that we've got a 80 Bo Lambda function built， let's go through and invoke it locally and look at a couple different ways we can test it。

 So first， we can do this command here， which is Sam local invoke。

RightAnd this invokes the Lambda function as long as you live inside of the correct directory。

 so notice that I'm not inside of the Lambda directory so I need to change into there。

 let's go ahead and do that。 let's look at this 80 post Lambda and it's inside of hello world。

And now if I type in CM local invoke。It will actually be able to look inside this template。

 pull a container and then test the function itself so it doesn't test the API Now if I want to test the API。

 so essentially the API gateway I'll run this command which is Sam local start API so let's go ahead and clear the screen run this and this is great because it runs a web service here and then if I go through and look in fact this is the thing that I want to call which is the 127001 colon 3000 slash hello and so I'm going copy that。

I'm going open up a new terminal here and then I'm going to run the curl command。 So curl go through。

 run this and we see that the payload is successful。 if I go to the output。

 you can see here as well that a 200 request was made to this application So there's a couple really clever ways to test things out locally and it's really a great convenience for local development Now let's go ahead and kill this I'll do control C and look at a few other things here So API gateway when it's in the AWS cloud。

 let's look at that， let's look at Cloudwatch logs and let's also look at the correct IAM security settings to make sure that we understand what those do So first off if we go to this function here and we look at the actual monitoring tab here。

It gives us the ability to look at a high levelvel overview of everything that's happening in this particular function。

 Now one of the things that we can do is we can actually say view logs and cloudWatch and if you've invoke the function inside of AWS。

 then itll allow you to look at those invocation so we can see here that these are all of the invocations that have occurred and because there's no print statements there's no output but if we wanted to add additional information to this function we can go through and do that so the other thing that we'll look at is also the API gateway so if I go through here and I again go back to the function itself。

Go through here， notice that the trigger is where the API gateway is set。

 So AWs Lambda has many different kinds of triggers。 you know Io Kafka cloudfront。

 these are all different things that can be hooked into the AWs Lada ecosystem in this particular instance。

 it's going be API gateway if I click on it， it'll show me this hello world function。

 So the last thing that we'll take a look at is the security settings。

 and the reason why this is important if we go through here and we look at this environment。

 we look at permissions here， the reason why this is important is that in particular。

 if you wanted to make sure that this could do other things you would have to change your your setting here that allowed it to do other actions like for example。

 call let's say AWS。Dynamod DB or to call S3 or to invoke SQS。

So these are all things that could be edited by allowing this particular function permission to access other resources。

 and so these are where you would go through and change those functions and this in particular is the statement ID that allows you to go through and edit those permissions。

So there's a couple different ways that you can do this。

 you can do this again by action right or you can also do this by resource。

 but in general it's important to know that these are abilities that your particular function has and this shows you all of those abilities so again for making more advanced applications you need to add a different role。



![](img/054cfad98c9d6a19cd21f8a7519a82b0_2.png)
# 伊利诺伊大学【中英⚡商业分析｜Business Analytics Specialization】 p56 P56 09_清理你的代码 -BV1z86nB9EGz_p56-

![](img/d41048cc7a96c0a9a5cd91e040f53af0_0.png)

Let's talk about how to clean your code。 That's right， not clean your data， but your code。

After exploring your data and creating a workflow to clean it up。

There's a good chance that you'll want to make sure that it's easy to read your code and that it runs efficiently。

So I want to walk through a simple scenario in which I've cleaned and explored the data and then demonstrate three things that you can do to clean up your coat。

In this Jupiter lab environment， I've created a data frame that is untidy in a variety of ways。

 So I've got this column here that has a space in the column name， a space category。



![](img/d41048cc7a96c0a9a5cd91e040f53af0_2.png)

And then the values in this a category column have some words that start with a capital letter and some that don't。

I've also got some missing values in here。

![](img/d41048cc7a96c0a9a5cd91e040f53af0_4.png)

So what I would normally do is I would go through my code and I'd do one thing at a time and then evaluate if it worked or not。



![](img/d41048cc7a96c0a9a5cd91e040f53af0_6.png)

So for instance， if I want to rename one column here。

 I'd use this rename function and rename a category to category。



![](img/d41048cc7a96c0a9a5cd91e040f53af0_8.png)

And I'd run that and verified that it worked。

![](img/d41048cc7a96c0a9a5cd91e040f53af0_10.png)

And then if I want to convert everything in the category column to lowercase。

 I'd use the string dot lower method。And then verified that all of the values in the category column are all lower case。



![](img/d41048cc7a96c0a9a5cd91e040f53af0_12.png)

Let's say I want to fill in the missing values in this cost column with the average value。



![](img/d41048cc7a96c0a9a5cd91e040f53af0_14.png)

So I would use the fill N function and fill in those values with the mean。



![](img/d41048cc7a96c0a9a5cd91e040f53af0_16.png)

Then verify that those are indeed filled in。And then let's say I also want to remove rows that have missing values in them like this one right here。



![](img/d41048cc7a96c0a9a5cd91e040f53af0_18.png)

![](img/d41048cc7a96c0a9a5cd91e040f53af0_19.png)

So I would run that。And verify that I no longer have any missing values in my data。



![](img/d41048cc7a96c0a9a5cd91e040f53af0_21.png)

So it's pretty easy to run those， especially once I've typed it out。

 I can run through it again really easily。But it's kind of cumbersome to go through and take this process and see what I'm doing in one glance。

 And I'm also printing out the data frame a lot。So let me demonstrate a few tips for cleaning up your code。



![](img/d41048cc7a96c0a9a5cd91e040f53af0_23.png)

The first thing you can do is remove all the exploratory displays of data。

 whether those are the data frames or the visualizations， if you don't really need them any more。

 then you can remove those。Another thing that you can do is combine your code into a single cell。



![](img/d41048cc7a96c0a9a5cd91e040f53af0_25.png)

Or a smaller subset of cells。

![](img/d41048cc7a96c0a9a5cd91e040f53af0_27.png)

And then you can take that step even a little further and combine some of your steps into a single line of code by chaining commands together。

 Let's look at one way that I can combine all those steps into a single line of code。



![](img/d41048cc7a96c0a9a5cd91e040f53af0_29.png)

So I'm going to create this new data from MDF clean。

 and then I'm going to chain on here the rename method。And then I've got this other method assigned。

 I'll talk more about this in a minute。But then I've got the fill N method。

Then the drop in a method and the reset index。Al right， so by running this a single line。

 I get the same result， but it's only one line of code。Now， before I go on any further。

 you're probably saying to yourself， yeah， but that's really complicated to read。

 And I agree that's dense。 and readability counts when using code to analyze data。

So let me show you how you can make this better。First of all。

 you can surround everything in this line of code。By parentheses。 Okay， so open parentheses。

 closing parentheses。And by doing that， I can put each method on its own line here。All right。

 Now this makes it much easier to read because I can see that I'm taking the original data frame I'm renaming a column。

And I' will come back to this assign row here。 Then I'm filling in missing values。

 I'm dropping rows have missing values， and I'm resetting the index。Alright， so much easier to read。

 And just by placing parentheses around it and then putting them on new lines， that's。

 that's powerful。Alright， now another thing that you'll notice about this is that I'm only typing out the data frame name once。

 whereas in all of this exploratory data， I'm having to type out。



![](img/d41048cc7a96c0a9a5cd91e040f53af0_31.png)

![](img/d41048cc7a96c0a9a5cd91e040f53af0_32.png)

A D F clean over and over again。Allright， so those are some benefits of it。 Now。

 one drawback is what we see in this line of code right here。

 Now this assign method is actually really helpful。

 It allows you to create new columns within a single function。

 and I don't have to type out the data frame name and then the name of the column。



![](img/d41048cc7a96c0a9a5cd91e040f53af0_34.png)

The downside of this is that I cannot refer to。The data frame like this。

 This is how we would normally do it， right。 And if you try that， you're going to get an error。



![](img/d41048cc7a96c0a9a5cd91e040f53af0_36.png)

![](img/d41048cc7a96c0a9a5cd91e040f53af0_37.png)

And so instead， what we do is we use a short lived anonymous function called a Lambda function。

 And if you don't know what these are， don't worry a whole lot about it。

 But just recognize that rather than type out the data frame name。

 we basically have to type out Lambda。And then some letter， and then a colon。

 And then we use that letter to represent the name of the data frame。Alright。

 so this is one of the drawbacks， I guess， of using this assign method to create new columns。

 But overall， I really like this approach because it， like I said。

 it just makes it so much easier to read。😊，In summary。

Remembering to remove exploratory displays of data。

 combining your code into a single cell or smaller number of cells。

 and then combining your code into fewer lines will really improve the readability and the efficiency of your data。

Now these things are not always required， you don't have to clean your code。

But you'll be grateful that you've done so when you come back or others come and read your code after you've created it。



![](img/d41048cc7a96c0a9a5cd91e040f53af0_39.png)

![](img/d41048cc7a96c0a9a5cd91e040f53af0_40.png)
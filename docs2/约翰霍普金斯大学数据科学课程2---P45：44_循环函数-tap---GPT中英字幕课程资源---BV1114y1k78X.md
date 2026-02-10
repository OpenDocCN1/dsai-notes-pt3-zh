# 约翰霍普金斯大学数据科学课程2：《R编程课程》｜r-programming｜中英字幕 - P45：44_循环函数 tapply.zh_en - GPT中英字幕课程资源 - BV1114y1k78X

![](img/28fdee01a38b611b32ff131d45bb6bd7_0.png)

![](img/28fdee01a38b611b32ff131d45bb6bd7_1.png)

T apply is a very useful function and it's used to apply a function over subsets of a vector。

 So the idea is basically imagine you have a vector usually it's going to be numbers of a numeric vector and there are pieces of this vector that you want to calculate a summary statistic over and so you're going to have to have another variable or another object which identifies which element of your numeric vector belongs to which group the idea is that for each group and the numeric vector you're going to calculate a summary statistic like a mean or a standard deviation or whatever。



![](img/28fdee01a38b611b32ff131d45bb6bd7_3.png)

![](img/28fdee01a38b611b32ff131d45bb6bd7_4.png)

![](img/28fdee01a38b611b32ff131d45bb6bd7_5.png)

![](img/28fdee01a38b611b32ff131d45bb6bd7_6.png)

![](img/28fdee01a38b611b32ff131d45bb6bd7_7.png)

![](img/28fdee01a38b611b32ff131d45bb6bd7_8.png)

So the basic idea behind T apply is that the first L argument is a numeric vector or a vector of some sort。

 the second argument is another vector of the same length。



![](img/28fdee01a38b611b32ff131d45bb6bd7_10.png)

![](img/28fdee01a38b611b32ff131d45bb6bd7_11.png)

which identifies which group each element of the numeric vector is in， so for example。

 if there are two groups， suppose you have a men and women， for example。

 in two groups and maybe the first 50 observations are men and the second 50 observations are women。



![](img/28fdee01a38b611b32ff131d45bb6bd7_13.png)

![](img/28fdee01a38b611b32ff131d45bb6bd7_14.png)

![](img/28fdee01a38b611b32ff131d45bb6bd7_15.png)

Then you need to have a factor variable which indicates which observations are men and which are women。

 and if you want to take the mean of the numeric factor within men and within women。



![](img/28fdee01a38b611b32ff131d45bb6bd7_17.png)

![](img/28fdee01a38b611b32ff131d45bb6bd7_18.png)

Then you can use T applied to do this so fun is the function that you want to apply and so this is going to be the same as before it's going to be either a function or you're going to pass in an anonymous function and then the dot dot dot contains the other arguments that may go to this function and then the simplifyim argument indicates whether you want to simplify the results kind of like the S apply simplification。



![](img/28fdee01a38b611b32ff131d45bb6bd7_20.png)

![](img/28fdee01a38b611b32ff131d45bb6bd7_21.png)

![](img/28fdee01a38b611b32ff131d45bb6bd7_22.png)

![](img/28fdee01a38b611b32ff131d45bb6bd7_23.png)

![](img/28fdee01a38b611b32ff131d45bb6bd7_24.png)

So here's a very simple example， I'm simulating a vector of normal random variables and uniform random variables and there's 10 normals。

 10 uniforms then 10 normals that have a mean of1 so you can think of this vector as having three groups so then I'm going to create another factor variable using the GL function it's going be this factor variable is going to have three levels and each level is going to be repeated 10 times so when I print out the factor variable here you can see that theres 10 ones there's 10 twos and there's 10 threes so that the factor variable indicates kind of which group the observation is in so now I can t apply on x pass the factor variable F and the mean function and that allows me to take the mean of each group of numbers in x。



![](img/28fdee01a38b611b32ff131d45bb6bd7_26.png)

![](img/28fdee01a38b611b32ff131d45bb6bd7_27.png)

![](img/28fdee01a38b611b32ff131d45bb6bd7_28.png)

![](img/28fdee01a38b611b32ff131d45bb6bd7_29.png)

![](img/28fdee01a38b611b32ff131d45bb6bd7_30.png)

![](img/28fdee01a38b611b32ff131d45bb6bd7_31.png)

![](img/28fdee01a38b611b32ff131d45bb6bd7_32.png)

![](img/28fdee01a38b611b32ff131d45bb6bd7_33.png)

![](img/28fdee01a38b611b32ff131d45bb6bd7_34.png)

![](img/28fdee01a38b611b32ff131d45bb6bd7_35.png)

If you don't simplify the result， then what you get back is going to be a list。

 so T apply applied to the same numeric vector and factor as on the previous slide。

 when I calculate the mean and I say simplifyimpl equals false。

 then I get back a list with three elements and each element of the list is the mean of that subgroup。



![](img/28fdee01a38b611b32ff131d45bb6bd7_37.png)

![](img/28fdee01a38b611b32ff131d45bb6bd7_38.png)

![](img/28fdee01a38b611b32ff131d45bb6bd7_39.png)

![](img/28fdee01a38b611b32ff131d45bb6bd7_40.png)

![](img/28fdee01a38b611b32ff131d45bb6bd7_41.png)

I can pass it a slightly more complicated summary statistics so here instead of calculating the mean which returns one number。

 I'm going to calculate the range of observations， so this gives me the min and the max of the observations within that subset of the vector X。

 and so here I'm getting a list where each element is a vector of length2。



![](img/28fdee01a38b611b32ff131d45bb6bd7_43.png)

![](img/28fdee01a38b611b32ff131d45bb6bd7_44.png)

![](img/28fdee01a38b611b32ff131d45bb6bd7_45.png)

![](img/28fdee01a38b611b32ff131d45bb6bd7_46.png)
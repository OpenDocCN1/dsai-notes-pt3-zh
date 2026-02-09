# 约翰霍普金斯大学《数据科学R语言基础｜Data Science： Foundations using R》中英字幕（deepseek - P63：44_循环函数tapply.zh_en - GPT中英字幕课程资源 - BV1tsFQemEts

![](img/fa1e4c15ecf5493e064df1a218dc02d2_0.png)

![](img/fa1e4c15ecf5493e064df1a218dc02d2_1.png)

T apply is a very useful function and it's used to apply a function over subset of a vector。

 So the idea is basically imagine you have a vector usually it's going to be numbers。

 a numeric vector and there are pieces of this vector that you want to calculate a summary statistic over and so you're going to have to have another variable or another object which identifies which element of your numeric vector belongs to which group the idea is that for each group and the numeric vector you're going to calculate a summary statistic like a mean or a standard deviation or whatever。



![](img/fa1e4c15ecf5493e064df1a218dc02d2_3.png)

So the basic idea behind T apply is that the first argument is a numeric vector or a vector of some sort。

 the second argument is another vector of the same length which identifies which group each element of the numeric vector is in。

 so for example， if there are two group， suppose you have a men and women for example in two groups and maybe the first 50 observations are men and the second 50 observations are women。

Then you need to have a factor variable which indicates which observations are men and which are women。

 and if you want to take the mean of the numeric factor within men and within women。

Then you can use T applied to do this so fun is the function that you want to apply and so this is going to be the same as before it's going to be either a function or you're going to pass in an anonymous function and then the dot dot dot contains the other arguments that may go to this function and then the simplifyim argument indicates whether you want to argument simplify the results。

 kind of like the S apply simplification。

![](img/fa1e4c15ecf5493e064df1a218dc02d2_5.png)

So here's a very simple example， I'm simulating a vector of normal random variables and uniform random variables and there's 10 normals。

 10 uniforms then 10 normals that have a mean of 1 so you can think of this vector as having three groups so then I'm going to create another factor variable using the GL function and it's going be this factor variable is going to have three levels and each level is gonna to be repeated 10 times so when I print out the factor variable here you can see that theres 10 ones there's 10 twos and theres 10 threes each so that the factor variable indicates kind of which group the observation is in so now I can t apply on x pass at the factor variable F and the mean function and that allows going to take the mean of each group of numbers in x。

If you don't simplify the result， then what you get back is going to be a list。

 so TF applied to the same numeric vector and factor as on the previous slide。

 when I calculate the mean and I say simplifyim equals false。

 then I get back a list with three elements and in each element of the list is the mean of that subgroup。



![](img/fa1e4c15ecf5493e064df1a218dc02d2_7.png)

![](img/fa1e4c15ecf5493e064df1a218dc02d2_8.png)

I can pass it a slightly more complicated summary statistics so here instead of calculating the mean which returns one number。

 I'm going to calculate the range of observations， so this gives you the min and the max of the observations within that subset of the vector X。

 and so here I'm getting a list where each element is a vector of length2。



![](img/fa1e4c15ecf5493e064df1a218dc02d2_10.png)

![](img/fa1e4c15ecf5493e064df1a218dc02d2_11.png)

![](img/fa1e4c15ecf5493e064df1a218dc02d2_12.png)
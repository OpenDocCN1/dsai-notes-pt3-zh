# 杜克大学《MLOps ｜ 机器学习运维（Python基础）｜MLOps ｜ Machine Learning Operations》 - P63：63_04_05_使用pandas应用函数.zh_en - GPT中英字幕课程资源 - BV1kw4m167aV

![](img/fe4881e684b3b9b817be11aca7d6870c_0.png)

。

![](img/fe4881e684b3b9b817be11aca7d6870c_2.png)

One of the differences between working with data in pandas then working with data in just plain Python is that in Python you would usually loop around the data so if it's a list or dictionary。

 you're creating new data structures you're extracting certain things but you're always looping around pandas has a way where whenever you want to manipulate things you're applying a function now this doesn't mean that one way is better than the other。

 but it's definitely if you're not used to applying functions to data then this might be a little bit surprising。

 but all that it is is that you're allowed to be working with your own functions to manipulate and do operations so here I've loaded the same data set as before and the business the business premise here。

 the business problem that we're having here the requirement is that we want to see the top wines。

 given some arbitrary opinion on the rating now like I mentioned。

The wine ratings will go basically from the lower  eighties0s all the way to 100， which and， and。

Means perfection in a wine。 So we want to say that anything above 95 points is is or 995 points or greater is going to be a good a good one。

 So we want to manipulate this and we want to create that column。 So how do we do that。

 we have a condition that we need to match。 and we want an output and we want to create a column。

 So I'm going to create the function here。 And you can see this is just a regular function。

 It doesn't do much here， you can see it's it the whole function is four lines and it's three lines of code or factual code that does the work。

 So it's going to receive a value that is going to be passed in by pandas。

 and the logic is going to be the value is above 94， then return true。 It's good one。

 That's the name of the function。 Otherwise return false。 How do you apply it to your data frame。

 Well， you're gonna say line8。I'm gonna create this new column called good。 And I'm gonna say， hey。

 the go and look at the rating and then apply these good wine function。

So it's going to for every single for every single item it's going to be passing the value and then that's going to be the foundation for good and then I'm going to query I'm going to query the rating to be above 94 and let's take a look at what we have All right so first first entry here we have good is true right now pandas perhaps these could be like a 1 or a0 like if you want to do some other numerical analysis or statistical analysis that might be a better a better type here than true or false。

 but you could be a1 or0 you can now you have a way to change that right so if I go here and say1 and instead of false I do0。

And then save that and run these you can see now that good is1 or was it would be a0。

 so there you have it， that's how you apply functions and in this case we've created a new column called good。

 you can do that even in place， but you're able to apply here directly and that's how you manipulate things with applying and using functions to apply certain logic to your columns and your values。


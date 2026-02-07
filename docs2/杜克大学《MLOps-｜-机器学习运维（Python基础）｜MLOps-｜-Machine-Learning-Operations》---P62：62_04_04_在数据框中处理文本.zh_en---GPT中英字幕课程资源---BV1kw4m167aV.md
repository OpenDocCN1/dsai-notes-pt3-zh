# 杜克大学《MLOps ｜ 机器学习运维（Python基础）｜MLOps ｜ Machine Learning Operations》 - P62：62_04_04_在数据框中处理文本.zh_en - GPT中英字幕课程资源 - BV1kw4m167aV

![](img/6321284745faa5408c4bbb5b48486b70_0.png)

。

![](img/6321284745faa5408c4bbb5b48486b70_2.png)

Manipulating text in data framems is something that you might want to explore as well because you might find yourself in a situation where you need to manipulate the text。

 also called manulating textual data where you want to do some operations on the text and pandas definitely allows you to do that now let me start here by loading my data set I'm going create my data frame here have the same data set as before this wine ratings data set I've been working with now you can manipulate the variety so for example here we have varieties red wine and also white wine I know this data set has white wine as well。

 but I want to create a new column that has that is named variety short and you can see here I'm calling it variety short and that's going to equal or get assigned the product of this operation。

The operation here is saying go and look into the variety column so it's going to look at these column right here and replace the values of like I'm passing a dictionary here。

 anything that says red wine so you can see like this one right here is red wine youre gonna replace it with an R and anything that is a white one you can replace it with a w this is a text replacement and then we're going to be creating a new column called variety underscore shorts I'm going run these and you can see now that variety short is has been created。

 this is red wine， the first entry and you can see that the variety short is is r for red1 so that is one way of manipulating text with that replace but there are several others now we have variety short we've created a new new column but definitely you can you can do it in place as well you can you can。

Change the variety and replace it in place。 but I always prefer to add a new column because if I mess up。

 then I have a way a nice way of getting back to my original data set and getting into trouble。

 Allright， so with high confidence， I want to do something， something else。 you can see。

Here that the region sometimes see some county like Mendocino comma， California。

 I just want to stick with California。 I don't want to deal with commas。

 I don't want to deal with anything else but I know that almost everything will have something comma and then something else so this is of course me knowing the data set but what I want to do is I'm going to split I'm going to split this text on the comma that's going to create a list and I want to get just the last item whatever that is So if there are 100 commass。

 it doesn't matter just the last item in this case this would be converted to California what I'm going to be doing I'm going to create a region underscore short and then I'm going to assign the product of this operation now look how nice this is I'm going to from the data frame I'm going to select the region column and I'm going to do that STR for which is short from。

For string， that split， that's a split method， the Python split method and then that STR that get Now this is coming from pandas and that get is coming from pandas I'm gonna to say I want the index the last the last item on that split operation that's what I want to do and then because pretty much everything that I have is California I don't want I want to show you everything that is not California so you get to see what the resulting output is so I'm gonna have now a region underscore short and you can see now that I have things from Spain in Washington and no commas whatsoever so that said that those are a couple of ways that you can manipulate text or textual manipulation as a panda's documentation says it is and things that you can do for creating new things hopefully you can you can find useful ways of operating or even improving on some of these techniques for manipulating text。


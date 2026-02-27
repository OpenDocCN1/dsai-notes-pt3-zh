# 杜克大学《Excel 到 MySQL：商业分析（5课全）｜Excel to MySQL： Analytic Techniques for Business》中英 p75 40_07_03_最终项目说明（下）.zh_en -BV1mS421X7yw_p75-

![](img/8c70cec81564cc70a0b43fd41b49a56c_0.png)

![](img/8c70cec81564cc70a0b43fd41b49a56c_1.png)

I'd like to talk a little bit more about how you're going to do your final project。

You've got six possible inputs for your model。They include each individual applicant's age。

The years of their current employer， the years at their current address。

Their current credit card debt。Their current automobile debt and their current income。

What you're going to want to do is try different combinations of these inputs so if you just think of them as ABC。

 DEF， you can try each one individually and calculate the area under the curve。

 if they have a very low area under the curve close to 0。5。

 then you probably should just discard them at that point。If they seem to have some positive。

 discriminatory power。Then you could try combining them， so a plus B， A plus C， A plus D like that。

You could try combining three of them just remember if you do a plus B。

 you might want to divide by 2 or a plus b plus C， you might want to divide by3 to make sure they fit within the 3。

5 to negative 3。5 range for the standardized values。You can also try ratios of things。

And of course you can try weighted combinations， 0。7 times1 plus 0。3 times another。

 this is up to you and I've left this problem very open so that you can just experiment manually。

 try cutting and pasting and just try different things and see what works。I feel like this is a very。

 very good way to get some kind of intuition for what's going on when you're developing a binary classification model。

Once you've got a model that seems to be working fairly well on your training set。

Take that model without changing anything and try it on the next 200 individuals。The test set。

If your model performs much worse as far as its area under the curve。

 you've probably overfi the data on the initial training set and you're going to need go back and adjust your model so that the difference between how it performs on the training set and how it performs on the test set is not so dramatic。

Once you've got a model that's fairly robust， meaning its performance does not fall off dramatically when you move to the second set to the test set。

Then I'd like you to take a look at the。Threshold that minimizes total costs。

 You may remember that this is the total number of false negatives times the cost per false negative plus the total number of false positives times the cost per false positive。

 And so in the problem will' give you those costs。 and then you can find the threshold that minimizes the total cost。

 and you can report what your average cost per event is。At the minimizing threshold。

Then you're going to want to try running the model on the second set， on the test set。

Without changing the parameters， so you need to use the same threshold if your threshold is。2。6 or 1。

4， you need to use that same threshold， not the threshold that would minimize costs。On the new data。

 but the old threshold， because you have to remember this is。

To simulate a forecast when you wouldn't know the data already。

 so you have to use the old threshold and then you get an actual measure of your what your costs are at that threshold。

If that cost is dramatically higher than the cost on your training set， then again。

 you probably have overfi the training set data with an over complex model and you're going to want to go back and simplify your model。

 it's often the case that problems don't emerge at the area under the curve stage。

 they only become really apparent at the cost minimization stage。

So that's the first part of part one of our course project。

You are then going to look at various metrics regarding your threshold。

 true positive and false positive rates， of course。

 but also the positive predictive value and negative predictive value。

 and the information gain over the base rate associated with your model。The base rate is of course。

 what happens with the initial group where everyone is granted a credit card。

So you can think of this initial group as where everyone。Tests。Negative。In other words。

 no one is classified as a potential defaulter。And you have a large number of false negatives。

 those are the defaulters and you can calculate the cost per event of using no model。

 so we want to compare information gain of your model against the base rate and cost savings of your model against the base rate costs。

Then to make it a little more interesting， we're going to introduce an alternative source of。

Data Aertopia， which is a predictive analytics company that provides very accurate credit rating scores。

 these scores allegedly have an area under the curve of about 0。84 to 0。85。

And they are for sale for a lot of money and your boss wants to know。

 should the bank buy these scores？What you're going to do is you're going to use a test sample of scores calculated on the test set。

To calculate the。Optimal threshold and minimum costs using the very simple model of simply using the ranked acartopia scores。

 So this goes back to our。Cancer diagnostic where you simply have a single rank set of scores and you use those to predict the outcomes and set an optimal threshold。

You will then calculate the metrics。Positive predictive value。

 negative predictive value and information gain。For the aurtopia scores。

And I think what makes this problem really interesting is you can figure out how much the bank should be willing to pay for the Aertopia scores。

Either if your model did not exist， in which case， the alternative would be simply the base rate。Or。

How much they should be willing to pay if they already have your model and the data that feeds it。

 the six input variables。嗯。This problem is intended to make a particular point。

 which is that often when we do data analytics， we don't acknowledge that the current state of knowledge is the thing we need to improve upon。

 so agartopia would probably like you to believe that they should get credit for all the reduction in uncertainty over the base rate。

 but in reality they should be rewarded and compensated only for the reduction in uncertainty over the model that you've built。

 which I'm sure is pretty good。Part two of our final project。

Is based on multivariate linear regression and will require you to create a regression model for forecasting of a continuous variable。

And then to include in your explanation and your model。

 a measure of your error and the confidence intervals of your estimate。

What we're going to do is we're going to look at an interesting phenomenon in the credit card industry。

 which is that。Often， certain customers。Who are very profitable for the banks。

Are those that tend to run up large debts， really sometimes even more than they can afford and are making late payments and are struggling and often ultimately become defaulters。

 but it is possible over time for a customer that defaults to nevertheless be net profitable for the bank。

Of course， the opposite is also true if you have a customer that scrupulously pays on time and pays minimal interest and maintains a very small balance。

 the bank is providing the service of the credit card and receiving almost no interest payments。

But we're focused on the former scenario， which is。

Profitable customers that may nevertheless default。 And what we're going to do is look at。

The bank's records over the three year period for the 400 individuals that we have studied in terms of default。

 no default in terms of a new。Output or target variable。

 which is their actual net profitability or net losses associated with that individual。

What we'll find is that we need quite a different model from a default model to forecast the actual profitability of an individual customer。

Of course， this model will not be perfect， and so what we're going to do is we're going to end up with a model where you'll be able to say for a particular input。

This customer has a forecast。Present value to the Bank of blank。$2，000。

Plus or minus at the 90% confidence interval。X，000。That's how we'll structure the final answers。

 and this should tie together many of the important themes in our course in terms of the need to make decisions。

With uncertainty remaining in a problem and the responsibility of the data analysts and data scientists to quantify that uncertainty when presenting their recommendations to decision makers。


# 密歇根大学《使用Python的统计学（理解并可视化数据、因果推断、建模）｜Statistics with Python》中英字幕 - P85：19_边际逻辑回归.zh_en - GPT中英字幕课程资源 - BV1dV411Q7j3

![](img/928ad55b791c3e382f03f87a0cb371e7_0.png)

OkayWel back to our discussion of marginal modeling approaches for dependent data now we're going to turn to marginal models for binary dependent variables and focus on the case of marginal logistic regression we've already talked about marginal linear regression for continuous dependent variables now we're going to turn to the case where our dependent variable is binary in nature and we have reason to believe that observations on that binary dependent variable are correlated within a cluster that was introduced by the study design。

So recall about marginal modeling approaches， with marginal models。

 there's again no explicit interest in making inference about between cluster variants in the coefficients of interest in a given model。

Last time we introduced GEE as a general technique for estimating marginal regression models and accounting for the within cluster dependency in a dependent variable。

 and again， that dependency might be introduced by cluster sampling or repeated measurements over time on a dependent variable of interest。

In this lecture， our primary interest is going to be on population averaged marginal relationships between predictor variables of interest and a binary dependent variable。

 so just like we talked about for marginal linear regression for continuous dependent variables。

 our focus is on overall marginal relationships across all of the clusters that may have been introduced by the study design。

So marginal models for binary outcomes， GEE methods were specifically designed by Liang and Zieger and others to readily accommodate nonnormal outcome variables that were measured longitudinally。

 so where there are repeated measurements over time on the same subject that's being studied and we have reason to believe that those repeated measurements are correlated。

The mean structure in the estimating equation recall is defined by a given type of generalized linear model。

 so in marginal linear regression， we talked about how the mean was defined by that linear combination of the predictive variables and the regression coefficients。

 that's how we modeled the mean of that normally distributed dependent variable。

Let's consider the case of logistic regression for a binary dependent variable。

 so you'll recall from week two that the mean of the dependent variable in this case is the probability that the dependent variable is equal to 1 we're just talking about a proportion or probability that we're interested in modeling so we write that mean using the notation that we introduced for GEE the mu subti notation for time point T on individual I。

 we can also write that as the proportion pi at T and we can also write that as the expected value of the dependent variable y conditional on the values of the predictive variables indicated here by x subti so what is the mean of the dependent variable given values on the predictive variables of interest that's how we can write down that mean function for the generalizedestim equation。

In the case， the specific case of logistic regression where we're using that lowit length function to fit the actual model。

 we write this probability that the dependent variable is equal to one as follows we write that as the exponential of that linear combination of predictive variables and regression parameters divided by one plus the exponential of that linear combination of predictive variables and regression parameters。

 this is an inverse logit function that can be used to calculate a probability that the dependent variable is equal to one based on the specified model。

 so again this is where the beta parameters enter into the estimating equation。

 we write down that mu function or the mean as you see here and that brings the regression parameters of interest into that estimating equation then we try to solve for the values of those parameters that solve the score function。

Furthermore， when thinking about binary dependent variables。

 remember that the variance of a given binary observation。

 if we have a random variable that follows a Bnoulli distribution only takes on values of1 and0。

 the variance of that type of10 variable is the probability that the observation is one which again is the mean like we just talked about multiplied by one minus the probability that the observation is one or in other words one minus the mean so what that means is that the mean and the variance of the binary dependent variable are both defined by the specified model。

 as soon as we write down a model for that probability we have a model for the mean and we have a model for the variance。

 so in this case with GEE， our job is to choose a working correlation structure because we've already specified the mean of the dependent variable and the variance of the dependent variable with the model that we've indicated。

So given dependent data， we can then pick the correlation structure that we think makes the most sense for these binary observations。

 these clustered binary observations， whether it's due to cluster sampling。

 or whether it's due to repeated measurements on the same subject。

 it's easy to do this using GEE and recall that we have different choices for that working correlation structure。

 we could choose exchangeable， first order autoaggressive， unstructured or independent。

 and find which one provides the best fit to a given set of dependent data on a binary dependent variable。

So let's revisit the smoking example from N Hainenes。

 recall that we fitted a logistic regression model to the lifetime smoking indicator in N Haynes。

 have you ever smoked 100 cigarettes or more in your lifetime？What did we find in that analysis。

 well， in the multilevel approach we found evidence of variability between the NhanN sampling clusters in terms of smoking prevalence。

 and again that was when we fit a multilevel model to the smoking data。

So there was some evidence of within cluster dependency。

 we want to see if we see the same evidence when using a marginal modeling approach。

Now we're going to consider a marginal modeling approach using the GEE technique。

 and we're going to examine whether our inferences change when fitting a population average model that does not include those explicit random effects of the NHAN sampling clusters。

So the table that you see here on this slide presents the estimates of our fixed effect parameters in the logistic regression model of interest following both the multilevel approach and the GEE approach that we're considering right now and overall if you examine the estimates in this table we see no differences in the inferences that we would make relative to the multi-level modeling approach so you can see that our estimates of the fixed effect parameters for predictors like male and age and white or black or being of other race BmiI household size family income to poverty ratio the regression parameters for each of those predictive variables the estimates are very similar whether we're using the multilevel approach or the GEE approach and we've indicated which of these regression parameters would be considered significantly different from zero using the asterisks that you see here in this particular table so males are very important predictor you see that if you're a male。

 whether we use the multilevel approach or the GEE approach being a male increases the probability of ever having。

mked 100 cigarettes pretty substantially older people have a higher probability of ever having smoked 100 cigarettes probably makes sense in theory。

 larger household size， you have a lower probability of ever having smoked100 cigarettes you see the negative fixed effect family income to poverty ratio again。

 a negative relationship as that income to poverty ratio goes up you have a lower probability of ever having smoked 100 cigarettes and we arrive at very similar inferences。

 whether we use the multi-level approach or GEE and you can see that the standard errors which reflect the clustering of the observations are very similar using both approaches。

So remember that the multi-level model also included those random effects of the Nhan sampling clusters。

 we didn't include the estimate of that variance component in this particular table of estimates。

 but we also have that additional parameter in the multilevel models so we're explicitly controlling for random cluster effects。

 we don't do that in the GE approach remember we're just specifying a working correlation structure that accounts for the correlations of observations within the same cluster。

Now let's think about some model diagnostics， our nuisance estimate of that correlation。

 assuming an exchangeable correlation structure within sampling clusters was only 0。

01 and the corresponding QIC value for this model was 6284。53。Again。

 like we talked about in the European Social Sur example for marginal linear regression modeling。

 considering unstructured and first order autoaggressive correlation structures doesn't really make a whole lot of sense here because again we don't have a time element。

 the NHs was cross- sectional in nature， we had a cross- sectional sample of area sampling clusters。

 so we don't really have a time ordering of observations within same cluster doesn't really make sense to consider these correlation structures as alternatives。

So we fit the independence model where we assume zero correlation within the same sampling cluster。

 now the QIC value is 6284。05 notice that the QIC value is actually smaller for the independence model relative to the exchangeable working correlation structure that provides evidence in favor of assuming that observations within the same Manhattan sampling cluster do not in fact have a strong correlation。

So our conclusion would be that the correlation in the marginal model is fairly weak and accounting for it is not making a huge difference in model fit。

So what conclusions can we draw from this example marginally when we look at the overall population average or marginal relationship across the unhan sampling clusters。

 we find essentially the same estimated fixed effects as we did when we fit the multilevel model。

 so whether we were conditioning on the random effects like we did the multi-level case。

 or we're just looking at the overall population average marginal relationships we would arrive at very similar conclusions about the importance of the different predictiveor variables in predicting lifetime smoking behavior。

Accounting for the dependency， rather than assuming independence of observations within each cluster did not seem to improve model fit in this case。

 so while there was some evidence of between cluster variants in the multilevel modeling approach that within cluster correlation did not prove to be substantial in this case。

And remember， we still interpret the estimated fixed effects marginally across clusters when using a marginal modeling approach。

 we're not conditioning on what's happening in a given andhaned sampling cluster。

 we're saying across all the unhan sampling clusters。

 what happens as the values onpredic variables change？

So what's next now you're going to have the opportunity to practice fitting marginal models using GEE in Python and going through and interpreting the results。

 so you're going to be able to go through a Jupyter notebook and see how marginal modeling works in Python for both linear and logistic regression。

 you'll have a chance to play around with fitting these models in Python and walking through a careful interpretation of the results of a particular modeling procedure。



![](img/928ad55b791c3e382f03f87a0cb371e7_2.png)
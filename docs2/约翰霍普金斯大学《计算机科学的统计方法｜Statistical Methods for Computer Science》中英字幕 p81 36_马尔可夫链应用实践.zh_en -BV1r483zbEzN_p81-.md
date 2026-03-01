# 约翰霍普金斯大学《计算机科学的统计方法｜Statistical Methods for Computer Science》中英字幕 p81 36_马尔可夫链应用实践.zh_en -BV1r483zbEzN_p81-

Hello， I'm Dr。 Ian McClled Accenture today I'm going to be talking about an improved method to measure the daily COVID 19 transmission rate from incomplete data。

Specifically， we want to measure the daily reproductive number Rt。 you may have heard of RO。

 which is roughly the number of new infections for every case of COVID。

And we provide a daily estimate of RT in the presence of incomplete data。

There's a big data quality problem surrounding COVID with over 3，000 public health offices。

 county public health offices， many with different reporting standards and systems。

 about half the people that have coronavirus are asymptomatic， they spread the disease yet。

 don't even know that they're sick， there's insufficient testing resources。

 insurance plays an impact， as you'll see in some of the other papers at this conference。

HIPAA rules also affect reporting， there's delays in reporting so just when a case is reported it could have happened days or weeks earlier。

 there's inconsistent standards on defining what is a positive case。

 especially over time and there's no authority that the federal government has to enforce any of these standards or rules on county officers or state state governments。

 so this becomes a data quality and engineering nightmare and under this backdrop is where we're going to talk about how we can estimate a better reproductive number and better compartments of the disease。

So when the disease began， if you may recall， think back some months ago。

 we learned that data engineering and visualization efforts are insufficient。

 so the leading model that was presented in the US and you see in the upper picture here predicted a total of 60。

000 US deaths with the COVID cases declining to zero by the summer of 2020。

 clearly that did not happen， there was an alternate model that was also briefed to the White House cubic model that also predicted a rapid decline in deaths and when you look at these models these are empirical models they're basically looking at the trend and they're trying to to predict what that disease propagation。

 what that disease spread will look like， but neither of the models in the early days reflected anything about the transmission dynamics of COVID。

So so the peak and decline is an artifact of the modeling procedure。

 not what's actually happening with the disease Some of the key shortcomings are there's no consensus between the different models they all provide something different a lot of them are inconsistent over time and location so you a model in Wuhan。

 China is going to be different than in Florida in the US and even if you vary the time windows。

 the model parameters are going to change significantly as you look at different time periods and different states between even Florida and New York there's hyperlocal estimates。

 any accuracy is very short term for a matter of days and I would argue that these results are not mathematically or statistically valid。

So what can we do if we turn our attention to mechanistic models。

 mechanistic models are ones that impose your understanding of the disease dynamics onto the forecast of the spread of the disease？

But what we found is when you have poor data quality it leads to nonsensical predictions。

 so we took a model that was performing very very well proposed by arenas and colleagues and it was performing very very well in Spain and in Italy in the EUA EU but when we attempted to fit them to US data we had absurd results so if you look at the chart here。

 our model using that that basic same model that was working well in Spain and Italy is producing the blue line which is very very high model prediction the actual cases are being reported clearly is not being represented by this model。

And so we now learned that that is due to the initial conditions that we had or understanding the case counts of the true case counts of coronavirus was problematic。

So what you're seeing in the chart to the left is our estimate of New York cases of coronavirus and so the little circles that you see at the bottom here represent the reported cases of coronavirus in New York during this period of mid- Marcharch through May。

 and then you'll see the blue line is representing what we think the most likely estimate of actual true case counts are in this paper was published in frontiers。

I guess published a few weeks ago。So the problem is that because the case counts are so significantly under reportedported。

 the initial conditions for the model are off， and then that totally affects the model dynamics。

So we need to rely on a method that allows us to infer the missing data that we need to drive the model。

 and so we're going to rely on Bayesian data augmentation as a method to do that。

So with Bayesian data augmentation， we are going to use the death data as the most reliable data that's reported on coronavirus and there's a few reasons for that。

 but we're going to use the death data to then reconstruct a Markoff chain and then use Monte Carlo via a linear noise approximation to address the uncertainty in our estimates。

And we choose to use deaths rather than actual cases because deaths while some deaths might be misattributed。

 they're rarely going to go unnoticed and we can do a little bit have a little more confidence in that measure so what I'm showing in the plot here to the right is the seasonal average in the gray band this is reported in Washington Post seasonal average of deaths in the US and then the black line reports the deaths in 2020 and so what you'll see is there is a spike that occurs here in the middle of March going up through April right as this gets significantly higher and you see the area in the dark shaded area can be attributed to COVID deaths and the light shaded area is deaths that have not been attributed to COVID and what I would argue is because you see this line remain relatively flat here in the middle of March and then it spikes and the slope follows the slope of the increased excess。

What I believe， my interpretation of this plot is that we fail to account for some of the early COVID cases as deaths due to reporting standards。

 but most of these are attributable to coronavirus， however。

 we can get a fraction of which deaths are attributable to coronavirus and which ones aren't。

 and so we can use that in building our estimate of what we have partially observed even in that death count data and then we use that information to infer the rest of the disease dynamics。

For those that are familiar with the Markov chain， Markov chain basically assumes that people fall into one of these compartments of susceptible。

 exposed， infected， recovered or dead， and I know that there is this asymptomatic period so some people break the infected into been exposed。

 you're asymptomatic， yet infectious and then you're infected for our purposes we've just lumped them together and say。

 hey， you're still shedding the disease the virus so you are infected and so we are basically going to then have a transition probability that's estimated and this is a fairly known process in epidemiology of what is the probability that a person is going to move from susceptible to exposed to infected or recovered or dead。

And so then if we understand the death rate and we understand the parameters for transition probabilities from clinical literature。

 so these are more controlled studies， they've been replicated a number of times at this point。

 so we can have a lot more confidence in those and the references for those are provided in the paper as well as the parameters and I also show you the parameters here。

So the other thing that we need to do is because we have this death。

 we can use linear noise approximation， allows us to invert this equation。

 estimating the number of deaths through the Markov chain and allow us to estimate the actual true infection cases and we can go all the way back through for that susceptible to exposed and that gives us our ability to estimate the daily reproductive number。

So here are some of the results that we have。So this shows the compartments of the number of people moving in the first graph from susceptible to exposed。

 then from exposed to infected， then infected to dead。

 and then also infected to recover if you recall additional compartments and so what you're seeing is as we do Monte Carlo。

 this is generating a random draw of numbers and then going backwards through the Markov chain to estimate each compartment and so that's what gives you that light blue shaded area it shows you a bunch of the different trials and then the dark line is is the maximum anterior anti posterior。

And what you'll see is the dots here for deaths are the actual death count data fitting the model fairly well。

 let's look at that a little more in detail so if you look at this you can see that the circles are the actual reported deaths and this case I believe is for the state of Florida and so you'll see over time the deaths are actually fit very well by the smooth model from our estimate Now the nice thing we've also done is we validate it these model fits against serology reports these are random samples of the population and they are tested for antibodies and so then we can infer from that what you know because it's a random sample we can infer what is the true number of people that have been infected with the disease and of course that might still under report because you have several people that are asymptomatic and they don't choose to go and get testing and there's a number of reasons why why that's still undercounted。

If we look a little closer at Florida and we look at during the periods of the lockdown is imposed on when Florida was under state lockdown and we also look at when they' phase2 reopening it was right and so now keep in mind the dark line indicates the number of people that are being infected and the circles are the reported cases you can see massive underreporting during the initial lockdown of Florida through know April to May。

 so significant underreporting here， and then even in their second wave we can still see that that is under counting the number of cases of those with coronavirus in Florida。

So this also allows us to look at that susceptible to exposed compartment which allows us to measure the daily reproductive number and so when we look at the daily reproductive number over that same time period in Florida。

 we can see that there's two peaks and what's interesting Florida is an example that we see in many states you'll see that the first peak occurs。

And then there's a lockdown and what we observe is the peak in transmission risk as this peak and then drop off occurs days and weeks before any government imposed lockdown。

 and it does not appear that the government imposed lockdown hastens the decline of that daily transmission risk so it really begs the question。

 did the government lockdown really have an effect in curbing the spread of the disease。

 or is the same information about the spread of the disease that alerts people to take precautions and to stay at home and to wear a mask and to take other protective measures is that same information that's alerting the public also alerting the government and and it's just coincidental that the government lockdown occurs during this period of downturn it is clear however。

 that once those government lockdowns are removed too early in those states。

 you see people getting a false sense of security and you see an increase in daily transmission risk following。

Second wave。嗯。And so I do think that the lockdown still serves the purpose of employers that may require their employees to come to work and those employees want to be more cautious and more safe。

 they don't really have many options， so I think the government lockdowns do help under those conditions。

 but it is clear that that the peak and the behavior of limiting the spread of disease occurs well before government lockdowns。

Thank you for taking the time to listen to this presentation I provided my email address and that of one of my co-auors。

 Kevin Keran， I'd also like to thank Trevor Kt for his work on this paper as well。

 Thank you very much。

![](img/a8f545bc3b2a89d870e8cee3a844f2ec_1.png)

![](img/a8f545bc3b2a89d870e8cee3a844f2ec_2.png)
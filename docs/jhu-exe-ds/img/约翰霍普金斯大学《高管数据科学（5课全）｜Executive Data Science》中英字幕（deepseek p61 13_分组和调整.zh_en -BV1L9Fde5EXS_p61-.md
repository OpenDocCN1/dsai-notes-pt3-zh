# 约翰霍普金斯大学《高管数据科学（5课全）｜Executive Data Science》中英字幕（deepseek p61 13_分组和调整.zh_en -BV1L9Fde5EXS_p61-

Hi， my name is Brian Kaffho， and this is the lecture on Blocking and adjustment。So， let's。

Start talking about this problem by putting it into a context。

Imagine if you're looking at improving mobility among the elderly and you want to do this using Fi tracker so I think for me。

 the most famous fitness tracker I think is Fitbit。



![](img/634c0999fe670946b0bc96ab897e3cc8_1.png)

And you want the fitness tractor to serve as motivation for greater mobility。

 and you're going to do a clinical trial where you randomize half of your subjects to receive a Fitbit and the control subjects get nothing。

 but most clinical trials， then they get something like the Fitbit at the end of the trial。

To reward them for being in the study in case you're worried about that。

So you're worried that age would confound the relationship。And ideally， and more likely， in fact。

 the age groups would be distributed in roughly equal proportions among the treated and the controls。

 however， if you have a smaller study， something like this might happen。

 you might get at the younger age group。

![](img/634c0999fe670946b0bc96ab897e3cc8_3.png)

One person who is a control at the middle age group， three people one person who is a control。

 at the middle age group， three people who are control and the high age group， in this case。

 five people who are control in each of those age groups having six people。And then in this case。

 age will be alias with control status for the younger ages， fewer controls for the higher ages。

 more controls， and so if you were to look at the relationship between the fitness tracker and measured mobility。

You'd then be worried that it's actually associated with age。

So and this would be an unlucky arrangement and if you had enough subjects。

 probably things would wash out just by probability。

 but because you know age is such an important factor a priori。

 you might want to force it to be equal within your age categories。

 you might want to take and get six people who are age 65 to 70 and then randomize among those six people three to receive the treatment and three to receive the control。

 and this is called blocking， and it's basically the principle that if you know that an important source of explanatory variation exists as a variable。

 why don't you control for it at the onset at the stage of the experimental design。



![](img/634c0999fe670946b0bc96ab897e3cc8_5.png)

Let's talk about a related problem when you don't have control over the experiment or when you've conducted the experiment and realized that there was some sort of aliasing。

 so for example you might have conducted this experiment and actually there was an aliasing。

 what could you' have done？So you're studying the elderly still and you're comparing the use of fitness trackers with mobility。

 but you're just。You're just observing the collection of people who self select into using fitness trackers versus the controls。

And so you're worried about because it's an observational study。

 you're worried about lots of factors that might confound the relationship between mobility and use of a fitness tracker。

 however。You're very concerned about age and specifics so let's just talk about that one variable while we would note for a full observational study you'd be concerned about lots of things。

 but you're worried about the age distribution， the younger subjects are going to be more likely to pick up a fitness track or just because of level of comfort with technology and other factors like that and so you're worried any results you see are going to be really associated with just differential age distributions。

So what's the most common way to look at this to solve this problem。

 and this is the idea of adjustment。And so adjustment is the idea of looking at the relationship within levels of the confounder held fixed so we would look at。

 say， for example， the middle age group， we would compare the mobility with the age group held fix so we're still comparing like would like now we may not have equal numbers of subjects in that age group but we will affix the age group so age isn't varying in that comparison so there's lots of different ways to do it to do adjustment。

 but perhaps the most common and straightforward and easiest one to do is so-called regression adjustment and this is when if we want to look at fitbit or not as a variable in a regression analysis what do we do we add age as another variable in that regressional analysis and that performs a sort of adjustment and I'm going to go through some examples to show you but also going through some examples to show you that adjustment is why you can get strange things。

When you add a new variable into a regression model。So here's a pretty simple example。So here again。

 the gray people are people who self selected into using a Fitbit and the red people are the ones who the are the ones who don't use a Fitbit。

And the Y axis is a measure of mobility， and the x axis is a measure of age。In this set。

 in this example， you can look the mean for the gray faces is higher than the mean mobility for the red faces。

 so the unadjusted effect is large。As we adjust it。

 we see that there's this line of mobility with age， however， and those lines are parallel。

 we're going to stick with just the setting where the lines are parallel in our examples。

And the lines are parallel， but the difference between the parallel lines is about the same as the difference in the means。

 So adjustment didn't really do much in this case other than give us peace of mind that our fact wasn't entirely due to just differential age distributions。

 But notice one reason why the adjustment didn't change much。 First of all。

 the data really suggest that the lines are parallel。 But secondly。

 there's a large overlap at every age distribution。

 you see people with both control and having Fibits。 okay so at every age distribution。

 there's a lot of overlap。 So there's a lot of data to directly make this comparison。

Consider this example。In this example， the marginal mean。

 the mean for the red group disregarding anything， disregarding age is higher than the mean for the gray group disregarding age。

😡，However。When we fit the regression model with age in it。

 we fit two parallel lines and notice that the parallel lines would suggest that the gray group is higher than the red group。

 okay， that the Fitbit mobility is higher than the。Control mobility and what this is an example of。

 this is an example where the effect would actually reverse itself。

 it would have gone from a significant effect。But in one direction。

 to a significant effect in the other direction after the inclusion of age in our regression model。

 So this serves as an example to show why it is when someone's reporting to you to a data analysis and you say。

 okay， well， I'm concerned that age may be causing this problem and they run the analysis real quick。

 and the effect actually reverses itself。 It's because of a phenomenon like this。

 I would also notice notice， look at this particular example。

 another hallmark of it is there's almost no overlap。 There's no。

 almost no ages where there's direct data to compare the fitness trackers with the。

Use of a fitness tracker with mobility only in this sort of middle age range is there are just a couple of people who are overlap and otherwise it's basically the old people don't use fitness trackers and the young people all do use fitness trackers so this data。

 our results， our adjusted results would be heavily dependent on our model。

Here's an example where the marginal mean， the mean without considering age for the。Control group。

 the red faces is higher than that of the gray group again， they're lower。 However。

 when we adjust for age notice the lines appear to be the same there appears to be no difference。

 so this would be an instance where you would have a strongly significant effect if you didn't factor an age。

 but once you accounted for age in your regression model it went away okay everything just lied on the same line。

 so if you disregarded age， So this is just an example of again how your effect can really change after the inclusion of another variable。

 Oh， and notice again in this one there isn't a lot of direct overlap。

 a lot of instances of direct comparability between the groups。

If there is a lot of direct comparability， the adjustment doesn't tend to change much。

And in this case， here's an instance where the mean disregarding age of both groups is about the same。

But when we fit the model adjusted for age， the lines the two parallel lines were fitting would be quite different in terms of their intercept or the shift between the lines would be quite high。

 and so this would be an instance of when it went from a nonsignant effect。

 if we disregarded age to a highly significant effect when we thought when we included age。

The final example I want to make this point one more time and what I wanted to say is in this case once you fit the model there would be a big effect between the two parallel lines they look very different in this case。

 however one thing I want to mention in this case there's no overlap there's no ages where we observe both control and treated group or control and self-selective FiIbit users。

 so。This。Result would be all model and no data， right The comparison we would be making would be extrapolating a line from the gray group on upward and extrapolating the line from the red group downward So there's no data there's no data overlap to inform this decision So this is anyway this is something to think about that regression does not handle by itself。

 right it does not tell you。That the comparison you're making has a lot of data。

 so I think it's often good to ask the people that you're managing to do some basic plots in this case you would want to look at the correlation of age with Fitbit use and if it's highly correlated。

 then that's a problem right in this case you could perfectly predict their Fitbit usage by their age if they were above this middle age round they all used Fitbit and if they were below that then they didn't use Fitbit and whenever you can whenever that can happen whenever your confounder predicts your regression variable very well that you're interested in。

 then that's a problem。

![](img/634c0999fe670946b0bc96ab897e3cc8_7.png)

Okay， so thanks for listening to this lecture and I hope you learned a little bit about two common strategies。

 one blocking something that we do as part of our experimental design and another adjustment。

 something that we do after we've collected data to try and account for confounding variables that may contaminate relationships that we're interested in。

Thanks again， and I'll see you in the next lecture。


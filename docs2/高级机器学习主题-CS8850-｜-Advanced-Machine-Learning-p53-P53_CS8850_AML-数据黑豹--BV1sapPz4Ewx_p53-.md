# 高级机器学习主题-CS8850-｜-Advanced-Machine-Learning-p53-P53_CS8850_AML-数据黑豹--BV1sapPz4Ewx_p53-

![](img/6978755bd3f9652983cb40d3c9e077d8_0.png)

Okay， yeah， hi everyone so we are team data Panthers and I will be presenting like for this team。

 so our team includes Abdul Luwek Shiam， Pra Omar and Mesha， so next time。

So we will be covering all the like outlines like the professor told us in the like what the different points we have to cover for this project so next slide。

So the project we chose was like MOA so before going to the project I will like to give like brief introduction what what we are trying to do and what problem we are solving so in the past like when the like medical companies or doctors they were trying to develop medicines。

 they were like doing on hidden and trial basis so they were not not like very targeted so using like but we are in like 21st century and the method should like be improved so now with the help of like machine learning and like various technologies like computer vision and we can like improve like we should not be doing like head and trial method for discovery of medicines so in this challenge we are trying to like。

Medicines based on the disease like next slide， can I go to next slide？

So the aim of this like computation is to develop algorithms and train models based on MOA so MOA is like you can like in medical field this is a term called MOA so every doctor or every disease has like MOA attached to it like it is a like term for any disease so like say you have a fever so for that fever you will have MOA so MOAs like fever has some protein so you can assume like I'm just giving an example like say vitamin is responsible for fever so what will happen if like when we use targeted like machine learning algorithms to develop medicines we will try to like reduce that vitamin K so in the body so that it will like in the reserve。

AndWhat will happen is we will treat the fever， so this is will what we are trying to do in this project。

😊，So next slide。So as I told you MO is like mechanism of action。

 so it's a every doctor will have like MOA in his like he will know MOA of different drugs and you can also like like think MOA responsible for like drugs as in the case when you go to doctor he will specify drugs like 500 MG 250 mG it gets like this is the what doctor assumes when specifying like 250 MG it will be like less powerful what like how the drug reacts to certain organs to the body。

 this is what it is responsible for MOA this is like a global term around the world so it doesn't mean like in US it will be other term in India it will be it will be global for like every other country。

So next slide。So for this competition Kagggle gave us like the data that we used had 24。

000 samples and 876 features， they were like three categorical features and the training testing dataset has 4000 samples the label dataset contains 206 boundary labels and this is the metric that we used to like evaluate you can go on to the next slide。

So evaluation was done on the basis of log loss log loss。

 so we will be trying to like lower the log loss so in turn we will be having better predictions so this is like the cad metric that we willll be using for like evaluating the model that we developed。

And now Abdul will go on to the next like part。Can you hear me？Yes， okay。Yeah， so just going over。

 you know， some of the EDA that we did， so the three categorical。

Features that were in our data set were CP type CPp time CP dose these were just in terms of sample treatment duration of treatment and dosages and what we have here is a。

A chart showing the different amounts of or the count basically of each of the categorical data in both the training and testing date testing set and what you can see is that。

Is pretty uniform in terms of the training set and the testing set。

Just based off the categorical features， you know， we assume that you know our models would generalize well to the testing set。

So like Kshagra said， there are different ways that the mechanism of action of a drug is determined。

 so there were 772 gene expression features as well as 100 cell viability features and this just shows the distribution of you know some random features of each type and basically what it shows is that you know between the testing and training set that the distribution and density are pretty similar。

嗯。After you know looking at that， we also computed a correlation matrix between the different features。

 but we broke it down into you know correlation matrix of just the gene expressions as well as of just the cell viability and then one with both combined and basically what you see here is that the gene expressions they weren't。

I mean， there were some that were very highly positively correlated。

 as well as some very universalversely correlated of the。

Of the 772 squared feature or what this matrix shows there's only 27。

000 that you know were highly correlated or highly inversely correlated。

 meaning that they had a value above 0。5 or negative 0。

5 and the highest correlation positive correlation was 0。9 and for inverse it was negative 0。82。

Similarly， this is for the cell viability， these features were very highly correlated out of the 10。

000 correlations you see here， 9，228 features were had a correlation value of 0。5 or higher。

So and the highest correlation was 0。9 and the lowest correlation that you see here is 0。6。

So this is a correlation matrix of all the features， so there's like 760。

000 correlations here and of those 81，648 or had either a highly positive correlated value or a highly inverse correlated value。

And you know that's pretty straightforward so moving forward to the training data set labels。

 so this was a multi label classification and each label was a binary value meaning 01 so there were samples you know。

Across the 206 labels that could be identified with that drugs mechanism of action。

 it could all be zeros or there could be one， one in there or two ones or how many of but basically 9 close9 close to or 9367 of these samples had all zeros there was 12500 samples that only had one one in the entire。

I guess。Prediction and so on and so forth and here we just have on the bottom left。

 we just have a frequency chart of the most。Frequent target。

 and on the right side on the bottom is how many。True targets there were in each of the labels and so you can see that there's quite a large imbalance the biggest one I think here was 732 and the smallest one was like one。

So to basically reduce the number of features we did both PCA as well as various inflation factor。

 is used to measure the multi colineity between multiple features。So。

Basically what you can do is you can take your correlation matrix and I believe I believe the question was one over1 minus r squared where r squared is the the correlation value from your correlation matrix and in general when you're doing variance inflation factor when you get a score for one when you get a score of one it means they're not correlated between one and five they're moderate moderately correlated and one is greater than five you is highly correlated there's a couple of notebooks we looked at you know people using this methods and what their cutoff range was some people use 15 we decided to use 10 based off of this distribution that。

We computed from all the VIF scores， so if when we chose 15 we only dropped 30 features。

 but when we chose 10 we dropped 90 features。嗯。For principal component analysis to standardize the data set。

 we went with quant transformer originally we did。Like a Minmax Gaalr which you know didn't necessarily you know subtract the mean and after you know looking at some other notebook C and discussion posts people found that using quantile transformer with you know a set parameters that they described you would get the best results so we went ahead and also use quantile transformer for that and basically with quantile transformer you can you know transform the features to you know follow a uniform or normal distribution so on the left here you see the unormalized distribution of the column means in the middle it's using Min Max Gaalr and on the right is with the quantile transformer。

So to determine how many components we would use。First， we figured out how many are。

How many components are needed for a range of。Cummulative or the cumulative explained variance。

 so we measured how many components were needed for explaining 85% of the variance all the way up to 99% and。

In the end， what we decided to do was choose a number of components that explain 95% of the variance。

 and this ended up giving us a total of 607。Priinncipple components， so we basically drop。

Another100 or in total we dropped 177 features from our data and on the bottom is just discrete plot here I know it's kind of small it's just because you know we have so many features。

So the component with the greatest or which explains the greatest variance。

 explained about 12% of the total variance。So now coming to baseline models。

What we did with baseline models was we computed K andN decision tree and random force and I'll get to another part where we did some more baseline models but that there's some more explaining needed for that but basically the correct baseline models that we used were K andN decision tree and random force and we kept the data as multi label and we did hyperparameter search we did just a regular nonparameter search model we also tested the baseline models on our pre-proces data which you know includes the PC and stuff as well as just on the raw data and what we found was that you know they weren't giving us you know the best of results and。

What we did here and these are basically the results of that and let me just you know run through once so you get an idea of you know what the scores here mean so basically we split data into 8020 split and so our Y test had a total number almost a million predictions that you know it needed and the number of you know true targets which we're just calling one here was only about300 or 3428 and so our model for and this is just the canN without parameter search on the preprocessed data it predicted 781 ones and this isn't you know。

If it predicted in the right spot or not this is just you know how many ones there on the day set and when we use the kgel metric which we which was offline we didn't submit this we got a value of 0。

1 we also you know just for。Added intuition or whatever you want to call it we use SK learners log loss。

 we calculated the accuracy and the important thing to note here about the accuracy is that since you know most of the。

Samples are have all zeros for the labels。 If we just predict all zeros as the predictions。

 we get an accuracy of 38。57。 So that basically means there's there's roughly 38% or 39% samples that are all just zeros。

 So， you know we're only accurately predicting。8ight or  nine% samples that have， you know。

Anything besides zeros。We also compute heming loss and zero loss。

 so basically 2554 of the individual bits were misclassified and for some of these we did compute cross or we did do cross validation。

 not nest cross validation just because of computational time and complexity but basically that's where we're at with the baseline models and this is you know another。

Thing we did， which was a mistake and I guess a learning curve really。

 which was that when we started we in， you know。Look at the evaluation metric as much so our perception was that you know it was just trying to get the best accuracy accuracy in terms of。

 you know getting the same labels as you know your test set your ground truth So for that what we did was use something a method called label power set basically you're training all your multilabel。

You're turning your multila classification problem into a multiclass classification problem and the problem with that is instead of predicting probabilities for whether or not a prediction is one or zero you're basically saying is zero1 and what the problem with that is when we submit it to KeGL and they're using their mean or mean columnized log loss function we're totally confident in our predictions and that leads to you know very large mistakes or losses and so。

We didn't realize this until like you know halfway and by that time we had already tested you know okay and then decision trees。

 naive Bays， random fours， multiple neural networks and even with the neural networks we did balancing methods such as random random under and upsling。

 we even used Smote and other methods we tried different neural networks， parameter。

 hyperparameters and such so basically the lesson learned here was to make sure you understand scoring method。

And but the one thing that we did note about LeO Poweret that was that if the metric for evaluating the models was based off of。

 you know， accuracy score or how if we're getting the same。

Label array as or if we're predicting the same label array as the ground truth。

 then label poweret was doing much better。And I'll pass it off to Ruth Figow。Okay， hello。

 I hope everyone can hear me。Okay， so like when we were experimenting with neural networks。

 the way we started it was。We looked at some different backs that have been implemented by some other people and some other teams in the competition。

And based on those， we started building our own。So at this point， we did a hyperparmeter search。

 but we only used 15 fits as it was。We a really long time。

We didn't end up with some great results with the parameter search like we have a few that that have been listed below。

😊，But later what we did was we had multiple notebooks that we were testing。

 we had a good line of communication with all the team members。😊，And based on the scores。

 we kept on improving the score。And that's how we started experimenting with different parameter values just getting move to the next slide。

😊，Even though we have we have a lot of different versions of the notebook that we done here we listed a few。

That we made official submissions to CAL。So what happened was。Initially。

 we were rounding off our predictions， so our k score was a little off。We were off by about 0。

08 from the top team。But later after three four atoms。

 we realized and we experimented by not rounding up and that reduced our gap tool about。Pot 02 or 0。

02，0， something from that range。And later we were only depending on accuracy at that point。

 so what what weed later was we used loss log loss matrix fromcal learn2。😊。

To compare our performance initial stages， it worked well。

 we tried reducing the loss and it correlated with the kgle score and we kept on improving our。

Score as well as the rank， but after a lot of experiments。After at some point。

 even the logic for maskelon didn't help us。So this is the line that has been highlighted was our best。

Apartments。So our kL score was 0。0174 right for this， I think we were off by。0015。

The margin was pretty less， but I think。We could do what。In the time frame。

 you managed to do the width。I think the time is running out， so I'll just pass it on to Press well。

So as we were already good good with the neural networks results， so I say like it was not too great。

 but we figured out that our neural networks are giving us a pretty good results。So but still。

 as we have already mentioned in the midpoint presentation that well be using the XG boost models or something like that。

 so we tried using the another boosting technique called as a light trading boosting machine which is a gradient boosting framework based on a decisionion trees to increase the efficiency of the model and also it reduces the remember usage。

In this model we also used the stratified Kfold， which is one of the techniques uses the it shuffles the data and splits the data into n parts。

 so this idea we have gotten from one of the kgel competitions which was for the multilabel data set。

And based on。The experience we have done， we have gotten the results as like this was one of the this was the best score like 0。

017990 in on private leaderboard and 0。02063 on the public leaderboard next slide please。

And this were the another Kegel submissions we have done。

 so as already the Abdul mentioned the baseline models we did a couple of experiments with the label power set and the label poweret neural networks and all but we found that our neural networks are performing pretty good and we got the best performing model as the neural network so which is in the next slide I have mentioned it。

So just keep over the next slide。So these are some of the Kegel submissions we have done next slide please。

Yeah， just just get to the base perform that top perform， yeah。

So this is our rank we stood 2862 on the kgggel and as Rudig already mentioned that we were just 0。

0015 points away from the top performer model in the kegel Comp。Next slide， please。

And this is our can burn flow。Next slide。And these were some of the gi commits we have done。

And our paper draft we have not yet shown here， we thought that the deadline photo show it is6。

But we are also working on our draft and we'll just present it soon。And。Yeah。

 that was for our presentation and we just concluded with this points that as professor has already。

Tt us in one of the lectures that there is no fixed way to do the machine learning。

 we have to keep exploring the different models and which we have to check the performance based on the different metrics。

And here we explored so many models and we found that we should organize the things very well。

And another thing we learnedt was。If we get some chance to redo the things。

 we'll first spend a lot of time analyzing what exactly the objective is and then we'll make some plans to work and so that whatever the time we spent on exploring。

 we could have saved it。And I think we are already。I think yeah， the time is already yet to。

 or I guess yeah， it's it's is time， yeah。So that's all from our side。

 if you have any questions you can we are happy to answer them， thank you。

If you allow me again to go with my questions first yeah thank you nice nice presentation。

 I like multiple pieces there but。What is the architecture of your neural network？啊。

So for the neural networks， what we first started off by doing was looking at a couple of different notebooks that people submitted。

 you know。What the architectures were like。 And so we tested those out。

 We did our own grid search cross validation on that。

 we tested those out and they didn't perform so well。 So then we。Just created a basic。

Format for a layer and after that what we did was basically sequentially adding more layers and changing different parameters and basically experimenting that way until we got to a point where we realize that this is a number this is how many layers we need all we need to do now is figure out what the hyperparameters for like dropout activation function and stuff like that should be。

That doesn't quite answer my question， so let me try so we have。Convolutional we have fit forward。

 we have what capsule network CNNs transformers a multi layerer perception that's what we were doing so it's just a fit forward neural network with different layers so it's basically okay no linear regression or multila and when you say multilabel you mean that simultaneously you need to predict multiple classes or size okay。

Did that help or did you try or think about like ensemble of models each one predicting one label separately or there were just too many？

So originally the plan was to try out like。Label power set chain classifiers and I forget last one。

 but by the time we got to finishing label Power set and realizing it wasn't the way to go。

 we shifted gears to you know MLP because we were noticing a of lot more notebooks at that time coming out with using neural networks and models like that。

Okay， good， another question。So it's a fit forward so basically your。Exploration was。

The architecture of a feed forward network， right。And another question。

 I really like the part about data exploration where you actually looked at everything and how it correlates。

 but it feels like all of your features， all of those gene profiles of whatever you correlated they're all correlated and usually correlation between features is at worst。

 it can lead to。Like bad the results or completely like inability of model to predict because the model will get stuck in local media because this region where features that matter everything is the same and it will just dwell in the feature space where everything is the same rather than finding the features that matter and at best it's a waste of computation so try have you tried to do something about it did was it there or I missed it or like did you just。

Originally， when we were first starting out， we did the PCA。 And after that。

 all the models we tried were just on the。Reduced data set right but then we started you know just messing around and trying to see if you know if we took the raw data just the way it was and to see if that you know gave us an improvement and for some of the models it did especially for like the neural networks we found that when they had the raw data as it was they did much better than when they had our process data with PC and。

VIF。And so last question it's mainly about the class and the processes so like you started like it's unclear why did you use accuracy at all like is it accuracy per label like I wonder if the class on model the lecture on model comparison came too late in the class and it wouldn't have helped if I moved it forward somewhere or or that wouldn't have helped what do you think about your fellow students next semester should I move it to an earlier place in the class but I feel it's like a more advanced and a different thinking there's actually a couple of lectures that you know I think might be useful ahead of time。

 especially like the crossvalation ones like the hyper hyperop and all those other tools that we use you know we kind of learned those towards the end and by that time we already had computed a lot of the models but in terms of。

Why we were doing accuracy in the beginning。Me personally， I was new to Kegggel。

 so I didn't you know。Really look at， you know， how they were evaluating the model and everything。

 I was just， you know， my my， my intuition was， you know， predict the same。

Label the way it is this this is a fantastic lesson， by the way。

 always just do what your stakeholder is paying for and I mean then you'll have a successful project。

 but of course mind。😊，It leads to it leads to kind of optimization or playing you know the system。

 but sometimes it's worth playing with system you know， gaming and getting your yourself established。

 even if you know it it may be stupid with。Yeah， if the market requires you do that and then figure out your own way。

 Okay， interesting we have 10 minutes other questions from other people。In the class。

 please go ahead and ask your questions。I don't have a question regarding the presentation。

 but I had a question for professor。 Is that okay。Can you hold it until we're done with the presentation questions。

 I really hope you ask the questions because。Well， okay。

 those people who don't ask the questions will feel how next time they give a talk and don't give get a single question from the audience。

 please remember today that you didn't ask a question and make the other people feel bad but please hold your question and let's ask questions that are presentation related。

Come on， anyone。Do you worry that systems like that from both of those talks could replace your personal doctors someday？

If you don't make it through and your insurance will not cover live doctors。

Or are you happy with that？I ask questions， is that going to stop that from happening？Wellow。

 you can try。You can， can can bring it， you can motivate these people to work harder and make this future you know。

 to come sooner。I just go live a hut in the woods。Well。

 have a sharp knife with a saw that event so you can。Soaw your head， oh I mean。

 you leg off when you know， you get in trouble， I mean， it's just like， you know。

 you have to be prepared。Well then don't worry the robot drones surgeons will chase you and save you in time。

 but really what I got from this too since you don't have any questions。

 it feels like a lot of medicine is highly correlational or like。

It relies on large data bank of the doctor of the cases that they've seen before。

 and maybe we can automate some simpler cases when the models learn to give us confidence in what they predict and the confidence is actually correlates with success。

Maybe maybe it it's easier to have a， you know hey Alexa， what am I having now。

 what pill should I take rather than wait for a month in line and I know the cases and especially in US medicine where people lost their hearing because they couldn't get assigned to a doctor when they had ear pain and things like that by the time they got there it was too late so the systems like that could help but。

Okay， anyways， if you don't have any questions， even unrelated ones。

 but to the team like Jack just had， then I'm open to answering one question or okay， two。



![](img/6978755bd3f9652983cb40d3c9e077d8_2.png)

Let's stop well， if this is not related， let's stop the recording then。


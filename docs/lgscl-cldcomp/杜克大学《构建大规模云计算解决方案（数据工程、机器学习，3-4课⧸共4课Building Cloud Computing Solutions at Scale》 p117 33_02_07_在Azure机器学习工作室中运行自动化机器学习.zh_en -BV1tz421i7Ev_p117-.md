# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p117 33_02_07_在Azure机器学习工作室中运行自动化机器学习.zh_en -BV1tz421i7Ev_p117-

![](img/d1d9ef80ffb10b7601858cad74665687_0.png)

So we're back on Azure Machine Learning Studio and I'm already like this is the homeage for Azure Machine Learn Studio。

 I'm going to click there。 We've tried to but we've done an overview we've tried to get a couple of datasets。

 let's take a look at datasets and where we're at right now we have Github dataset wine ratings。

 But now we want to get started with the automated MLl or automl run。

 So if I go here new automated MLl run and we want to get started。

 we have our Github dataset wine ratings there。 we dropped a couple of columns that were useless So we can click this one。

And then we can click next。 So now we have all of our data sets here。 perfect when I click next。

Let's see what happens。 There you go， it loads。And it gives us an overview on how to configure the run。

To recap we wanted to start a new automated ML run。

 we've gone and selected the type of data that we want。

 we've imported that data into Azure and we've selected what comms are important to us and how do we want to deal with those we've dropped a couple that were not very good。

 not very useful and now we're ready to configure this run。 So we we have selected our data set。

 Github data wine ratings。 again， that's coming from these raw URL。 So we got go back。

 this comes from this repo。If I go click here， that's the。As it comes。

 he comes for it with a Jupyter notebook that is pretty useful if you want to check it out and。Now。

 again， we're back to con。 So we have the data set。 We need to select an experiment name。 Well。

 I want to create a new one just to be distinct。 So new experiment name。

 we're to say demo wine ratings。 And then we're going to be selecting a。Target column over here。

 We're gonna say， well， we have name region right。 I know the data setting inside it out because I created。

 So I think it would be pretty cool to like， this is basically a data set that talks about different wines that come from different。

 that have different names and regions and varieties in rating and notes。

 I know that the rating is pretty useful。 So I'm gonna select that。 And then I am。😊。

Going to do let's see select compute cluster。 Oh， oh no， we have a problem here。

 We don't have a cluster。 Well， I've just created this one， but I have that one。

 But let's just go through the various different details that will explain how to that。

 So now you can either create a new compute。 or you can。

 you can actually go to here on the left on manage and select compute。

 Let's actually go and open a new tap in there。 I could do it here。

 but like I don't want to stop and and get started with here and with this automated Ml run configuration。

 I'm gonna click here and。😊，I'm gonna open a new tab。

 And so you have four different types of compute that you can create compute instances。

 These are pretty good for， for Azure machine learning notebooks， Very interesting， very good。

 what we want is a compute cluster。 Now， if you didn't know where or why you need to create。

 if you go back to start run。 if you click here， create new compute。

 that will take you directly to compute clusters。 If I click here， I'm gonna to click new。😊。

And then we start to see some of the details that are pretty interesting Alright。

 so lets let's talk a little bit about what's going on。

 what do we need here So it's a virtual machine that that's basically what you're getting what you're configuring and there's a difference between dedicated and low priority let me skip this for now and let me come back to it later in a second。

Brch machine type is like if you have， if you have a preference for CPU or GP。

 well you would select that here， CPU for now is fine and now you are getting to the sizes。

So by default fault， it selects standard DS3 V2， which is four core 14 gigs of Ram and 28 gigs of storage。

 The category is basically generic， I don't know， like if I can consider category， yeah。

 general purpose， workload types， classical MLl model training， RMl runs， pipeline runs， etc cetera。

 This is the default full compute。And I don't like it that I can't。I can seem to make this a nice。

 Well， it's 20 cores and。Let me make this a slightly， slightly。Slightly smaller。

 So you can see what we're dealing with。 This might be a little bit small， but it's fine。 I'll。

 I'll make a bigger in in a second。 This is 29 cents an hour。 That's not really bad。 Well。

 you can see that the maximum monthly cost would be。 What was it。It was like something like 215。

 Yeah，$215 a month， however。Like I really like this。

 I would like to go to like step it up a notch and get something better I don't want。😊。

I don't want like 37 cents an hour。 so if I scroll back up here and I say low priority。

 and I want to put this here so you can check what happens。So now this went from 29， what was it 29。

 so let's click dedicated yeah 29 cents to low priority6 cents and the one that I want to step up to is 7 cents an hour。

So that's significant。 What is the difference， Well， if we click here。

 low priority rich machines are cheaper， but don't guarantee the compute notes。

 Your job may be preempted。 That means that you might。

Be waiting a little bit for your jobs to to run to be executed。

 to be scheduled so I mean or rather they'll be your jobs will be scheduled。

 but they'll take a little bit longer to run because perhaps maybe there might not be notess allocated for you versus dedicated where you're like paying a from for that exclusivity。

 I want my notes to be up and ready and enable when I want them right when I need them。

Low priority is an excellent way of saying， hey， I want to create a cluster with a bunch of powerful nodes。

 So let's， let's click this one。I'm gonna pay 7 cents an hour， which is pretty ridiculous。

 So it's going to， if I run these for a whole month， it would take me 52 bucks。 Not that bad。

 So let's click that one next， Comp name。 Let's say sometimes I tend to name these compute names。

 You can name anything you want。 You have a cap at 20 characters。 I think。 So you can do standard。

's see， I tend to name them the same B B2 that way I know exactly what they are。

 but you can name them anything。😊，'s it's fine really anything that describes what you're trying to create here。

 Minim number of nodes is nice because if I if I do one， you will see what happens here， one boom。

 you get a warning to avoid charges when no jobs are running set the minimum notess to0。

 That means that hey， if nothing's running， I don't want any nodes available。 you know。

 So now you're you're a little bit like tweaking around and saying， well。

 what's what's useful for me to have essay as a minimum。 I tend to use them set them as0。

 I don't I don't I don't need to have like any number of notess ready and available for me。

Maximum number of nodes well you can you can certainly see the elasticity of the service here。

 the more number of maximum nodes that means it can grow up to that number of nodes So if I go say two or three or5。

 it doesn't matter。You you might get into a CA situation where things might not be set to you know your account might not be set to have that number of course course are measured against your quota so that's something to keep in mind I usually do for for the type of trainings that I do an idle seconds before scale down it means like hey if nothing's running if I don't have anything scheduled wait these many seconds before starting to get this number four all the way down to number0 and that's pretty much it like I usually don't enable SSH access。

 I don't have a virtual network。Thing to configure or to enable or to assign a managed identity。

 These are advanced settings I don't。those， this is pretty useful。 And then you click create。

 And then the one thing， though， is that that takes a while， that takes a while to run。

 So I've created， look at this。 I've created this demo cluster before。

 so we can certainly use that to start running our our auto and automated MLl run。

 So if we go back here to start run， we have。😊，This is where we left up before going to the create new compute。

Settings， so if I click here， you'll see only demo cluster is available again。

 if I go back to my compute clusters， demo cluster is this one。It will say， you know。

 like that's provision in state succeeded， there's zero nodes running if I go back。

My standard D is 12 v2 it succeeded as well and nothing is running andqui no count is0。

 So if I go back here and I say hey demo cluster just use my demo cluster I'm going hit next。

Now we're getting into how we're going configure these ML run。 So classification is fine。

 when I predict one of the one category， which is like yes or no， blue， red or green， that's fine。

 that looks accurate， that's what we want。 We're not doing regression or time series forecasting when I click finish。

 and now it's going to create a new automl run， which is pretty pretty nice Now it's not started。

 let's take a look at it's using the demo cluster。 So if go here， it's not using that one。

 This is my tab where I have my compute， So if I go to demo cluster。It will see that is。

 it's kind of like everything's idle， right， like everything's like nothing， well， not idle。

 like nothing zero usable nodes。 like let's hit refresh。Let's， let's hope like something is moving。

 well， nothing is moving if I click runs。You will see that something has been scheduled already for 21 seconds。

 I created it start time is running。If I go to notes again。Seerro par node。

 So that's the thing when you're， when you're configuring these node， it will take a second。To。

 to run。 So that's it。 That's how you associate a a compute cluster with your auto automated M L run and how you configure it to。

 to， to associate itself as well with a data set that you may have created previously。



![](img/d1d9ef80ffb10b7601858cad74665687_2.png)

![](img/d1d9ef80ffb10b7601858cad74665687_3.png)
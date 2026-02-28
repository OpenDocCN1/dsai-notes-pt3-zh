# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p137 53_03_08_Azure自动机器学习AI预测.zh_en -BV1tz421i7Ev_p137-

![](img/75a7bbef7b6a0048047f4df76241a480_0.png)

If we go to Azure here。And I go to。A home。And I go to machine learning。

 One thing that we could do that' that's kind of neat is that I can。Go to。

 let me show you like an a workflow for computer vision。 that's pretty easy。 So I'm going go to。嗯。

Some NBA data that I have。And I'm going to download this NBA data。Which is here。

And I think it would be。This is a good bit of data。 So this is some MB data that has。Players。

Positions， that kind of stuff and also。3 pointers and。Salary and Wikipedia date。

 all kinds of fun stuff。 So I'm gonna， I'm going to go to this。



![](img/75a7bbef7b6a0048047f4df76241a480_2.png)

And I'm going。Download this。 So yeah， Twitter recount， salary， all kinds of good stuff。

 So so I'll go here and just say a file。Save as。

![](img/75a7bbef7b6a0048047f4df76241a480_4.png)

And let's say I want to predict salaryri for an NBA player， what I could do。

Is go to a Michel workspace。And then。Launch the studio。And then go to this AutoMl as well。

 So I'm going to click on start。And then I'm going to do a new AutoL run。

And if I click on the new AutoML run。I'll show you the end result， which I did earlier。

 but I could say create result and say from local files， from datas， from web files。

 from open data sets， but I'm going to say from local files here。And I will say NBA。salaryary。

And it's going to be tabular data。And I'll just put the same thing in a salary。I'll go next。



![](img/75a7bbef7b6a0048047f4df76241a480_6.png)

Use existing。Da storage。Goqiu。😔。

![](img/75a7bbef7b6a0048047f4df76241a480_8.png)

Upload this tabular data。Go ahead and say next。And once I say next here， I can say。

Use headers from the first。File。And then I could say next again。And this is a schema， right。

 these are all the different things that are in this file。If I say next， it's going to say。

 do you want to create this， sure I'll go ahead and create this。And now。If I go to NBA salary。

OneWe can kind of look at all the different statistics of this， which is pretty cool。

If I needed to like each of the columns， it already generated all these descriptive statistics。

 which is actually pretty helpful。shows me how many are missing， for example， if I wanted to。

You know， see。You know， what are the missing count of things？And。And I guess if I go to salary here。

 which is one of the more interesting ones。Let's look at the salary in the MB， so the distribution。

Here。😔，Is that there's a lot of people not making。More than 3 million。 so 0。06 or 3。

 and there's a very gets smaller and smaller and smaller。 there are some people making this was。

 I think 2016， but there's people making 30 million same with page views right。

 These are the Wikipedia page views， but the reason I was showing all this is I could select this and I could say。

Next。And I can say。Create a new experiment and say predict salary。Like that。And。

I can select the target。 I want to predict how much money。People are making， right， salary。

In millions， and I'm going to select this demo cluster。

And then I could choose here what is the kind of problem that I want to solve is it classification right this would be categorical yes。

 no， blue green and do I want to do deep learning or is it regression so in salary it would be regression because it's the continuous numerical value or time series forecasting。

I'm going to go ahead and select regression and then say finish。

 and then it'll go through and it'll build this out。

 So this is again another thing that you could do is you could you could。

You could actually just spin one of these up。Upload it manually and then call via the Azure Python SDK and get the results and then put that into a flashask gap。

 which I think is actually pretty interesting。Now， let me show you， I ran this earlier。

 so I think I have this result here completed。And let's look at what happened。And we can see that。

That it went through and it ran a bunch of different models for me。And so inside of this model。

It was able to do a voting ensemble， so it picked a bunch of different types of models to try to predict who would be paid the most money。

And if we look at this explanation here， we can see that。

It was able to to come up with a pretty good results here。 So if I go back again here。

 we look at the。The correlation that view other metrics， we see that。The R squared is 56%。

 which is pretty good。And here's our spearman correlation， explained variance。

 mean absolute error is three。 so basically。嗯。We were we were able to come up with a prediction here and if I look at the explanation。

 what is it that explains？What are the things that explain the most in the MBA who gets paid what。

 and so what we can see is that it looks like free throws are the most important feature。

 which is nonintuitive， right， the second most important feature would be age。

And then minutes played， which I guess is somewhat intuitive。

 but what's also interesting is look that defensive rebounds and then also social media right so we can see that actually Twitter and Wikipedia are actually more important than field goals attempted。

 which is very surprising right that or two point attempts so we can see that。Somehow。

Potentially even their importance as social media stars plays a role in what they play。

 and we can look at the absolute value as well。And we can see that， in fact。

The worse you are at free throws， the less money you get paid。

 which is actually very fascinating and then the more this is I mean。

 massively important to the model and。If we look into this。

 we can see age is kind of equally distributed both positively and negatively to the salary And then the minutes played is kind of similar。

 And then also we can see that page views in Wikipedia。

 So so this might be an interesting thing if I was the agent for。And an NBA player would say， hey。

 you need to make your free throws， this is one of the most important factors in getting paid millions of dollars per year。

So then again， you can actually go down and use the。You can actually go to。

What is it if I go to Azure Python SDK here？呃。For Azure ML， you could easily call flask from this。

And you could call into that endpoint and you could list the experiments。

And let's just look at the reference here， so you would you would。

If we get to this experiment right here。You could call into this experiment。In fact。

I could try that real quick， let's see here。If we go back to。

We know that this experiment is called NBAA salary。So let's try that。

 let's see real quick if I can be brave and see if this works。



![](img/75a7bbef7b6a0048047f4df76241a480_10.png)

So， I will。ItIt's not。That confident， but let's just see if I can really quickly programally call that experiment and see how we could hook into it。

So I would provision a cloud chill。And look at history to find like a。Here we go。

 here's a virtual environment I have。And then I would probably do。

Maybe like either i Python or a script， probably in this case。嗯。H Python might work。

And let's see what the API call wants。

![](img/75a7bbef7b6a0048047f4df76241a480_12.png)

Yeah， we may not be able to。To do this but let's see so it needs a workspace object。So。

Let's try this， let's put this next to it。Go here。 So you would say。



![](img/75a7bbef7b6a0048047f4df76241a480_14.png)

From Azure import this。And then I also， I think you have to import the workspace object。

 which shows the space that I did this experiment in。So， I think it's from。Asure core dot。Let's see。

 I might have one。Workspace from config。Me， what is that？Let's see if we can get this working。

I'll briefly try this to see if I've got something in memories here somewhere。

I thought I did have a list。A workspace。That looks pretty good。

So I just have to import the workspace so it's say。From Azure。Cool， so from it。还是。Ml dot core dot。

Workspace。Import workspace。Hopefully， it's like that。B from Azra Malcour。Import。Is it that， okay。

 that looks like that worked。Okay， and then I can try。This next La code here， which was。

List experiments。Oh， experiment。 La list。And so we see NBA salary here。So， I can just do。嗯。

We can just say。um。That would be number。What would that be， It would be number 1，2，3，4，5。6，7。Eat。😔。

So I could do that， I could say results。Is equal to。That。Result is it 7。 So theca it starts at 0。

 That looks good。 And so say。NBA here。And then， NBA。Dot。呃。Maybe it would be list。 anyway。

 you you could， you could basically start。You could。

 you could start programmatically I don't I don'd have to look at the API calls to exactly get it right。

 but basically you can take that same workspace and and hook hook the。



![](img/75a7bbef7b6a0048047f4df76241a480_16.png)

The inputs into it， and start doing other。APpiI call so like you have those same variables and throw it in there and start building out your own machine learning prediction。

 So I think this is also a very interesting process because you can see here you can easily build your own experiments。

 In fact we could try one more experiment real quick a little bit of time is。Let's try one more。

 so if I take the same data。And I go to Autom， I could say new automated run。

Grab the same thing that I did earlier， which is this MB data。And go next。呃。Create a new experiment。

 and we'll call this predict。Page views or something like that。

And so we can we predict who has the most page views， so like who's the most popular？

And so I would say we want to pick the page views right here。

 so we want to target this and we can look at this note here that says this is what the model will be trained to predict。

 Sam thing。 Pick this cluster。Go next and this would be， again， a regression。

So we could do a bunch of different experiments here got。The page views one。

 let's do another one as well。 So I'm going。I'm going to do one more here。

 I'm going to go to new run， go to the MB data again。 and let's do categorical， So if I look at the。

 in fact， let's go look at this data set real quick。

 let's see other categorical variables I can predict let's see maybe position。 Yeah。

 that would be kind of cool is let's see if we could pick the kind of the position based on this would be actually very interesting So we'll say a new experiment and we say position。

PPos prediction or something like that。Like that go through here and go to position。And then as well。

 go to this demo cluster， go next this time we'll do actually classification and we could if you wanted to do deep learning。

 but I think that this is better for text data， so we don't need to do it in this particular one。

And I'll say finish and so we'll see here we have a couple different email models so for me as someone who I can do this myself from scratch。

In Python， But why， why would I do this if I can just build all this myself？

 And so let's see this one's preparing。 this one's running。 So this will be interesting。

 Let's see how long this one takes to see if this one。We'll be pretty quick。

 so I think I can just click on this。And again， what it will do is it will tell it a bunch of difference。

嗯。Predictions here。And give us what it thinks are the best models for predicting page views based on this data。



![](img/75a7bbef7b6a0048047f4df76241a480_18.png)

![](img/75a7bbef7b6a0048047f4df76241a480_19.png)
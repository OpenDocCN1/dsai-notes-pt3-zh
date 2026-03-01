# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p105 21_02_06_无代码低代码自动机器学习第2部分.zh_en -BV1tz421i7Ev_p105-

![](img/f5a7ec3f246dda65553ab8ddf89c7356_0.png)

And now let's go to the next section here。 So let's go to what's next on our list。 So we did Apple。

 GCP， AWS。 Oh， yeah， Azure。 So let's go to Azure next。What do they have that we can use？ Well。

 if we go to Azure。

![](img/f5a7ec3f246dda65553ab8ddf89c7356_2.png)

嗯。There are some interesting tools in Azure also that are fairly low code， no code。

 and in particular。One of the tools that they have。That's fairly powerful is off the shelf OttawoM。

And they also have off the shelf computer vision， but let's look at this machine learning system they have。

 So if I go to this ML platform。We can see this is Azure Ma Learn Studio。

 this is an immersive experience for managing end to end。Products， and if I click on this。

I get this dashboard that allows me to do a lot of things and this here is one of the ones that I would maybe want to look at as automated machine learning and if I wanted to say。

 okay I want to do a new automated machine learning run。

 how would I do this I can say create data and I could again either grab it locally or get it from a data store that I could onto Azure grab it from web files or from open datas。

 let's first start with this from local files and I'll just go through here and say this is feature importance。

Eportance。Go through here。And then we'll just call this features or something like that。

That looks good， go to next。And then either I can use this existing。

Data store that I've got set up here， grab this data。



![](img/f5a7ec3f246dda65553ab8ddf89c7356_4.png)

Which is pretty simple data。

![](img/f5a7ec3f246dda65553ab8ddf89c7356_6.png)

And I can say go to next， it will validate the data。

Which hopefully is very quick because it's a small amount of data。

And it will show me what's inside and I'll say， yeah， I do have the headers。Here。

And it will adjust the data for me。There we go column name feature importance， I can go to next。

And it will also。Infer the schema as well。So again， I'm not writing any code here。

We've got all this information， and I even can profile this and I can select some kind of a compute cluster to profile that for me。

And I go through here and I now have ingested a new data set。And if I click on this。Here。

 now I put that data in。I can。Say， I want to do。An experiment。And I can say， create a new experiment。

 and we'll say。Features。Experiment。And then what is it I want to predict？

Feature performance importance。It's kind of a silly example， right， because I don't have anything。

It's not really a data set that I can predict something on。

 but I can go through your next and I can even enable deep learning or not。

 but then all I have to do is say what is it I'm trying to do classification。

Regression predict continuous numerical values。So let's select regression。

And it'll go through and it'll create a new automated ML run。 So in this case it says oh oh。

 the data should have at least 50 rows for a valid regression or classification task。

 so this is good。 It tells us exactly that we don't have enough data。

 So what I could do is find some other data set in fact。I have one。 I can go to another project。

I think I have it with。Social power and B， A。So I have some really good data。That I could go to here。

And。If I say， let's see NBA's players salaryri。Let's look at this。 looks pretty good。

 a lot of good information。Here， we have。The different players in the NBA。And we can have。

 what else do we have in here， We have。Mibi。😔，We can try to predict。The amount of money they make。

 There we go。 This is a good one。 so I'll just download this file。And I think I can just。Go to raw。

And say， save as。And just put this on my desktop。 Now， let's do the same thing。

 We'll go back to Microsoft。Azure， which， where is Azure。Here， so I'll close this。 So。

 so good Azure and say finish。 Okay， great。Did't it didn't like that one let's go back and do AutoML run again。

 so we'll say a new create a new data set from local file， we'll call this NBAA data。Tabular。

This is salary。Data from the NBA。Go next year。Use this data store。嗯。Upload。



![](img/f5a7ec3f246dda65553ab8ddf89c7356_8.png)

AThe data set that I just put in here。

![](img/f5a7ec3f246dda65553ab8ddf89c7356_10.png)

It will then go as well and inspect the schema。We can see that it's comm delimited。

It does have headers， so we can say use headers from the first file。And from here。

 we see the different columns。 we have the player name， the position， the age。The minutes。

 field goals， all kinds of great values to look at and probably yeah let's see if we can predict how much money they make。

So we go through here。We have all these different values， these look good。We go to next。

And then we can say profile the data as well。Click on C。We're going to now select this NBAA data。

Create a new experiment。Well call this NBA salaryri。And okay， now。

 now we can get to the point where it says， okay， well， what do you， what do you want to predict？

 Well， I want to predict。The money they make。 I want to see how rich they they are。 Here we goes。

 salary。Millions， so can we create a model that will show me。

When an NBA player will get paid and then it'll ask me to select a compute cluster。

I'll go through here and then I have to tell it what what is this， this is a regression， right。

 so I know it's going to predict continuous numerical values。

 a salary is a continuous numerical value。We'll go through here， and we'll say finish。And。

Now we're going to go through and we're we're going to。

 it's going to automatically go through and do a bunch of work for me and figure out。

A way of predicting based on those all of those columns that it that it was given like social media。

 the rebounds， the points they scored， what team they were on。

 all the stuff it's going to just crunch on that for a while and it will come back and it will give me this report。

 So this will take a while longer probably than we have。

 I think So what I'm going to do is I'm going to go to。

A previous experiment that I ran on a different project， and I will look at。A run。

 And we can see the kind of things that it can do。 So if I go to this one here。

Here's an example of actually the same banking data。From before that I was using from。EWS。

And notice what it shows here is if I go to models that。With Ottawa Mill。

It will actually go through and run a lot of different models， so it will go through and。

Bun voting ensemble， Max 80 Scalar， Sprse normalizer。 By the way， this is a different problem。

 It's a classifier。 so it's it's a different。Machine learning algorithms。

 we go through here and it just again with no code， I click a button， it runs， runs， runs。

 runs when it's done of one of the runs it said， oh look this is this one took about a minute。

And this has the best accuracy。And I can even look at the explanation。And I go through here。

And I see the explanation。And。I can see that there's top K features right here， and I can see that。

 oh， look， this is the most important feature。For my autotel。 And it turns out that how long。

The customer。Is is with the bank is the most important feature by double， right。

 The next important feature would be that whether they're employed， which is intuitive。

 right if they don't， if you're not employed， you're not going to be putting money into the bank。

 You don don't have any money。 And so this is super helpful。 And I even can see a different view。

 which is the absolute value view and this absolute value view shows me both the positive and negative relationship of that feature to the model。

 So we see that in the cases where they do deposits the absolute value。

 the positive part is actually the most extreme。 but but these other features。If you're not employed。

 it has a negative， more it's more heavily weighted。Towards saying I won't deposit。

 then if you're employed it has some impact right， positive to the model。

 but the most positive predictor of whether they would deposit or not。

Would be the duration of employment right so again what's great about these kind of tools is that I don't have to write any code at all。

 I just click a button run it， I look at the results and then if I wanted to as well。

 I could I don't know， take this as well and put this into my explanation and I could do high level machine learning。

 computer vision， deep learning。And I didn't write any code right。

 so we could put this in our modeling section so I could go here and I say， okay。

 I created a model that predicts who is a customer。



![](img/f5a7ec3f246dda65553ab8ddf89c7356_12.png)

![](img/f5a7ec3f246dda65553ab8ddf89c7356_13.png)

啊。Of our bank。And I'm going to put this into the model。 And so later when I。

 when I come up with my report， I can link to this， and I can， I can explain。 So。

 so even this might be a little too much for。A CEO。

 especially if they're the the kind of CEO that we have in America where they don't read books。

 I mean， there's a lot of CEOs that do。 But the one that's running in America that you have to simplify even more kind of make it。

 make it more straightforward。 And so。The key thing that I would probably put in this report。

If we were going to do a report on this would be some findings would be that R。Email models。

Show that。And then you put the two things inside that length。Of time。As customer。

Is a critical feature？In deposits right， so so then maybe even I grab this data。And I am I。

Save it again to GiHub。🤧。And I go to。

![](img/f5a7ec3f246dda65553ab8ddf89c7356_15.png)

Business report here。

![](img/f5a7ec3f246dda65553ab8ddf89c7356_17.png)

And。What I do is I put in this conclusion。And I say that my recommendation here would be that。

Our bank， I'll just say example。I say like， so I want to do a very firm conclusion for the CEO and say。

 you know， just as example to the CEO。Example， conclusion。Is our bank。Needs more revenue。

Everybody wants more revenue。To increase revenue。We need to create a special。Marketing campaign。

That sends emails to customers。That。Have been with the bank。4，5。Or more years。And offer them。Ai。$50。

Gift card。If they deposit。$5000。Into。A Cd。Right， there we go。

 So we've got actually a very a very firm conclusion。's this is not ambiguous， right。

 This is that a executive。Can look at this。And。And then they say， oh， okay， well well that's great。

 I I'll have my team look at your report。But you didn't waste their time。

By going into the meeting with the CEO and starting with， okay， so look。

 our absolute value is negative two with duration medium with duration mean。Impututer。

 someone that's a CEO would just say get out。 I don't want。 I don't want to hear about it anymore。

 Unfortunately， they don't want to know anything about this。 They don't want to hear about the data。

 They don't want to hear about any of this stuff。Now， somebody else on their team may look into this。

 So you do have to have good， good results here， but。When you're doing a business presentation。

 you have to focus and make it very compelling in your final conclusion， as a say。

 our bank needs more revenue to increased revenue， we need to create a special marketing campaign that sends emails to customers that have been with the bank for five years or more and offer them a $50 gift card if they deposit $50 into a C or $5000 into C。

 That's it。 there's nothing unclear about this and only took two or three sentences。

 right So that's really my recommendation as you're thinking about building these reports。

 not just in these projects， but but in general， is to have this kind of a structure。 And again。

 as I showed here。You don't need any code at all。 you can write no code and you can do advanced machine learning。

 advanced neural networks， business analytics， and the most important thing， though。

Is this conclusion so that there's a call to action for the people that you're working with and that if you do this approach。

You'll be the person that the executives will bring into their office because I've been the person。

 I've been the person in charge of a company and and I know the details， and I can do this myself。

 But if somebody starts coming in and they start showing me all this technical stuff。 It's like。

 look， get out， I don't have time for it， I'm busy why are you telling me all this stuff。

 what do I need to do， you need to give them a call to action， this is more likely going to be。

 now you can't make it up。You can't make up the data right that's going to be a problem so you better have your facts together in your report。

 but if you're the kind of person that comes in and gives people very concise information。

With a call to action， you'll probably be one of the most popular people in your company because you're always going right to the point。

 giving someone what they need and you're a very helpful resource for your organization。



![](img/f5a7ec3f246dda65553ab8ddf89c7356_19.png)

![](img/f5a7ec3f246dda65553ab8ddf89c7356_20.png)
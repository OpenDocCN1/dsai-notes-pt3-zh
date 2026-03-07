# 2025 Pytorch大会 ｜ Pytorch Conference 2025 p39 P39_“多模型”时间序列预测——在数千个...上扩展PyTorch训练-_V._Sridhar__S._Chen -BV1b8kRB6EJG_p39-

Hello， everyone。 Good morning。 Thanks for being here。

 My name is Vina I'm a product manager at Snowflake。 I'm John on stage with Shuulin。

 who's on the engineering team。 give you a chance to also talk more about your role as you get to your session。

 everyone。 My name is Sulin。 I'm an engineer。 And today。

 I'll be presenting the demo on many models training in just a bit。😊。



![](img/effd9e321411776e6560e60ba0844871_1.png)

Cool so our talk is focused on this framework called many model framework and we'll talk a little bit about the use case。

 we'll apply this to complex time series forecasting and we'll show you how these are actually very。

 very pertinent problems as we're seeing across the market。😊，And we have a cool demo for you。

 would love to also， of course， spend more time taking your questions。

So me to talk with this safe harbor slide in case there are some things we say。

That is future looking， please don't hold us to that commitment。

So I want to start with just setting the context for forecasting problems in general。😊，We。

 as part of Snowflake， deal with many， many different customers，terabytes。

terabytes of data on our platform。And a common pattern we're seeing is how forecasting has become so much more complex today。

 It's no longer what we saw simple regression earlier。

 So take a case of a retailer you want to forecast product sales。

 you want to make sure that your inventory systems are in the right place you want to make sure the supply chain is sufficiently optimized to deal with these type of weighing demands and all of this means you have to take in signals from everywhere to make sure you get to this accurate forecasting So when you're doing things like product level forecasting。

 you want to make sure you're taking in customer feedback reviews， sentiments。

 a lot of multimodal signals， people are uploading videos and images and everything contributes to。

The ability to， to forecast on the success of a product line。

Now put that into how this plays out across a time series sequence， you got nonlinearar time series。

 you've gotities you've got seasonalityities within seasonalityities。

 you've got a fall window with long weekends and Halloween weekends and all of this means there is a very complicated series of windows that you need to make sure that you're capturing in your feature set that reflects the ability to forecast how your sales are going to be。

And then think of all the external factors that are contributing to this process。

 You've got market signals。 You've got competitor announcements。 you've got。Geopolitical situations。

 everything that contributes to your need to make sure that you are forecasting things the right way。

 Now， this can easily be translated to other scenarios。

 We've got financial services companies who are doing this on equity forecasting。

 You want to make sure you're predicting stock forecasts。 It's a really。

 really complex and consuming process and。I would say almost a large majority of these use cases are now doing somewhere between an LSTM and a transformer and the transformers are becoming a lot more common in these types of forecasting。

Okay， so that is not that new a problem we've seen this is this becoming a lot more common these days。

 but what is actually becoming a real challenge is trying to do this at these micro segmented levels like imagine you have a retailer who's got。

😊，100 product lines。500 stores， four， five different geographical locations。

 and you want to make sure that every one of these micro segmentss has this type of detailed forecasting。

You as an implementer， as a technologist， now needs to figure out， okay。

 I have these complex models I'm training on。Probably percu， per Q times store ID times geography。

 whatever that key is。That has to then train frequently。 I can't just do this once a month。

 right you want to make sure your forecast is up to date and it reflects the latest patterns and indicators。

 you have to train this weekly， biweekly， possibly even daily， and you're trying thousands。

 tens of thousands， hundreds of thousands of these complex models every single time。😊。

This means your infrastructure needs to be scaled up sufficiently。

 your training needs to be robust and reliant， you need to make sure checkpointing is in the right place。

 you need to make sure observability is in a good shape。

 you need to make sure all of this can be automated and deployed in a nice operational manner。

This becomes an enormous scaling challenge。Which is where we in Snowflake have leaned in heavily to make sure that this is really simple for people trying to implement this type of pattern。

So what weve introduced and we'll show you a demo for really in a short bit is how we have defined this thing called a many model framework where effectively what we're saying is you as a user make sure your data set is partition you give us a partitioning key yourition partitioning key could be a combination of your store ID product ID and SkuU or whatever that is right all you need to do is give us a partitioning key。

Point us to the set of table set of data wherever they are and write your training function。

 write your Pyth definitions， write your optimizers， layers。

 whatever that may be which you're going to do anyway for a single queue。Give us these three things。

 we will do the rest。 We will make sure that infrastructure is abstracted away。

 the orchestration is abstract abstracted away。 Everything is robust and you end of the day get an end to end working pipeline。

 not just that well train these tens of thousands of models concurrently。

 we will also make sure there。Logged to a registry where you can infer on these log models with the same partitioning sequence。

So I'm sure you can see a lot more in the demo and w to quickly touch on what the simple layering diagram just to sort of put into place what we're using a lot of the orchestration and the scheduling is happening through Ray and we all know ray' is phenomenal at doing a great job at hetero is compute and making sure that the data is pipeline sufficiently for the best utilization of resources we've seen great GPU saturation coming out of using ray so we're happy to talk about how much we've invested in making sure Pytarch on ray runs really well at the same time it's snowflake data so you've got large amounts of data that needs to make sure it's streamlined its pipeline into these ray actors and that's where a lot of the engineering work is gone in。

Want to touch on a few quick things here so in addition to what we're calling the many model training or the partition training which is the third box you see there。

 there's other distributed frameworks that we've built to make life easier for customers over Ray so we've got a distributed data connector which means wherever your data is your data and S3 your data and tables。

 we will bring it in using Ray into memory of your notebook or wherever you're running your workloads in a very very scalable and efficient way we've got all of the distributed ML training hyperparameter tuning API is also built on Ray and of course what we're going to be talking to you about today。

CoolSo I'll give you a quick intro into this framework and then I hand it right over to Susan So what is happening under the hood is we have a snowflake table where you define part again snowflake table could be any table This is just a simple database construct。

 You have a table you have a partitioning key What we will do is we will automatically run a query to extract every single partition in this case you have thousands of these partitions into its own data frame those data frames are then converted into a ray data set and that's where the magic of ray happens like each ray data set is mapped to a ray aor and that ray aor is then fed that data set along with the training sequence we set up in the initial definition and then all of these are kicked off in parallel we assign compute clusters as in when they come up so each time a reactor is alive we connect a node to it and that way you're given the gradual scaling up and gradual scaling down so that's also part of the optimization that。

😊，Don and of course you can use GP clusters， CPU clusters。

 combinations of these multi GPU nodes where you want to train a single Pytorarch model on multiple GPUs or multiple nodes。

 all of these combinations are possible through this framework。Great。

 so this can be super complicated。 We want to keep it really simple。

 just show you what it looks like in the notebook。 and you know the goal of this demo is the simplicity of the interface and the power beneath it。

 So I'll hand it over to Suln to do a quick demo thanks Mindy。😊，嗯。Okay。

Let's get it running all right thanks everyone to joining today now that we have seen the overall many model training framework architecture let's dive in and see how it actually works in code in this demo we're going to work through a simple synthetic synthetic retail dataset sets we'll chain a pilot model for each store in parallel to predict the daily sales based on historic data we'll then scale out the cluster to speed up the training process and finally we're going to deploy all the chain models into the model registry and for inference later on so just to mention we're now focusing on the modeling part in this demo specifically it's just going to be basic synthetic data and small modeling the main real story we're trying to convert here is to showcase the many model training framework that to easily chain manage and scale out many of the models that you have in very efficient way。

😊，So as you can see this entire everything you see here is running inside a container runtime environment in this case is running in a CPU cluster that consists of a x64 medium instance that has six CPUUs on it。

 but we're going to scale this scale this out later on as part of the training process as you can see so before that let's do some basic setup。

 first we'll create a snowflake session object， this is what allows us to connect to the snowflake data the row data that we try to chain with our model zone。

 then we're going to set up a snowflake stage which is used as a persistent storage for saving any many model training associated artifacts。

That's all the setup we need before we jump into the data parts right so the data。

 the synthetic data basically as you can see it has a multiple of rows each row represents a product daily sales along with features such as price promotion and competition pricing this data set as relatively small it covers 150。

000 total records spans through 10 stores and each stores having 500 unique products in each store and it so prepare to prepare this raw data for our model consumption。

 we need a little bit of feature engineering work so here we are simplifying to using creating a sliding 14 day sequence of features and pair pairs each sequence with a next day's sales value so effectively the model itself learns to focus the next day sales best。

On the previous two weeks of activity so the resulting training tensor is the number of samples you have and it's gonna be 14 by3 14 as the number of past 14 days and three in this case is the three features that it's going to fit into the model now for the fun part thats dive into the actual how do you invoke in many model training so there are a couple of parts related to it so the first is that we need to define a training function and the next we need to scale out our cluster accordingly and the last is that we're going to invoke API to run that training function across all our training workers and we're gonna monitor the process as it's running so the first step is we basically define this training function the LTM model very simple and then we have a user training function this basically takes in two things。

So take in the data connector， which will connect basically。

The MMT framework under could petition the data and pass each store petitionition into this training function。

 so each of these training function will only receive the corresponding store ID petitionition data the second argument here is a context object。

 this context object provides information such as which part ID is is associated with this data that is passing into this training function。

 So here I purposely throw an error when this training function is processing partition5 and we'll see in a bit how this error is actually surfaced up later on moving on we connect the data to pandas and we prepare the data into the sliding 14 day windows before we fitting into the model then we connect we basically convert that data into a torch data and fit it into the data loader and the rest is just very straightforward torch chain chain it for a few apos。

And we record the logs along the way and for now we basically just print it out and I'll show you in a bit how those information is actually being captured so once this is done before you actually invoke it we can choose to with simple one command we can basically scale out our cluster to have more notess so one cool thing about this is the scaling is actually can be done in asynchronous way so we don't have to imagine if you have many nodes that you want to spin up。

 you don't have to wait for all the node to be up before you can start running many model chain so while the nodes are starting to come up。

 the many model training can start running and as more nodes come up they could join the work poolol to take up more training work along the way so let's see in this many model chain API we take in the user function that we define in the earliest step we take in a stage name that we create it at the first step to persist the artifacts。

We also pass in the run ID here before into the run function。 let's hit a run。 let's give it a run。

 just want to point out the run I is useful for if your notebooks for some reason disconnects you can use the run I to cover back the previous result so you can see there is a extremely we're just showing you the realtime progress we separate out the data ingestion and chain as what we mentioned earlier so as soon as one data instion is ready to be trained。

 we will have a worker to pick that up and running it directly and also we are showing because we're running in a two node setting as we just scale out just now you'll see that there are two nodes the CPU utilization and memory in the real time but for some more textavvy users who really like to see underlying like what is the rate operation you're doing under the code we also provide user the direct link to the red dashboard and their user can actually have the default native red dashboard。

To investigate any like under the button like the red task or actor resource usage， logs， cluster。

 etctera， auto box so all of these are very negative in as what rate provides so once this chain finish here it shows fail and this is intentional because remember we previously in our chain function we throw an expected failure for a specific part so imagine now for a real user。

If they run get progress with this specific run that we define in the previous step。

 thats it's going to show that theres nine out of 10 petitions。

 there are nine petitions that succeeded， but there's one fail one take a look at like say the first succeeding petition and the corresponding logs associated with that you will see that it prints out the the correct training loss as what we define in the previous step training function。

 and we can also easily get the model weight out from date chain model in that petition through the get model call。

 So this is all the tens weights as you can see， but what's even more interesting is actually debugging what is actually failing。

 So theres one failure and we can easily get that and print out the logs Now that we retry it for three times and eventually fail。

 So this is the runtime error that that we threw in the earlier step。

 So in the real worldor scenario。😊，AArras does happen and what we have seen happen a lot is auto memorymory error so sometimes each petition could have different skills so when petition becomes too large or the model complexity becomes too complicated there's a chance to womb and what we have done here is we have built in a womb detection system they basically we kill the job right before it's about the womb and we handle it nicely and surface that error to the user and as you can see even if a couple of petition fail is not going to fail the entire many model training job and the benefit of this is if a user is running a very large scale many model training worknot they can say for days or hours。

 they can literally take a look on the resulting fail petition diagnose what's going on and then only rerun the pipeline on those fail petitions instead of the entire petition to save time and cost。

So moving on so after we have chain the1 models based on each store and product。

 we're going to log these models to the model registry for inference so log into the registry is really straightforward here we basically define a petitionition model this petitionition model is basically a model that encapsulate all the chain models sub models that we have changed in the previous step and we get all those sub models in the step through the many model chain framework get model code and we pass it down to this model context object and to construct this petitionition model and after that we're going to log into the model registry and for the timest I already did this step earlier so here we will log a model called petitionition model and to the registry once log model finished you'll see in a snowflake snowside UI that there is a model being called petitionition model with a version name called Sc2。

So you can see the input and output of that model a typical of what this model expects and what's more is you can click into the artifact just to see because in this case we have1me store ID so for each store ID we change a specific model for it and you can see the to model and then you can download it to player with it to debug anything and a very position level if you need it and we also come with a bunch of other metadata files for users convenience so after the model is logged let's go back to see how we actually run inferenceprint on the log model so in this case we are preparing our test data into a past 14 days of features and what this is going to be do is that once we pass this data to our model and code model that run on it it's going to take in the past 14 days which consists of many different stores。

And our model our framework is going to be able to route each record to the right set model that corresponding to that store and run inference on it。

 So this run will basically take run all of these records。

 and then this is a simple prediction how operation result actually looks like what this means is basically for store ID9 and product ID0 based on the past 14 days of the features that we're passing we predict the next day sales is going be 30 in this case and that pretty much sums up the demo portion that switch back to the slide。

 So。Just a quick notes on the performance。 so we have done benchmarking comparing this。

 even running the menu model training on a single node and when you compare it to with a serial manner of running models。

 we're still showing like as the petition size increases。

 the MMT started to outperform serial training by a lot and then what's more if you scale out your cluster from one node to multiple nodes。

 we see there is a linear correlation between the number of total run time associated with the number of nodes that you scale up and this shows that the entire menu model training framework is highly scalable across multiple nodes and we have tolerance built into each of our petitionition training section。

 So each of the user training function that we saw earlier。

 we automatically retry we handle the room error out of box and we provide a nice interface for user to debug if anything goes wrong and then only retry the fail options。

Petitions if needed and with that that should sum up the entire presentation thanks to everyone for following along and now I think we can open up for some questions。

😊，Like all the demos， you we can learn best week。To run visa， Ju burn no whos ourselves shelves。your。

三び拜。So。The first two are actually generic distributed Pytch tutorials that you can run on snowflake。

 it's trial account compatible so you can log into snowflake。

 datas are already there the first two ones actually point you to general distributed Pytarch。

We will publish documentation for this particular framework that we spoke about。

 It's just getting out of preview as we speak。 So the the demo that Shu just showed you that is not yet on our websites。

 but you can see something similar in the first two links。So on your left here。

The failure and restart detection work that you had there was very cool。

 thanks for showing that I'm curious how that works in a multinode scenario where you might be failing in a collective where the other node is know waiting on the node that actually failed。

 do you kill the whole job and restart it or what do you do in those scenarios？

Are you talking about a scenario where each training function is running across multiple nodes or the single node setting yeah so a good question I think the question is about like in a many model training framework if you run each of your training function across multiple nodes and if one of the node fail will it affect other worknots right so in this case I think we do technically we have actually we enforce some sort of resource boundary each node is only allowed to use up to certain amount of resource once it gets across to that level we kill that job automatically so we will kill that specific petition job and it will mark that job as failing and then we'll throw an error in that log saying that this job fail because it ws out after it surpass this extra memory space and it's up for the user to actually retry with a larger node or basically scale to nodes basically I think another way of answering that is auto scaling。

Not yet in place。 So that's something that we want to overcome。

A question I had was like sometimes om happens because my CPU and GP like if my data processing is happening on some CPU kind of thing and then I'm loading the model training on GP。

 is there a way to apply a little bit of back pressure or is it like you have to materialize the data frame in memory and then train on that So it's kind of separate This joint Yeah this' is a very good question So I think in the in existing pipeline we already we doing the pipeline between the loading data from snowflake but and then loading data from that into GP from CPU to GPU also incur additional。

Time right now， we haven't done specific optimization on that yet。

 but it definitely something on our road。 This is will be more related to how user actually define their chain function。

 And if there is any optimization they can do it。 But we're also thinking about from a framework perspective。

 what we can do about it as well。 Yeah， but that's a good question。😊。



![](img/effd9e321411776e6560e60ba0844871_3.png)
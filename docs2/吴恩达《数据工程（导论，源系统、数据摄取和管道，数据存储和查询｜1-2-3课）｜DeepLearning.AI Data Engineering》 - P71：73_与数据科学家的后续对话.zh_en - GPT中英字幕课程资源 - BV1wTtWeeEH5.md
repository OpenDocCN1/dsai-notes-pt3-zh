# 吴恩达《数据工程（导论，源系统、数据摄取和管道，数据存储和查询｜1-2-3课）｜DeepLearning.AI Data Engineering》 - P71：73_与数据科学家的后续对话.zh_en - GPT中英字幕课程资源 - BV1wTtWeeEH5

![](img/ced6663866c169d5e72b9af706fd0e66_0.png)

It's good to see you again， Colleen。You kind of look like the software engineer I just talked to a bit ago。

 but without the glasses but anyway， yeah we get that a lot。 that a lot。

 Well the last time we spoke we talked about two projects you're working on for the marketing team an analyticsboard and a recommender system Since then I actually got a chance to talk to the product marketing manager to have learned more about their needs for each of these systems than I met with one of these software engineers platform team to learn more about how we can best access the data they're generating on the sales platform。

 What I'd like to do now is learn more from you about how you're imagining the recommender system will work so we can start a prototype of data pipeline to serve the system。

 Can you tell me a bit more about your work so far on this project。 Sure thing。

 So I've been experimenting over the last month or so with some models and ideas for the recommender system。

 And for now I've decided to implement a contentbased recommender system。

The way that works is that I take a set of features containing information about each product and then also a set of features containing information about each user I then compute a vector embedding for each user and each product and look for similarities between these embeddings in order to make product recommendations to users so the model takes user and product features as inputs and generates a list of product IDs as output Oh awesome so you've already got something up and running。

Well， sort of I've been experimenting with some models on my local machine。

 I've trained a contentbased recommender with some of the user and product data that I had initially downloaded from the dashboards。

 The model seems to be working Okay， and what I'd like to try next。

 is retraining model based on a fresh batch of data to see how stable it is and try to get a sense of how often we might want to retrain and update the model in deployment。

 Okay， great。 Well， if you can tell me bit more about the format and structure need for the training data。

 I could start working on a plan for a data pipeline to deliver that data and batches to you。 Yeah。

 that would be awesome。 So the training data I'm using is in a tabular format。

 Each row contains data for a single product purchase where the columns include a collection of user features。

 which are customer number， credit limit， city， postal code and country。

 And then there's also a set of product features， including product code， quantity in stock by。😊。

MSRP product line and product scale in addition to these user and product features。

 there is a rating value from one to5 that represents the user's rating of that product got it now if you had to guess how frequently do you think you might want to retrain and update the deployed model Well。

 the short answer is I'm not sure yet I will plan to monitor the model' output。 In fact。

 it would be great if in addition to surveying recommendations on the platform all the model output could be automatically saved for later analysis and then I would plan to retrain the model if I notice any drift and performance or change in the input data。

 So I guess I might want to retrain the model as frequently as once a week but might be less than that like monthly or quarterly So it would be great if it doesn't require too much operational overhead for you to deliver a new batch of training data and possibly in a modified format if we have a new product or user features want to。

Great okay， that all makes sense now can you tell me a bit more about how you're expecting the recommender model user production Yes。

 so what I was thinking is that I would like to make recommendations based on both the user information as well as any information about products they have been browsing or they have in their shopping cart The way I imagine this could work is that the model will set up to take user information as well as information about any number of products that they have been looking at as the input I can then find a set of products to recommend based on the user information and additional products to recommend based on the products they have been browsing or have in their cart So how fast will the system need to generate recommendations。

Sure， so we would like to be able to present recommended products to the user more or less instantaneously as they are  browsing through different products or during the check out process。

 it usually takes a new page a second or two to render。 So if the recommender could work that fast。

 it would be。Okay how long does it take to actually run the model and generate recommendations Oh so the model is really fast my local machine only takes a few milliseconds to generate recommendations given a set of input features。

 the way I have it set up is that I already have all the vector embeddings for the products in the catalog stored such that when I run the model I can quickly run the similarity calculation as I understand that the platform records data from users currently online in an event log so it should be possible to just stream events from that blog with very low latency So assuming that the sales platform is able to provide user and product data and then receive and render product recommendations with subsecond latency I should have maybe one second or so to complete the roundtri with the data enabling ingest transform and serve user and product features to the model and then return the recommended product like these back to the platform What about scalability。

A sense of how many concurrent users you would expect to be serving product recommendations to Well。

 the company currently has around 100000 customers in the database。

 meaning that many individual customers have bought at least one item and many of them are repeat customers。

 We're expecting that number to grow as the company expands to new regions and product lines So right now it varies a lot。

 sometimes there are only a few people shopping on the platform。

 but we can see activity spikes of up to 10000 users on the platform at the same time。

 and we could see more in the future。 All right so it sounds like there could be a wide range in terms of concurrent users。

 right well I think I've got everything I need in terms of information at this point。

 So thank you very much Colleen Okay great let me know if any questions come up do Thank you。


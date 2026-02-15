# 吴恩达《构建多模态搜索和 RAG｜Building Multimodal Search and RAG》中英字幕【短课均可关英文字幕】 - P7：7.L6 Multimodal Recommender System.zh - GPT中英字幕课程资源 - BV1sx4y1W7uV

![](img/c6ad1ac84c9117fdb1467145b6182a48_0.png)

In this lesson， you build a recommendation engine。 you are going to use Vigate to build a multi vector recommender system that can recommend relevant items by searching over different mod driven representations of items。

 Allright， let's push the boundaries of innovation。



![](img/c6ad1ac84c9117fdb1467145b6182a48_2.png)

First， let's think about how searching is different from recommendation。 Search is objective。

 It doesn't depend on who is searching。 You don't need to worry about personalizing the results to the user as long as the results match the query semantically。

 the search can be considered successful。 So if a user searches for basketball jersey。

 returning any of the following jerseys would be correct。



![](img/c6ad1ac84c9117fdb1467145b6182a48_4.png)

![](img/c6ad1ac84c9117fdb1467145b6182a48_5.png)

Recommendation， on the other hand， is subjective。 It's very dependent on who is asking the question。

Let's say your store sells， basketball jerseys and a customer ask for a jersey。

 You need to know more about the customer to provide the right response。 So， for example。

 if this Lakers fan comes over to your shop， then the best jersey that you can recommend are these Lakers shirts。

 On the other hand， if you have a Boston Celtics fan coming over。

 then the best recommendations are the Celtic jerseys。😊。



![](img/c6ad1ac84c9117fdb1467145b6182a48_7.png)

Muldymod data offers a great solution to personalizing a recommendation system to a user by allowing you to capture their interest using all available modalities。

 So let's see an example。 So if I asked you for your perfect burger。

 you could write down a description for me in text or you could show me an image。

 or you could give me nutritional facts about your perfect burger。😊。

I could use all this information of your perfect burger to identify what you like and dislike。

 I could also use these separate modalities to personalize recommendations to do this。

 you could capture all this information to a vector or even multive representation where every vector comes from a specialized model and allows you to search over that modality。

 This is important， because some people might buy due to the way the product looks。

 other people might buy because of the detailed descriptions。

 while someone else might pick it based on the nutritional information。😊。



![](img/c6ad1ac84c9117fdb1467145b6182a48_9.png)

Alright， so let's now see all of this in practice In this lab。

 you load an embedded multimodal movie data with two separate MLl models。

 then run text and multimodal queries in different vector spaces。 Great， let's code。😊。

So like all the previous lessons you're going to start with ignoring all the unnecessary warnings and again we are going to load necessary API keys this time though we are going to use two different keys。

 one for the multimodal embeddings， which is the same model as we use before。

 but we are also going to use a text embedding from open AI here。

 and then we're going to load them just like this。And you are going to connect to the embedded instance of Wvi again。

 this time we're going to use the two different modules， one for textware for multimod。

 and we have to pass both of those API keys as part of the headers。



![](img/c6ad1ac84c9117fdb1467145b6182a48_11.png)

And by running this， you can connect to an embedded we variances。



![](img/c6ad1ac84c9117fdb1467145b6182a48_13.png)

And now that you're connected to Vivi8， you're going to create a new collection called Movie and then to help you you already have here predefined properties so we can expect title overview。

 vote， average release year， etc， etc， and then this is a really important one。

 the path where the images will go and that's one step。And because this is a multi vector collection。

 first， you need to configure a name vector for your text embeddings and you are going to call this vector space text vector and specifically for this name vector。

 you want to vectorize on title and overview and ignore all the other properties。

And for the second vector space， you're going to add a second name vector。

 and then this one will be the multimodal vector， and we want to run it on the image fields。

 which will be inside the poster field and together with the specific model that we need to run and all the additional information。

And just to clarify the name vector space will be called poster vector。



![](img/c6ad1ac84c9117fdb1467145b6182a48_15.png)

And with this， we can execute it and this will create a new collection for you。



![](img/c6ad1ac84c9117fdb1467145b6182a48_17.png)

In case you need to rerun and recreate this collection again， you can uncommon this line。

 which will delete the collection for you and then you can recreate it。

 just be careful with this because if you do run this。

 you also lose all the data that was in that collection at the time when you run this。

And now that you have a ready collection you can start looking into importing sub data。

 so inside this project there is a movies data adjacent file which lists 20 different movies together with posters for them。

 so let's have a look at what we can see in there and you can see that there is a link to the poster which is in here called the bugd path and in here if I scroll through the columns。

 you can see that you already have all the necessary data like the original title。

 the overview the popularity but and then really important one， the poster path etc， etc。Next。

 you need to load the helper function， which will take a file path and then convert it to basease 64 representation。

 which is something you've done already in previous lessons。

Now that you have all the building blocks it's time to import the data so one of the first things you need to do is grab the collection。

 the movies one， and then it's over here and then on that collection you want to create a batch object with the rate limit 20 which basically means that you want to only upload 20 images per minute which can help us with rate limits of the service and then using the data frame we can iterate through all the movies in the preloaded data set there are only 20 so that also matches the rate limit that we're after。

And then this statement here is quite helpful because using the Gen view ID which is imported at the top。

 we can provide a movie ID and if that a movie ID already existed in our data set。

 then we can skip it so even if you rerun this cell。

 you're not going to import the same movie twice which is super helpful and we're good to go。Next。

 as you iterate through all the objects in the data frame。

 you want to parse the path to the poster file， which is inside the post folder。

 and then go one by one， convert that into a base 64 representation。

Then using this information into construct a movie object which will contain the title， overview。

 vote average， ID poster path and poster B64。And the final thing you need to do now is just call batch at object。

 so passing the movie object as the properties and then generate a UI from the movie ID which is then used in the earlier stage to verify that we're not ever importing the same thing and with this we can run it and import all our images。



![](img/c6ad1ac84c9117fdb1467145b6182a48_19.png)

So what's happening right now， all these 20 movies have been sent to two different vectorizers。

 so in here we are sending the posters into the multimod model which will vectorize all of them。

 but also the title and description has been sent to the text model from Open AI to vectorize the title in the description。

 and this should take about a minute。And that after that。

 you should be good to start querying this dataset and as the final step。

 you need to check if the import went well So the way you can do it you can go into the movies batch object and look for failed objects if there any failed objects at all because this is a list you can print it or maybe print the first one and if theres no errors we should get a happy import complete with no errors message。

 which is great。 And now it's time for you to get to the fun part where you can run some queries on the data and so let's set for some movies about lovable cute paths and this query is very similar to what you've run before however。

 because we are using a multi vector space or collection has configuration for two different vectors you need to specify which of the vector space you want to search through so in this case for this query you want to set across the text vector space and when that executes。



![](img/c6ad1ac84c9117fdb1467145b6182a48_21.png)

You want to print the results so it's good to print the title。

 the overview and also display the poster from the object that we got back that matched to the query that we searched through please note that this specific query would only try to match it based on what's in a title and overview because that's what the text vector was constructed on alright let's run this。



![](img/c6ad1ac84c9117fdb1467145b6182a48_23.png)

![](img/c6ad1ac84c9117fdb1467145b6182a48_24.png)

And you can see the first result for me is the 101 animations together with the description and the poster from the movie。

 I also got the poster from Stetuart Little together with the title and its description and the third response was aB's life together with the description for it again and a poster from that movie。



![](img/c6ad1ac84c9117fdb1467145b6182a48_26.png)

![](img/c6ad1ac84c9117fdb1467145b6182a48_27.png)

![](img/c6ad1ac84c9117fdb1467145b6182a48_28.png)

And now let's try another query on the same vector space。

 but this time let's look for epic superheroes。

![](img/c6ad1ac84c9117fdb1467145b6182a48_30.png)

And you can see。

![](img/c6ad1ac84c9117fdb1467145b6182a48_32.png)

We got an Ironman。Incredible too。很是的。And one thing that you probably are thinking right now is like。

 okay， this query is based on the text vector embeddings， but we still get in here posters。

 The thing is that， yes， that is true。 The query is still only running on the title and overview。

 However， the objects that we're getting back contain the information about the poster。

 So that's how we were able to display them。 but the posters weren't used for the query just yet。

 This is coming in the next step。😊。

![](img/c6ad1ac84c9117fdb1467145b6182a48_34.png)

So to actually search across the posters， what you need to do is run similar query。

 but on the poster vector vector space by running this and then what well be trying to match is movies about lovable cute pets where the posters reflect this query。

 So let's run this and see what we get。

![](img/c6ad1ac84c9117fdb1467145b6182a48_36.png)

And you can see here that the results are very similar， but they are not exactly the same， however。

 they do match the original query really well， so the lovable cute pads are visible across all three posters that we got back here。



![](img/c6ad1ac84c9117fdb1467145b6182a48_38.png)

![](img/c6ad1ac84c9117fdb1467145b6182a48_39.png)

![](img/c6ad1ac84c9117fdb1467145b6182a48_40.png)

So let's try another query here to again search to the poster vector space。

 but this time you want to look for epic superheroes so that you can compare like and like the results to what you got back when you search through the text vector space。



![](img/c6ad1ac84c9117fdb1467145b6182a48_42.png)

![](img/c6ad1ac84c9117fdb1467145b6182a48_43.png)

And again， the results are very similar， but they're not exactly again the same because the information that we got in the posters are slightly different to what we have in the title and description of the movie。

 and youd probably get even more differences between what you get from one and the other。

 but in this case of the data that we have we only have 20 different images。

 So really there's like five posters of superheroes 5 with animals， etca， etc。

 So there's high likelihood that we repeat those。 But if you had like hundreds of thousands then probably both with much really well。

 but wouldn't necessarily return the exactly same objects。

 And another thing that you can do this data is to use images to search across the posters on the poster vector space。

 So let's start with this image of this spooky situation。



![](img/c6ad1ac84c9117fdb1467145b6182a48_45.png)

![](img/c6ad1ac84c9117fdb1467145b6182a48_46.png)

![](img/c6ad1ac84c9117fdb1467145b6182a48_47.png)

So to search using this spooky image， what you need to do is call a near image with this spooky image converted to Bay 64 you want to search across the poster vector space and then when that's finished。

 let's just display the title and the poster to make the output a bit more cleaner and then execute this。



![](img/c6ad1ac84c9117fdb1467145b6182a48_49.png)

And what you got back are posteders for spooky movies like the nightmare before Christmas。

 Hocus Pocus， and Scre。

![](img/c6ad1ac84c9117fdb1467145b6182a48_51.png)

And as a final example， let's try to search for some superheroes based on this picture。

And the search is super similar。 but this time， just use a different image。

 And what we get back here is Aya is Batman versus Superman。 He also get Iron Man。



![](img/c6ad1ac84c9117fdb1467145b6182a48_53.png)

![](img/c6ad1ac84c9117fdb1467145b6182a48_54.png)

![](img/c6ad1ac84c9117fdb1467145b6182a48_55.png)

And I age， well， let's face it the squirrel chasing the nut is definitely a superhero mine。



![](img/c6ad1ac84c9117fdb1467145b6182a48_57.png)

And now that you're done with all the query， you can close the client and complete the lesson。



![](img/c6ad1ac84c9117fdb1467145b6182a48_59.png)

Well， that wraps up this lesson and the course and in this lesson what you learn is how to use a multi vector space and then surf across two different vector spaces。

 one being a text vector space another multimod space and then understand the data from different perspectives and as you could see some of the results could be similar across different vector spaces but also each vector space in each model could give you different types of results which can be very powerful could be very useful and I'm pretty sure you are going to come up with many ideas and many use cases on how to take this and make the most of it。



![](img/c6ad1ac84c9117fdb1467145b6182a48_61.png)
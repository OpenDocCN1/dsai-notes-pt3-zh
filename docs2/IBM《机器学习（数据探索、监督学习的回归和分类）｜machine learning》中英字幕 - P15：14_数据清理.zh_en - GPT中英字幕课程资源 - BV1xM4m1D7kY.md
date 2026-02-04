# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P15：14_数据清理.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

Now that we've pulled in our data， let's discuss the next steps。

 starting with the importance of cleaning our data。

So let's go over the learning goals for this section。



![](img/00c043c907092bf41011853f8d393405_1.png)

We're going to go over。Why data cleaning is important for machine learning Think garbage in garbage out。

 our models can only be as good as our data。

![](img/00c043c907092bf41011853f8d393405_3.png)

Some issues that arise with messy data and ways in which data can be messy in the first place。



![](img/00c043c907092bf41011853f8d393405_5.png)

How to identify duplicate or unnecessary data and how to handle that accordingly。



![](img/00c043c907092bf41011853f8d393405_7.png)

And policies for dealing with outliers and the pros and cons of different methods as there's not one size that fits all。



![](img/00c043c907092bf41011853f8d393405_9.png)

![](img/00c043c907092bf41011853f8d393405_10.png)

So why is data cleaning so important， We know that decisions and analytics are increasingly driven by data and models。



![](img/00c043c907092bf41011853f8d393405_12.png)

And key aspects of our machine learning workflow are going to depend on clean data。



![](img/00c043c907092bf41011853f8d393405_14.png)

Observations， an instance of the data， usually a row of the data set。 Think if a row。

 an observation is not clean。 We are misrepresenting to our model the relationship between our features and our targets。



![](img/00c043c907092bf41011853f8d393405_16.png)

![](img/00c043c907092bf41011853f8d393405_17.png)

![](img/00c043c907092bf41011853f8d393405_18.png)

Our labels have to be labeled correctly， right， Are output variables being predicted。

 We need to make sure that they are all labeled appropriately。 We can think to imagenet。

 which we discuss where were labeling all the pictures。

 and if humans were labeling the pictures in order to create that data set。

 If they mislabeled one of those pictures， then it will mislead our model。



![](img/00c043c907092bf41011853f8d393405_20.png)

![](img/00c043c907092bf41011853f8d393405_21.png)

![](img/00c043c907092bf41011853f8d393405_22.png)

![](img/00c043c907092bf41011853f8d393405_23.png)

Our algorithms， the computer programs that estimate models based on available data。

 we need to recognize that our algorithms are going to be learned。

 assuming the data accurately represents a real world。



![](img/00c043c907092bf41011853f8d393405_25.png)

![](img/00c043c907092bf41011853f8d393405_26.png)

Our features， the information we have for each information。

 if the recording of certain features are off， such as transaction amounts or locations with fraud。

 think about how easily that can throw off fraud detection。



![](img/00c043c907092bf41011853f8d393405_28.png)

![](img/00c043c907092bf41011853f8d393405_29.png)

And then the model itself， the hypotheide relationship between observations and data。

The model itself is going to be assuming that this is actual data representing the real world。

So the bottom line is messy data can lead to garbage in garbage out effect。And therefore。

 unreliable outcomes， given our data set。 So the first step must always be to ensure that our data is clean。

So what are some problems that companies face in regards to having clean data。



![](img/00c043c907092bf41011853f8d393405_31.png)

Be a lack of data for a model to be successful， there must be sufficient， relevant data。

 and if not companies need to start by ensuring that they are collecting the appropriate data or if needed acquiring additional data from third parties and making all that data accessible throughout their organization。



![](img/00c043c907092bf41011853f8d393405_33.png)

![](img/00c043c907092bf41011853f8d393405_34.png)

![](img/00c043c907092bf41011853f8d393405_35.png)

Now， although a lack of data can hamper AI adoption。

 the same can be said for having too much data when companies have too much data spread across different environments and databases。

 it quickly becomes a data engineering problem。 In this instance。

 companies need to collect and organize their data to make it ready to even consider getting into leveraging get for machine learning。



![](img/00c043c907092bf41011853f8d393405_37.png)

![](img/00c043c907092bf41011853f8d393405_38.png)

![](img/00c043c907092bf41011853f8d393405_39.png)

![](img/00c043c907092bf41011853f8d393405_40.png)

And then just bad data， garbage in， garbage out。 As we said earlier。

 the problem is that even though business leaders list improving the use of data as a top priority。

60% are challenged by managing data quality in the first place。



![](img/00c043c907092bf41011853f8d393405_42.png)

![](img/00c043c907092bf41011853f8d393405_43.png)

![](img/00c043c907092bf41011853f8d393405_44.png)

So the first step for any organization to get started with artificial intelligence or machine learning is ensuring that their data is actually ready for use。



![](img/00c043c907092bf41011853f8d393405_46.png)

![](img/00c043c907092bf41011853f8d393405_47.png)

So how can data be messy， what do we mean by messy data？



![](img/00c043c907092bf41011853f8d393405_49.png)

And have data duplicates that can bring extra weight to observations to a model or bring in unnecessary noise。

 So if we think about our example of fraud， if we have a certain credit card transaction that was fraud。

 and that's repeated 200 times with the label of fraud。

 All of those features that LED to that fraud will have a lot more weight because it was accidentally duplicated that many more times。



![](img/00c043c907092bf41011853f8d393405_51.png)

![](img/00c043c907092bf41011853f8d393405_52.png)

![](img/00c043c907092bf41011853f8d393405_53.png)

![](img/00c043c907092bf41011853f8d393405_54.png)

![](img/00c043c907092bf41011853f8d393405_55.png)

Inconsistent text and typos data will often depend on correct spelling， yet to have no extra spaces。

 the capitalized versus non capitalizeized letters。 This will all lead to the same feature。

 the same value for a feature being categorized as different values， within the same feature set。

 even though they should be categorized as the same。



![](img/00c043c907092bf41011853f8d393405_57.png)

![](img/00c043c907092bf41011853f8d393405_58.png)

![](img/00c043c907092bf41011853f8d393405_59.png)

![](img/00c043c907092bf41011853f8d393405_60.png)

You have missing data。 And that's going be something we'll have to deal with to some degree。

 no matter what， but too much in the wrong fields can lead to an inability to use certain features。

 which otherwise may have been powerful predictors。



![](img/00c043c907092bf41011853f8d393405_62.png)

![](img/00c043c907092bf41011853f8d393405_63.png)

![](img/00c043c907092bf41011853f8d393405_64.png)

Outliers will occur that can skew a feature disproportionately and make it difficult to find the true underlying model。



![](img/00c043c907092bf41011853f8d393405_66.png)

We can have data sourcing issues， we have trouble bringing in data from multiple systems or working with different database types。



![](img/00c043c907092bf41011853f8d393405_68.png)

![](img/00c043c907092bf41011853f8d393405_69.png)

Or trying to wrangle and combine data coming from on premises versus on the cloud or many others。

 and trying to pull in data from all these different data sources can lead to a mismatch when trying to talk about the same data when it's being pulled in from different sources。



![](img/00c043c907092bf41011853f8d393405_71.png)

![](img/00c043c907092bf41011853f8d393405_72.png)

![](img/00c043c907092bf41011853f8d393405_73.png)

So let's start off with how do we work with duplicated data？



![](img/00c043c907092bf41011853f8d393405_75.png)

We want to dive in and see if duplicate observations are indeed needed or not。

 It's possible for our ir data set， for example， to have duplicates。

 if two flowers are indeed exactly the same， they have the same exact measurements for sepel and petal length and they are the same species that can happen out in the wild。

 Given that we're only going up to two decimal points and we'd probably want to keep both those observations in place if that's happening in the real world。

 Now， if we're trying to label pictures， for example。

 we probably don't want to have duplicate of the same exact picture。

 because that's not going to help in our labeling process at all。



![](img/00c043c907092bf41011853f8d393405_77.png)

![](img/00c043c907092bf41011853f8d393405_78.png)

![](img/00c043c907092bf41011853f8d393405_79.png)

![](img/00c043c907092bf41011853f8d393405_80.png)

![](img/00c043c907092bf41011853f8d393405_81.png)

![](img/00c043c907092bf41011853f8d393405_82.png)

![](img/00c043c907092bf41011853f8d393405_83.png)

It's always a good idea to look at the features and filter the data first to get a better look at the duplicates。



![](img/00c043c907092bf41011853f8d393405_85.png)

![](img/00c043c907092bf41011853f8d393405_86.png)

Just in case I would always suggest not to filter too much to ensure you keep access to the initial data that may be useful later on。



![](img/00c043c907092bf41011853f8d393405_88.png)

Now that's it for this section in the next section we're going to talk about working with missing values as well as working with outlier values。

 Look forward to seeing you there。

![](img/00c043c907092bf41011853f8d393405_90.png)

![](img/00c043c907092bf41011853f8d393405_91.png)

![](img/00c043c907092bf41011853f8d393405_92.png)
# Mathworks《实用数据科学与MATLAB（数据探索、特征工程、机器学习、毕业项目）｜Practical Data Science with MATLAB》 p97 12_使用分类学习器应用程序.zh_en [BV1Jr421w7wL_p97]

🎼。

![](img/395ca753cd0bc8e3d9fb4197fe57b761_1.png)

You've learned the basic ideas behind some common classification models。

 now let's apply that knowledge to the taxi data。

![](img/395ca753cd0bc8e3d9fb4197fe57b761_3.png)

Commercial navigation apps provide a lot of information about your trip， distance。

 estimated travel time， and tools you may encounter on route。

Can the pickup and drop off locations from the taxi data predict if the trip will have a toll。

 let's use a binary classification model to find out。



![](img/395ca753cd0bc8e3d9fb4197fe57b761_5.png)

In this video， you will create classification models using the classification learner app。

Compare the performance of those models and export your work to MATLAb for further analysis。



![](img/395ca753cd0bc8e3d9fb4197fe57b761_7.png)

The classification learner app uses the same workflow as the regression learner app。



![](img/395ca753cd0bc8e3d9fb4197fe57b761_9.png)

Once you have selected your data， the app enables you to iterate through the process of choosing。

 training， and assessing your model before exporting to MATLAb。



![](img/395ca753cd0bc8e3d9fb4197fe57b761_11.png)

To get started， you first need to import and prepare your data in MATLab。



![](img/395ca753cd0bc8e3d9fb4197fe57b761_13.png)

Here， the January taxi data is loaded。The Add was Toll paid function adds a variable to the table。

 indicating if a toolll was paid to each trip， this will serve as the response variable over the classification models。

With the data preproces done， let's open the classification Learner app。



![](img/395ca753cd0bc8e3d9fb4197fe57b761_15.png)

In the apps tab of the To strip， choose the classification learner app。



![](img/395ca753cd0bc8e3d9fb4197fe57b761_17.png)

Just as you did with the regressionion Learner app， start a new session by clicking New session。

And selecting from Workspace。Select was tool paid as the response variable。

Classification response variables are most often logical or categorical variables since these naturally break the data set into different classes。

In the Preors pane， unselect all of the variables and select the four features that will be used to build the predictive model。

The latitude and longitude of the pickup location and the latitude and longitude of the drop off location。

As with the regression learner app， your typical workflow will involve using validation as part of your model training。

 but that topic will be covered in a future lesson， so for now， select No validation。



![](img/395ca753cd0bc8e3d9fb4197fe57b761_19.png)

Click Start session to finish loading the data。

![](img/395ca753cd0bc8e3d9fb4197fe57b761_21.png)

The classificationification learner app mirrors the regression learner app。

The tool stripip along the top enables you to easily choose the model type， access model options。

 train the model， and visualize the results。

![](img/395ca753cd0bc8e3d9fb4197fe57b761_23.png)

![](img/395ca753cd0bc8e3d9fb4197fe57b761_24.png)

The left pane shows the model history and the details of the current model。



![](img/395ca753cd0bc8e3d9fb4197fe57b761_26.png)

The center pane shows model visualizations。The default is a scatterplot of the data。



![](img/395ca753cd0bc8e3d9fb4197fe57b761_28.png)

Here， pickup up locations are displayed and grouped according to the W toolll paid variable。

 The blue dots indicate that no tool was paid。

![](img/395ca753cd0bc8e3d9fb4197fe57b761_30.png)

![](img/395ca753cd0bc8e3d9fb4197fe57b761_31.png)

The main differences between the two apps are in the models and visualizations available。



![](img/395ca753cd0bc8e3d9fb4197fe57b761_33.png)

Open the model type pane to see the available classification models。

Logistic regression is a good starting point for creating a binary classification model。

 It's quick to train and provides a simple expression to classify the data。😊。

Now let's train the model。Wow， the model only took a few seconds to train。

 and it has over 95% accuracy。

![](img/395ca753cd0bc8e3d9fb4197fe57b761_35.png)

The group scatterpl now uses markers to indicate where the model correctly predicted that a toll was paid。



![](img/395ca753cd0bc8e3d9fb4197fe57b761_37.png)

Dots represent a correct prediction， and x's represent when the model was incorrect。



![](img/395ca753cd0bc8e3d9fb4197fe57b761_39.png)

More specifically， blue X's indicate where there was no toll paid， but the model predicted a toll。



![](img/395ca753cd0bc8e3d9fb4197fe57b761_41.png)

And orange X's indicate where a toll was paid， but the model didn't predict it。



![](img/395ca753cd0bc8e3d9fb4197fe57b761_43.png)

That's a bit confusing， but a confusion matrix can clear things up。



![](img/395ca753cd0bc8e3d9fb4197fe57b761_45.png)

This visualization shows how often a model gets each class right and which class is chosen when the model misclassifies a data point。



![](img/395ca753cd0bc8e3d9fb4197fe57b761_47.png)

The rows represent the value of was tool paid from the dataset set。

The top row of the matrix shows trips that did not have a toll。

 and the bottom row shows trips that did have a toll。The columns represent the model predictions。

The first column contains trips that the model predicted would not have a tool。

 and the second column contains trips that the model predicted would have a tool。

The main diagonal elements are the trips where the model correctly predicted the response。

 either true negatives， where there was no toll and the model predicted no toll。

 or true positives where there was a toolll and the model predicted a toolll。

The off diagonal entries show where the model made an incorrect prediction。

The top right corner shows the false positives， the model predicted a toll that wasn't there。

The bottom corner shows the false negatives。Here， the model incorrectly predicted a toll free trip。



![](img/395ca753cd0bc8e3d9fb4197fe57b761_49.png)

In this situation， a false positive could be a pleasant surprise。

 You expected a toll and didn't have to pay one。

![](img/395ca753cd0bc8e3d9fb4197fe57b761_51.png)

But a false negative means a surprise toll。 too many of those would be annoying。



![](img/395ca753cd0bc8e3d9fb4197fe57b761_53.png)

But what if instead of tolls， you were testing for a disease here。

 a false positive could be scary and lead to extra testing。

 but a false negative could lead to serious illness going undiagnosed， delaying possible treatments。

Your domain knowledge will guide you in deciding when false positives and false negatives are acceptable。

Minimizing one or the other could be very important。In this model。

 only about 10% of the actual tools are correctly predicted by the model。



![](img/395ca753cd0bc8e3d9fb4197fe57b761_55.png)

This is because of the imbalance in the class sizes。Out of the over 230，000 trips， fewer than 10。

000 had a toll。Since only about 4% of the trips have tolls。

 a model that always predicts no toll would have 96% accuracy， it just wouldn't be very useful。



![](img/395ca753cd0bc8e3d9fb4197fe57b761_57.png)

Models like logistic regression and SVM often have trouble dealing with data sets with imbalance classes like this。

Let's try a can nearest neighbor or KNN model instead。

Lop passed several options for nearest neighbor classifiers。



![](img/395ca753cd0bc8e3d9fb4197fe57b761_59.png)

The fine， medium， and co models use Euclidean distance， while cosine， cubic。

 and weighted use more complex distance measures。

![](img/395ca753cd0bc8e3d9fb4197fe57b761_61.png)

Choose Mediium KNN as a starting point。

![](img/395ca753cd0bc8e3d9fb4197fe57b761_63.png)

This model has tuning options available via the Advanced button。

A medium KNN model uses the 10 nearest data points to make a prediction。



![](img/395ca753cd0bc8e3d9fb4197fe57b761_65.png)

A course model looks at the 100 closest points。And a fine model uses the single closest point to make its prediction。



![](img/395ca753cd0bc8e3d9fb4197fe57b761_67.png)

Let's train the model。

![](img/395ca753cd0bc8e3d9fb4197fe57b761_69.png)

99% accuracy。Remember， though， always predicting no toll was 96% accurate。



![](img/395ca753cd0bc8e3d9fb4197fe57b761_71.png)

The scatter plot has significantly fewer visible X's。 This model looks promising， but。

Let's check the confusion matrix。

![](img/395ca753cd0bc8e3d9fb4197fe57b761_73.png)

There are many more true positives with this model。

 It looks like the KNN model could be a good choice for this prediction。To determine how good。

 we'll need more performance measurements。

![](img/395ca753cd0bc8e3d9fb4197fe57b761_75.png)

The following lessons will cover these in detail for now。

 let's save your work by exporting the model to MatTLb like the regression learner app。

 the classification learner app has the option to save the algorithm used to train the model or to export the train model directly into the MATLb workspace。



![](img/395ca753cd0bc8e3d9fb4197fe57b761_77.png)

![](img/395ca753cd0bc8e3d9fb4197fe57b761_78.png)

Click Export model and choose Ex model from the list。



![](img/395ca753cd0bc8e3d9fb4197fe57b761_80.png)

Name the exported model， K and N model。

![](img/395ca753cd0bc8e3d9fb4197fe57b761_82.png)

The model is now available in the MATLb workspace。

![](img/395ca753cd0bc8e3d9fb4197fe57b761_84.png)

You can access it in the same way you access the regression models。



![](img/395ca753cd0bc8e3d9fb4197fe57b761_86.png)

In this lesson， you learn how to use the classificationification learner app to select， train。

 and assess some simple classification models。You found a promising candidate to predict if a trip will have a toll based on the pickup and drop off locations。

In the following lessons， you'll learn more about metrics used to quantify classification model performance。



![](img/395ca753cd0bc8e3d9fb4197fe57b761_88.png)

Yeah。
# Mathworks《工程与科学计算机视觉（简介、机器学习、目标检测）｜Computer Vision for Engineering and Science》 p16 5_训练图像分类模型.zh_en -BV1yJ4m13715_p16-

🎼，Previously， you extracted some intensity based features from the concrete image data set。

In this video， you'll train and evaluate a classification model that uses these features to label the images as having or not having a crack。



![](img/b5ad5b2f3cc3c5da758d400c973b9f6a_1.png)

You'll then use this classifier to predict the labels of some new unlabelled images shown here。



![](img/b5ad5b2f3cc3c5da758d400c973b9f6a_3.png)

Because you won't know in advance which models and parameters will give the best results。

 It's common to train many models， and compare them。To facilitate this process。

 we'll use the classification learner app。

![](img/b5ad5b2f3cc3c5da758d400c973b9f6a_5.png)

Begin in Matlab and make sure you load the training table variable in the MA file saved in the live script from the previous reading。



![](img/b5ad5b2f3cc3c5da758d400c973b9f6a_7.png)

Then open the classificationification learner app and start a new session。



![](img/b5ad5b2f3cc3c5da758d400c973b9f6a_9.png)

To load the training data set into the app， select the concrete table as the input variable。

The table's columns appear below as either response or predictor variables。

The response variable contains the categories that each image will be predicted as belonging to。



![](img/b5ad5b2f3cc3c5da758d400c973b9f6a_11.png)

Choose crack label， which has the two categorical values of crack or no crack。



![](img/b5ad5b2f3cc3c5da758d400c973b9f6a_13.png)

The predictors are the variables used to determine the response。In this case。

 the model should not consider the image name。 So remove it from the list。Next。

 you'll need to choose the validation method and test data set。

Remember that both validation and test data are critical in machine learning to avoid mistakes like overfitting your model to the data。

The test data is used to confirm your best model after training is complete。

 If you've not already set aside test data， you could do it here。

The validation data is used to compare models during the training and evaluation process。



![](img/b5ad5b2f3cc3c5da758d400c973b9f6a_15.png)

To illustrate the importance of validation data。Imagine you have a simple data set consisting of two classes and two predictor variables。

First， the validation data is set aside。Then the model is trained in this case。

 using a highly complex linear SVM kernel， resulting in a squiggly decision boundary。

If the boundary is complex enough， your model can achieve up to 100 per cent accuracy on the training data。

 Ma it seem much better than it is。That's why the model is evaluated on the reserved validation data。

This overly specific model will likely yield many misclassified validation points。

 correctlyly marking it as having poor performance。In this way。

 validation identifies complex decision boundaries that are overly sensitive to noise during the training process。



![](img/b5ad5b2f3cc3c5da758d400c973b9f6a_17.png)

The two most common schemes for validation are hold out validation and cross validation。



![](img/b5ad5b2f3cc3c5da758d400c973b9f6a_19.png)

Holdout validation is reserved by setting aside a fixed percentage of the data for evaluation。

This option results in models that are quicker to train。

 but are potentially less robust to overfitting。Therefore。

 it is typically reserved for large data sets。Cross validation is generally the preferred method。

However， it requires training the same model multiple times using different subsets of the data。

Therefore， it's more computationally expensive。For this example of 800 images。

 we'll stay with a default choice of five fold cross validation。



![](img/b5ad5b2f3cc3c5da758d400c973b9f6a_21.png)

![](img/b5ad5b2f3cc3c5da758d400c973b9f6a_22.png)

You're now ready to start the session and train some models。

The app will generate a scatter plot of the predictor features。

 much like what was shown after they were generated。



![](img/b5ad5b2f3cc3c5da758d400c973b9f6a_24.png)

Along the top， the tool strip shows various options for training classifiers。

You can select model types， train them。Use plots to compare their results。

Evaluate their performance on the test dataset set。And export them to Matlab， to make predictions。



![](img/b5ad5b2f3cc3c5da758d400c973b9f6a_26.png)

There are also options available to tune or select predictor features。

But this is often done after some initial training。

 And when several predictors are either irrelevant or redundant。



![](img/b5ad5b2f3cc3c5da758d400c973b9f6a_28.png)

![](img/b5ad5b2f3cc3c5da758d400c973b9f6a_29.png)

To select a model to train， use the drop down list of available models。

Notice that there are many different categories of models to choose from。And within each category。

 there are often several standard hyperparameter settings。



![](img/b5ad5b2f3cc3c5da758d400c973b9f6a_31.png)

Hyperparameters are model specific options that are chosen by the user。



![](img/b5ad5b2f3cc3c5da758d400c973b9f6a_33.png)

For example， a hyperparameter for a K and N model is K。

 The number of points to treat as neighbors with the default options labeled as fine。

 medium and coarse。

![](img/b5ad5b2f3cc3c5da758d400c973b9f6a_35.png)

But what is the value of K for these three options。To find out。

 select each one from the menu to add them to your list of models。



![](img/b5ad5b2f3cc3c5da758d400c973b9f6a_37.png)

The model's summary window shows all the available hyperparameter to tune。

 including the number of neighbors value， which is 100 for course。



![](img/b5ad5b2f3cc3c5da758d400c973b9f6a_39.png)

10 for medium。

![](img/b5ad5b2f3cc3c5da758d400c973b9f6a_41.png)

And one for fine。You'll also notice the fine tree model， which is included by default。For now。

 you can delete it and we'll just stick with the KN N models。



![](img/b5ad5b2f3cc3c5da758d400c973b9f6a_43.png)

And that's it。 You're now ready to train some classification models。



![](img/b5ad5b2f3cc3c5da758d400c973b9f6a_45.png)

Select the train all button and wait just a moment while your computer does all the hard work。



![](img/b5ad5b2f3cc3c5da758d400c973b9f6a_47.png)

After each model is finished training， it'll show an accuracy percentage of correctly labeled images calculated using the validation data。



![](img/b5ad5b2f3cc3c5da758d400c973b9f6a_49.png)

This metric， along with others discussed later， is used to compare your trained models so that you can choose the best one as part of the evaluation process。



![](img/b5ad5b2f3cc3c5da758d400c973b9f6a_51.png)

For a more in depth analysis of how well a model performs， you can also examine the confusion matrix。

This plot is a standard way to visualize classification results。

 as it shows all possible outcome combinations for an image's true class versus the class predicted by the model。



![](img/b5ad5b2f3cc3c5da758d400c973b9f6a_53.png)

In this case， about 90% of the crack images were correctly predicted to have cracks。

And only a small number of images were predicted to have cracks， but actually had no cracks。



![](img/b5ad5b2f3cc3c5da758d400c973b9f6a_55.png)

Once you've trained this model type yourself， you may see slightly different numbers than what is shown here。

 That's because the validation subset is randomly selected when importing the data into the app。

Based on the accuracy alone， it looks like the medium K and N model。

 which had a value of K equal to 10， performed the best。



![](img/b5ad5b2f3cc3c5da758d400c973b9f6a_57.png)

But will another value of K do better。

![](img/b5ad5b2f3cc3c5da758d400c973b9f6a_59.png)

To find out， duplicate the model。Then change the number of neighbors to something else， like5。

This process of finding the value of k that yields the best model is an example of hyperparameter optimization。

 which you can automate using the optizable K and N model。But for now， we'll just do it manually。

Before we train again， let's also see how SVM models perform。

You can train all the available default SVM models with various kernel functions by selecting the All SVMs option。



![](img/b5ad5b2f3cc3c5da758d400c973b9f6a_61.png)

Now we're ready to train again。You'll likely notice that SVM models are slower to train than K& N。



![](img/b5ad5b2f3cc3c5da758d400c973b9f6a_63.png)

If you want to train a lot of models or have a very large data set， this step could take some time。



![](img/b5ad5b2f3cc3c5da758d400c973b9f6a_65.png)

But luckily， for this example， we're done relatively quickly。This time。

 the new K And N model performed better than before。However。

 it was overtaken by an even more accurate SVM classifier with a non linear kernel。



![](img/b5ad5b2f3cc3c5da758d400c973b9f6a_67.png)

Return to the scatter plot visualization to see which data points were incorrectly classified。Here。

 the two predicted classes are shown using two colors。

 and an X marker is used if the prediction was incorrect。Overall。

 I'd say this model performed quite well。Because validation data is used during the training process。

 there's still a chance the model could overfit the data。

That's where the test data you set aside earlier comes in。The test data is not used during training。

Therefore， if we did everything right， the validation accuracy should match the accuracy calculated using the test data。



![](img/b5ad5b2f3cc3c5da758d400c973b9f6a_69.png)

To generate the test data。Switch to Matlab。The test data store should already be loaded into your workspace from the mat file。

Use it to generate the test data table by applying the custom feature extraction function。



![](img/b5ad5b2f3cc3c5da758d400c973b9f6a_71.png)

Back in the app， you can now load the test data table variable into the app here。



![](img/b5ad5b2f3cc3c5da758d400c973b9f6a_73.png)

Select it from the drop down menu and confirm that the correct response and predictor variables are used。



![](img/b5ad5b2f3cc3c5da758d400c973b9f6a_75.png)

After importing， you can reevaluate every model using the test data。

Notice that all the reported acuracies have changed， but only by at most， a single percentage point。

This is a good sign that the models can be trusted and are ready to use。

There are several ways to proceed from here。

![](img/b5ad5b2f3cc3c5da758d400c973b9f6a_77.png)

You can save the app session so that you can later resume where you left off。



![](img/b5ad5b2f3cc3c5da758d400c973b9f6a_79.png)

You can generate a MALb function， which you can use to retrain a model using the same hyperparameters on a new data set。

Or you can export the model itself into the MatTLb workspace。



![](img/b5ad5b2f3cc3c5da758d400c973b9f6a_81.png)

We want to see our new model in action， so let's export it。After naming the model variable， select O。



![](img/b5ad5b2f3cc3c5da758d400c973b9f6a_83.png)

In Matlab， notice how the trained model is now in the variable workspace。

 You'll also notice how it's of data typestruct， which is short for structure。

This data type is used to store dissimilar types of data in the same variable。

You'll find that it behaves like a table variable and that it uses dot notation to specify fields。



![](img/b5ad5b2f3cc3c5da758d400c973b9f6a_85.png)

Remember， the original goal was to use the trained model to classify the set of unlabelled images as having cracks or no cracks。



![](img/b5ad5b2f3cc3c5da758d400c973b9f6a_87.png)

To do this， repeat the steps to generate the data table for the new images by first organizing them into a data store。

Then generating the intensity based features using your custom function。To make a prediction。

 use the exported model structure along with dot notation to access the prediction function。

And pass in the unlabeled data table， as the input。Then save the output to a new variable。

Running the results。Gives you a table with a column listing the predicted class for each image。

One way to visually inspect the results is to use the montage function。

 which accepts an input of image file names。Along with logical indexing to isolate just the images for one of the classes。

Repeat this for the other class。

![](img/b5ad5b2f3cc3c5da758d400c973b9f6a_89.png)

And look at the results。

![](img/b5ad5b2f3cc3c5da758d400c973b9f6a_91.png)

You may notice this image of textured concrete that was mislabelled as having a crack。

But that's expected for a model that used only two basic features。 So I'd call this a success。

Now it's your turn to test out the image classifier。

Find your own pictures of concrete and see how accurately the model labels them。

Then share your results on the forums。
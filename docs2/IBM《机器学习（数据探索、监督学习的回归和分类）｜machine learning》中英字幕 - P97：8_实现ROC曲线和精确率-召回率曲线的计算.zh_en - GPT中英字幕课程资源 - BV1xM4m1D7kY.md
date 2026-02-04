# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P97：8_实现ROC曲线和精确率-召回率曲线的计算.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

So here's an example where we extend this to multiple classes and we have here a three class classification problem。

 again， that blue diagonal is going to be the true predictions by the model assuming that we gotten them correct。

 so we predicted them all correctly。

![](img/81fb43155f2fbf086450047accb3c8ed_1.png)

![](img/81fb43155f2fbf086450047accb3c8ed_2.png)

![](img/81fb43155f2fbf086450047accb3c8ed_3.png)

![](img/81fb43155f2fbf086450047accb3c8ed_4.png)

And accuracy， once we extend to three labels or three classes。

 is just going to be the ratio of this diagonal。

![](img/81fb43155f2fbf086450047accb3c8ed_6.png)

![](img/81fb43155f2fbf086450047accb3c8ed_7.png)

Over the total number of samples， so very similar to what we saw with just the two examples or the two labels。



![](img/81fb43155f2fbf086450047accb3c8ed_9.png)

Now there's no directed generalization of ROC precision recall and the remainder of the measures。

 but we can look at both precision recall specificity etc。

 for each class as a one versus all approach so we can look at the specificity of class one versus the rest class two versus the rest and so on and with that when we're looking at multiclass classification it'll still also be important to pick or define the right metric for the problem at hand and we want to think for multiple classes at this point what is the cost of misclassifying one class as the other so what's the cost of misclassifying class one is class2 class3 is class1 etc and this is where're also looking at our larger confusion matrix so our confusion matrix is what did we predict versus what of the actual values and we can see here predicted class1 versus actual class2 we can see that within the matrix will help us make these decisions。



![](img/81fb43155f2fbf086450047accb3c8ed_11.png)

![](img/81fb43155f2fbf086450047accb3c8ed_12.png)

![](img/81fb43155f2fbf086450047accb3c8ed_13.png)

![](img/81fb43155f2fbf086450047accb3c8ed_14.png)

![](img/81fb43155f2fbf086450047accb3c8ed_15.png)

![](img/81fb43155f2fbf086450047accb3c8ed_16.png)

![](img/81fb43155f2fbf086450047accb3c8ed_17.png)

![](img/81fb43155f2fbf086450047accb3c8ed_18.png)

As well， and we can actually pull out these confusion matrixes using Python。



![](img/81fb43155f2fbf086450047accb3c8ed_20.png)

![](img/81fb43155f2fbf086450047accb3c8ed_21.png)

So the error metrics are going to be located in the appropriately named metrics library of PsyitLarn so here we see from the metrics library we import the accuracy score and for essentially any one of these metrics they follow a similar syntax where the inputs are the actual and predicted labels respectively。

 as we see here， the test versus what we actually predicted， so the test being the actual values。



![](img/81fb43155f2fbf086450047accb3c8ed_23.png)

![](img/81fb43155f2fbf086450047accb3c8ed_24.png)

![](img/81fb43155f2fbf086450047accb3c8ed_25.png)

![](img/81fb43155f2fbf086450047accb3c8ed_26.png)

And we're able to get the accuracy score there and if we wanted to do the same thing using any of our other scores。

 we see that we have precision score available recall score， F1 score， ROC， AUC score。

 the we can actually pull out the confusion matrix as I promise in just the last slide。

 the ROC curve， the precision recall curve and even more if you want to look deeper into the metrics library。



![](img/81fb43155f2fbf086450047accb3c8ed_28.png)

![](img/81fb43155f2fbf086450047accb3c8ed_29.png)

![](img/81fb43155f2fbf086450047accb3c8ed_30.png)

![](img/81fb43155f2fbf086450047accb3c8ed_31.png)

![](img/81fb43155f2fbf086450047accb3c8ed_32.png)

Some of them take in the predicted classes， so predicting either one or zero， such as accuracy。

 the F1 precision and recall， and some of them are going to take in the predicted probabilities。

 so we want to keep this in mind as we discuss ROC AUC score and the precision recall curve we'll both bring in probabilities if you're unsure I would suggest just looking at the documentation and it'll give you a clear picture of which one you should be passing into each one of these different AR metrics。



![](img/81fb43155f2fbf086450047accb3c8ed_34.png)

![](img/81fb43155f2fbf086450047accb3c8ed_35.png)

![](img/81fb43155f2fbf086450047accb3c8ed_36.png)

![](img/81fb43155f2fbf086450047accb3c8ed_37.png)

![](img/81fb43155f2fbf086450047accb3c8ed_38.png)

So now let's recap what we've learned here in this section。In this section。

 we broke down the importance of how to separate out different error types。

 such as type1 and type2 errors and looking at them in relation to both the actual values of our labels。

 as well as the values that we predicted for each one of those labels。



![](img/81fb43155f2fbf086450047accb3c8ed_40.png)

![](img/81fb43155f2fbf086450047accb3c8ed_41.png)

![](img/81fb43155f2fbf086450047accb3c8ed_42.png)

With that， we discussed many approaches to measuring classification outcomes outside of accuracy。

 such as precision， recall the F1 score， the ROC curve， and the precision recall curve。



![](img/81fb43155f2fbf086450047accb3c8ed_44.png)

![](img/81fb43155f2fbf086450047accb3c8ed_45.png)

And then we learned how with our different ways of measuring error。

 we must realize that the error metric and model we end up choosing will depend on whether our business problems should focus on accuracy overall。

 or having a low number of false positives or a high number of true positives， etc。



![](img/81fb43155f2fbf086450047accb3c8ed_47.png)

![](img/81fb43155f2fbf086450047accb3c8ed_48.png)

![](img/81fb43155f2fbf086450047accb3c8ed_49.png)

And with that， we close out our section here on measuring error and we will jump into our notebook on logistic regression as well as actually looking at these different error classification metrics in practice。

 thank you。

![](img/81fb43155f2fbf086450047accb3c8ed_51.png)

![](img/81fb43155f2fbf086450047accb3c8ed_52.png)

![](img/81fb43155f2fbf086450047accb3c8ed_53.png)